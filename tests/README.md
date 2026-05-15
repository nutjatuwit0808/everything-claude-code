# tests/

โฟลเดอร์นี้เก็บ **ชุดทดสอบ (test suite)** สำหรับตรวจสอบความถูกต้องของ scripts, hooks, และ configurations ทั้งหมดใน ECC

## ภาพรวม

Tests ใช้ Node.js built-in test runner โดยไม่ต้องพึ่ง testing framework ภายนอก โครงสร้างของ `tests/` สะท้อน (mirror) โครงสร้างของ `scripts/` เพื่อให้หาได้ง่าย

## การรันทดสอบ

```bash
# รันทุก tests
node tests/run-all.js

# รัน test แต่ละไฟล์
node tests/lib/utils.test.js
node tests/lib/package-manager.test.js
node tests/hooks/hooks.test.js
```

## โครงสร้าง

```
tests/
├── run-all.js          — Entry point รันทุก tests
├── lib/                — Tests สำหรับ scripts/lib/
├── hooks/              — Integration tests สำหรับ hooks
├── scripts/            — Tests สำหรับ standalone scripts
├── commands/           — Tests สำหรับ commands
├── docs/               — Tests สำหรับ documentation
├── ci/                 — CI-specific test utilities
├── integration/        — Integration tests ข้ามระบบ
└── *.test.js           — Test files สำหรับ root-level configs
```

## Test Files หลัก

| ไฟล์ | สิ่งที่ทดสอบ |
|------|-------------|
| `tests/lib/utils.test.js` | utility functions |
| `tests/lib/package-manager.test.js` | package manager detection |
| `tests/hooks/hooks.test.js` | hook behavior integration |
| `codex-config.test.js` | Codex configuration |
| `opencode-config.test.js` | OpenCode configuration |
| `plugin-manifest.test.js` | plugin manifest validation |

## Python Tests

โฟลเดอร์นี้ยังมี Python tests สำหรับ `src/` module:

```bash
pytest tests/test_builder.py
pytest tests/test_executor.py
pytest tests/test_resolver.py
```

## กฎการเขียน Tests

- Script ใหม่ใน `scripts/lib/` ต้องมี test ที่ตรงกันใน `tests/lib/`
- Hook ใหม่ต้องมี integration test อย่างน้อย 1 ตัวใน `tests/hooks/`
- รัน `node tests/run-all.js` ก่อน commit ทุกครั้ง
- Test suite ต้อง green ทั้งหมด (~1000+ tests) ก่อน merge

## สถานะ

โปรเจกต์รักษา test suite ให้ green เสมอ — ปัจจุบัน 997+ tests passing ครอบคลุม hooks, scripts, configurations, และ plugin manifests
