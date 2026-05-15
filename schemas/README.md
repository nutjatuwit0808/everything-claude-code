# schemas/

โฟลเดอร์นี้เก็บ **JSON Schema definitions** สำหรับตรวจสอบความถูกต้องของไฟล์ configuration ต่าง ๆ ใน ECC

## ภาพรวม

Schemas ใช้ JSON Schema specification เพื่อ validate โครงสร้างของไฟล์ config ทำให้มั่นใจได้ว่าข้อมูลที่ใส่เข้ามาถูกต้องตามรูปแบบที่กำหนด

## ไฟล์ Schema

| ไฟล์ | ใช้ validate |
|------|-------------|
| `ecc-install-config.schema.json` | การตั้งค่า install ของ ECC |
| `hooks.schema.json` | โครงสร้างของ hook definitions |
| `install-components.schema.json` | components ที่สามารถ install ได้ |
| `install-modules.schema.json` | modules ใน install pipeline |
| `install-profiles.schema.json` | install profiles (minimal/standard/full) |
| `install-state.schema.json` | state ของ installation ปัจจุบัน |
| `package-manager.schema.json` | การตั้งค่า package manager |
| `plugin.schema.json` | โครงสร้างของ plugin manifest |
| `provenance.schema.json` | ข้อมูล provenance ของ artifacts |
| `state-store.schema.json` | โครงสร้างของ SQLite state store |

## การใช้งาน

Schemas ถูกใช้โดย:
1. **Install pipeline** — `scripts/install-plan.js` และ `scripts/install-apply.js` ใช้ validate manifest files
2. **CI/CD** — tests ตรวจสอบว่า config files ตรงตาม schema
3. **Editor support** — VS Code และ editors อื่น ๆ ใช้ schemas เพื่อแสดง autocomplete และ validation

## ตัวอย่าง

```json
// hooks.schema.json ครอบคลุมโครงสร้างแบบนี้
{
  "hooks": [
    {
      "matcher": "PreToolUse",
      "hooks": [
        {
          "type": "command",
          "command": "node scripts/hooks/pre-bash-dispatcher.js"
        }
      ]
    }
  ]
}
```
