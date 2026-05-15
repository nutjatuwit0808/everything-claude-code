# skills/

โฟลเดอร์นี้เก็บ **Skill definitions** — องค์ความรู้และ workflow เฉพาะโดเมนที่ Claude Code ใช้เป็นแนวทางในการทำงาน

## ภาพรวม

Skill คือไฟล์ Markdown ที่อธิบาย "วิธีทำงาน" ในบริบทเฉพาะ เช่น การออกแบบ API, การเขียน tests, หรือการจัดการ database migration เมื่อผู้ใช้เรียก skill ผ่าน `/skill-name` Claude Code จะโหลด context นั้นเข้ามาเป็น guideline

## ความแตกต่างจาก Agents

| | Skills | Agents |
|--|--------|--------|
| บทบาท | ให้ความรู้/แนวทาง | ทำงานแทนผู้ใช้ |
| รูปแบบ | How-to guide | Prompt + tools |
| การเรียกใช้ | `/skill-name` | delegate โดย Claude |

## โครงสร้าง Skill (229+ skills)

### Engineering Patterns
- `agentic-engineering/` — การพัฒนาระบบ agentic
- `api-design/` — ออกแบบ REST/GraphQL API
- `ai-first-engineering/` — การพัฒนาแบบ AI-first
- `autonomous-loops/` — การวนซ้ำอัตโนมัติ

### Language & Framework
- `angular-developer/` — Angular patterns
- `android-clean-architecture/` — Android Clean Architecture
- `api-connector-builder/` — สร้าง API connectors

### Testing & Quality
- `agent-eval/` — ประเมินประสิทธิภาพ agent
- `ai-regression-testing/` — Regression testing สำหรับ AI systems
- `agent-sort/` — จัดเรียงและจัดการ agents

### Agent Operations
- `agent-architecture-audit/` — ตรวจสอบสถาปัตยกรรม
- `agent-introspection-debugging/` — debug agent behavior
- `agent-harness-construction/` — สร้าง harness สำหรับ agents

## Skill Placement Policy

- **skills/** — Skills ที่ผ่านการ curate และอยู่ใน source control
- **~/.claude/skills/** — Skills ที่ AI สร้างขึ้น (`/skill-create`) หรือ import จากภายนอก

ดูรายละเอียดเพิ่มเติมที่ `docs/SKILL-PLACEMENT-POLICY.md`

## รูปแบบไฟล์

```markdown
# Skill Name

## When to Use
อธิบายเมื่อไรควรใช้ skill นี้

## How It Works
อธิบายขั้นตอนการทำงาน

## Examples
ตัวอย่างการใช้งาน
```
