# examples/

โฟลเดอร์นี้เก็บ **ตัวอย่างไฟล์ CLAUDE.md** และโปรเจกต์ตัวอย่างสำหรับ tech stacks ต่าง ๆ เพื่อใช้เป็น template เมื่อเริ่มโปรเจกต์ใหม่

## ภาพรวม

ไฟล์ CLAUDE.md บอก Claude Code ว่าโปรเจกต์นั้นทำงานอย่างไร ใช้ stack อะไร และมี conventions อะไรบ้าง ตัวอย่างใน folder นี้ช่วยให้ copy-paste และปรับแต่งได้ทันที

## ไฟล์ตัวอย่าง

### CLAUDE.md Templates ตาม Stack

| ไฟล์ | Tech Stack |
|------|------------|
| `saas-nextjs-CLAUDE.md` | Next.js SaaS application |
| `django-api-CLAUDE.md` | Django REST API |
| `go-microservice-CLAUDE.md` | Go microservices |
| `rust-api-CLAUDE.md` | Rust API server |
| `laravel-api-CLAUDE.md` | Laravel PHP API |
| `harmonyos-app-CLAUDE.md` | HarmonyOS mobile app |

### โปรเจกต์ตัวอย่างสำหรับ Harness

| โฟลเดอร์ | คำอธิบาย |
|---------|---------|
| `gan-harness/` | ตัวอย่างการสร้าง GAN (Generative AI) harness |
| `evaluator-rag-prototype/` | Prototype ระบบ RAG (Retrieval-Augmented Generation) |

### ไฟล์อื่น ๆ

- `hud-status-contract.json` — Contract specification สำหรับ HUD status display

## วิธีใช้

1. เลือก template ที่ตรงกับ stack ของโปรเจกต์
2. Copy ไปที่ root ของโปรเจกต์เป็น `CLAUDE.md`
3. แก้ไขให้ตรงกับ conventions และ requirements ของโปรเจกต์
4. Claude Code จะโหลดไฟล์นี้อัตโนมัติเมื่อเปิด session ในโปรเจกต์นั้น
