# config/

โฟลเดอร์นี้เก็บ **project stack mappings** — ข้อมูลที่ใช้ระบุชนิดของ tech stack และ map ไปยัง rules/agents ที่เหมาะสม

## ภาพรวม

เมื่อ Claude Code เริ่มทำงานในโปรเจกต์ ระบบจะตรวจจับ tech stack อัตโนมัติและโหลด rules, agents, และ skills ที่เหมาะสมโดยอ้างอิงจากข้อมูลใน `config/`

## ไฟล์

### project-stack-mappings.json

กำหนด mapping ระหว่าง tech stack และ components ที่ควรโหลด:

```json
{
  "typescript": {
    "rules": ["rules/typescript/"],
    "agents": ["typescript-reviewer.md"],
    "skills": ["angular-developer/"]
  },
  "python": {
    "rules": ["rules/python/"],
    "agents": ["python-reviewer.md"],
    "skills": ["django-patterns/"]
  }
}
```

## ความสัมพันธ์กับ Scripts

`scripts/lib/project-detect.js` ใช้ข้อมูลนี้เพื่อ:
1. ตรวจจับชนิด project จากไฟล์ที่มีอยู่ (package.json, requirements.txt, Cargo.toml ฯลฯ)
2. Map stack ที่ตรวจพบไปยัง components ใน `config/project-stack-mappings.json`
3. โหลด rules และ agents ที่เหมาะสมสำหรับ session นั้น
