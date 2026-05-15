# contexts/

โฟลเดอร์นี้เก็บ **Context documents** — เอกสารที่ให้ข้อมูล background เฉพาะโดเมนสำหรับการทำงานแต่ละประเภท

## ภาพรวม

Context files ทำงานคล้าย "briefing document" ที่ Claude อ่านก่อนเริ่มทำงาน ช่วยให้ AI มี background knowledge ที่จำเป็นโดยไม่ต้องอธิบายซ้ำทุกครั้ง

## ไฟล์

| ไฟล์ | หน้าที่ |
|------|---------|
| `dev.md` | Context สำหรับงานพัฒนาทั่วไป — conventions, patterns, workflows |
| `research.md` | Context สำหรับงานวิจัย — วิธีค้นหา, evaluate, และสรุปข้อมูล |
| `review.md` | Context สำหรับการ code review — มาตรฐาน, checklist, สิ่งที่ต้องดู |

## ความแตกต่างจาก Rules

| | Contexts | Rules |
|--|---------|-------|
| ลักษณะ | Background knowledge | กฎที่ต้องปฏิบัติตาม |
| ขอบเขต | เฉพาะ task type | ทุกงาน |
| การโหลด | โหลดตามบริบทของงาน | โหลดตลอด session |

## การใช้งาน

Contexts จะถูกโหลดโดย commands หรือ agents ที่เกี่ยวข้องโดยอัตโนมัติ หรือผู้ใช้สามารถ reference ได้โดยตรงในคำสั่ง
