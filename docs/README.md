# docs/

โฟลเดอร์นี้เก็บ **เอกสารประกอบ (documentation)** ทั้งหมดของ ECC ครอบคลุมตั้งแต่คู่มือการตั้งค่า สถาปัตยกรรม ไปจนถึงการแปลภาษา

## โครงสร้าง

```
docs/
├── pt-BR/          — คู่มือภาษาโปรตุเกส (บราซิล)
├── zh-TW/          — คู่มือภาษาจีนตัวเต็ม
├── ja-JP/          — คู่มือภาษาญี่ปุ่น
├── ko-KR/          — คู่มือภาษาเกาหลี
├── tr/             — คู่มือภาษาตุรกี
├── ru/             — คู่มือภาษารัสเซีย
├── vi-VN/          — คู่มือภาษาเวียดนาม
├── th/             — คู่มือภาษาไทย
├── architecture/   — เอกสารสถาปัตยกรรม
├── releases/       — Release notes
└── *.md            — เอกสารเฉพาะเรื่อง
```

## เอกสารสำคัญ

### Setup & Configuration
- `HERMES-SETUP.md` — คู่มือตั้งค่า Hermes operator workflow
- `SKILL-PLACEMENT-POLICY.md` — นโยบายการวาง skills ใน repo

### Architecture
- `architecture/cross-harness.md` — สถาปัตยกรรม cross-harness (Claude Code, Cursor, Codex ฯลฯ)

### Release Notes
- `releases/2.0.0-rc.1/release-notes.md` — release notes ล่าสุด

## การแปลภาษา (i18n)

เอกสารแต่ละภาษาอยู่ใน subfolder ของตัวเอง และควรเป็น translation ของ `README.md` หลัก:

| โฟลเดอร์ | ภาษา |
|---------|------|
| `pt-BR/` | Português (Brasil) |
| `zh-TW/` | 繁體中文 |
| `ja-JP/` | 日本語 |
| `ko-KR/` | 한국어 |
| `tr/` | Türkçe |
| `ru/` | Русский |
| `vi-VN/` | Tiếng Việt |
| `th/` | ภาษาไทย |

## การเพิ่มภาษาใหม่

1. สร้างโฟลเดอร์ใหม่ตาม locale code (เช่น `docs/de/`)
2. แปล `README.md` และเอกสารสำคัญ
3. เพิ่มลิงก์ใน `README.md` หลักบรรทัดแรก และใน `<div align="center">` language picker
