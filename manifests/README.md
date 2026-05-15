# manifests/

โฟลเดอร์นี้เก็บ **Install manifest files** — ไฟล์ที่กำหนดว่า components, modules, และ profiles ใดที่สามารถ install ได้ผ่าน ECC installer

## ภาพรวม

Manifest-driven install pipeline ช่วยให้ผู้ใช้เลือกติดตั้งเฉพาะส่วนที่ต้องการได้ แทนที่จะต้องติดตั้งทุกอย่างพร้อมกัน

## ไฟล์

### install-profiles.json

กำหนด install profiles สำเร็จรูป 3 ระดับ:

| Profile | คำอธิบาย |
|---------|---------|
| `minimal` | เฉพาะ components จำเป็นพื้นฐาน |
| `standard` | components หลักที่ใช้บ่อย |
| `full` | ทุกอย่างรวมถึง experimental features (แนะนำ) |

### install-components.json

รายการ components ทั้งหมดที่ ECC มีให้ติดตั้ง เช่น:
- agents
- skills
- commands
- hooks
- rules
- mcp-configs

### install-modules.json

รายการ modules ย่อยภายใน components แต่ละตัว ช่วยให้ install เฉพาะส่วนที่ต้องการได้ เช่น เฉพาะ Python rules โดยไม่ต้อง install Java rules

## วิธีทำงาน

```
install-profiles.json
        ↓ เลือก profile
install-components.json
        ↓ เลือก components
install-modules.json
        ↓ map ไปยัง files
scripts/install-plan.js    — สร้าง install plan
        ↓
scripts/install-apply.js   — ดำเนินการ install
        ↓
State tracked in scripts/lib/state-store/
```

## การอ้างอิง

- Schema ของไฟล์เหล่านี้อยู่ใน `schemas/install-*.schema.json`
- State ของ installation ปัจจุบันถูกเก็บใน SQLite ผ่าน `scripts/lib/state-store/`
