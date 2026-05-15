# agents/

โฟลเดอร์นี้เก็บ **AI subagents เฉพาะทาง** ที่สามารถถูก delegate งานจาก Claude Code ได้

## ภาพรวม

Agent แต่ละตัวคือไฟล์ Markdown ที่มี YAML frontmatter กำหนดชื่อ คำอธิบาย เครื่องมือที่ใช้ได้ และโมเดล AI ที่เหมาะสม เมื่อ Claude Code ต้องการทำงานเฉพาะทาง เช่น ตรวจสอบโค้ด หรือแก้ไข build error จะ delegate ให้ agent ที่เหมาะสมทำงานแทน

## รูปแบบไฟล์

```markdown
---
name: agent-name
description: คำอธิบายว่า agent นี้ทำอะไร
tools: [Read, Write, Bash, ...]
model: claude-sonnet-4-6
---

เนื้อหา prompt สำหรับ agent นี้
```

## ประเภท Agents (60+ ตัว)

### Code Review
- `code-reviewer.md` — ตรวจสอบคุณภาพโค้ดทั่วไป
- `typescript-reviewer.md` — เฉพาะ TypeScript
- `python-reviewer.md` — เฉพาะ Python
- `rust-reviewer.md`, `cpp-reviewer.md`, `java-reviewer.md` — ภาษาอื่น ๆ

### Build Error Resolution
- `build-error-resolver.md` — แก้ไข build errors ทั่วไป
- `pytorch-build-resolver.md`, `java-build-resolver.md`, `kotlin-build-resolver.md`
- `dart-build-resolver.md`, `swift-build-resolver.md`, `rust-build-resolver.md`

### Architecture & Design
- `architect.md` — ออกแบบสถาปัตยกรรมระบบ
- `code-architect.md` — ออกแบบโครงสร้างโค้ด
- `a11y-architect.md` — ออกแบบด้าน Accessibility

### Testing & Quality
- `tdd-guide.md` — แนะนำ Test-Driven Development
- `performance-optimizer.md` — วิเคราะห์และปรับปรุงประสิทธิภาพ
- `security-reviewer.md` — ตรวจสอบความปลอดภัย

### Utilities
- `planner.md` — วางแผนการ implement
- `code-explorer.md` — สำรวจและทำความเข้าใจ codebase
- `doc-updater.md` — อัปเดตเอกสาร
- `chief-of-staff.md` — ประสานงานและจัดการงานหลายชิ้น

## การใช้งาน

Claude Code จะเลือก agent ที่เหมาะสมอัตโนมัติตาม context ของงาน หรือผู้ใช้สามารถระบุ agent โดยตรงผ่าน `/` commands
