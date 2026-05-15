# scripts/

โฟลเดอร์นี้เก็บ **Node.js utilities** — สคริปต์ที่ใช้งานข้ามแพลตฟอร์ม (Windows, macOS, Linux) สำหรับ hooks, installation, และ session management

## ภาพรวม

ทุกไฟล์ใช้ CommonJS (`require`/`module.exports`) รองรับ Node.js >=18 สคริปต์แบ่งออกเป็น 2 กลุ่มหลัก: scripts ที่ทำงานตรง และ helper libraries ใน `lib/`

## โครงสร้าง

```
scripts/
├── hooks/          — Hook scripts ที่ทำงานตาม event ของ Claude Code
├── lib/            — Shared utility libraries
├── ci/             — CI/CD helper scripts
├── codemaps/       — Code mapping utilities
├── codex/          — Codex-specific scripts
├── codex-git-hooks/ — Git hooks สำหรับ Codex
└── *.js            — Standalone utility scripts
```

## scripts/hooks/ — Hook Scripts

สคริปต์ที่ทำงานอัตโนมัติตาม lifecycle ของ Claude Code:

### Session Hooks
- `session-start.js` — รันเมื่อเริ่ม session
- `session-end.js` — รันเมื่อ session สิ้นสุด
- `session-activity-tracker.js` — ติดตามกิจกรรมใน session
- `session-end-marker.js` — บันทึก marker เมื่อ session จบ

### PreToolUse Hooks (รันก่อน tool ทำงาน)
- `pre-bash-commit-quality.js` — ตรวจสอบคุณภาพก่อน commit
- `pre-bash-dev-server-block.js` — ป้องกันการรัน dev server โดยไม่ตั้งใจ
- `pre-bash-git-push-reminder.js` — เตือนก่อน git push
- `config-protection.js` — ปกป้องไฟล์ config สำคัญ
- `block-no-verify.js` — บล็อก `--no-verify` flag

### PostToolUse Hooks (รันหลัง tool ทำงาน)
- `post-edit-format.js` — จัดรูปแบบโค้ดหลังแก้ไข
- `post-edit-typecheck.js` — ตรวจสอบ types หลังแก้ไข
- `post-bash-build-complete.js` — แจ้งเตือนเมื่อ build เสร็จ
- `post-bash-command-log.js` — บันทึก log ของ commands

### Quality & Security
- `quality-gate.js` — ตรวจสอบ quality standards
- `design-quality-check.js` — ตรวจสอบคุณภาพ design
- `check-console-log.js` — ตรวจจับ console.log ที่ลืมลบ
- `gateguard-fact-force.js` — ตรวจสอบ facts ที่ต้องปฏิบัติ

### Observability
- `cost-tracker.js` — ติดตามค่าใช้จ่าย API
- `ecc-metrics-bridge.js` — ส่ง metrics ไปยัง monitoring
- `ecc-statusline.js` — แสดงสถานะใน status line
- `desktop-notify.js` — แจ้งเตือนบน desktop

## scripts/lib/ — Shared Libraries

| ไฟล์ | หน้าที่ |
|------|---------|
| `utils.js` | utility functions ทั่วไป |
| `package-manager.js` | ตรวจจับและจัดการ package manager |
| `session-manager.js` | จัดการ sessions |
| `state-store/` | SQLite state store |
| `install/` | installation utilities |
| `skill-evolution/` | พัฒนา skills อัตโนมัติ |
| `hook-flags.js` | จัดการ `ECC_HOOK_PROFILE` และ `ECC_DISABLED_HOOKS` |
| `project-detect.js` | ตรวจจับชนิดของโปรเจกต์ |

## Standalone Scripts

| ไฟล์ | หน้าที่ |
|------|---------|
| `install-plan.js` | วางแผนการ install components |
| `install-apply.js` | ดำเนินการ install ตาม plan |
| `status.js` | แสดงสถานะระบบ |
| `doctor.js` | ตรวจสอบและแก้ไขปัญหา setup |
| `harness-audit.js` | ตรวจสอบ harness |
| `orchestrate-worktrees.js` | จัดการ git worktrees |
| `sessions-cli.js` | CLI สำหรับจัดการ sessions |
| `uninstall.js` | ถอนการติดตั้ง ECC |

## Hook Runtime Controls

ทุก hook script รองรับ environment variables:
- `ECC_HOOK_PROFILE=minimal|standard|strict` — กำหนด profile ของ hooks
- `ECC_DISABLED_HOOKS=hook1,hook2` — ปิดการใช้งาน hooks บางตัว

Hook scripts ทุกตัวต้อง exit 0 เมื่อเกิดข้อผิดพลาดที่ไม่ critical เพื่อไม่ให้ block การทำงานของ tool
