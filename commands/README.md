# commands/

โฟลเดอร์นี้เก็บ **Slash commands** — คำสั่งที่ผู้ใช้เรียกใช้โดยตรงในรูปแบบ `/command-name` ภายใน Claude Code

## ภาพรวม

Command แต่ละตัวคือไฟล์ Markdown ที่อธิบาย workflow ที่จะทำงานเมื่อผู้ใช้เรียกคำสั่งนั้น Claude Code จะอ่านไฟล์นี้และดำเนินการตาม instructions ที่กำหนดไว้

## รูปแบบไฟล์

```markdown
---
description: คำอธิบายสั้น ๆ ของคำสั่งนี้
---

เนื้อหา prompt / workflow instructions
```

## คำสั่งทั้งหมด

### Development Workflow
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/plan.md` | วางแผนการ implement feature |
| `/feature-dev.md` | workflow พัฒนา feature |
| `/build-fix.md` | แก้ไข build errors |
| `/refactor-clean.md` | refactor และทำความสะอาดโค้ด |
| `/checkpoint.md` | บันทึก checkpoint ของงาน |

### Testing
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/go-test.md`, `/rust-test.md` | รัน tests ตามภาษา |
| `/flutter-test.md`, `/kotlin-test.md` | รัน tests mobile |
| `/test-coverage.md` | ตรวจสอบ test coverage |

### Code Review
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/code-review.md` | ตรวจสอบคุณภาพโค้ดทั่วไป |
| `/go-review.md`, `/python-review.md` | review ตามภาษา |
| `/fastapi-review.md`, `/flutter-review.md` | review ตาม framework |
| `/review-pr.md` | review Pull Request |

### Multi-Agent Orchestration
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/multi-plan.md` | วางแผนงานหลาย agents |
| `/multi-execute.md` | รัน agents พร้อมกัน |
| `/multi-backend.md` | จัดการ backend services |
| `/multi-frontend.md` | จัดการ frontend |
| `/multi-workflow.md` | workflow ซับซ้อนหลาย services |

### Session Management
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/save-session.md` | บันทึก session ปัจจุบัน |
| `/resume-session.md` | โหลด session ที่บันทึกไว้ |
| `/sessions.md` | ดูประวัติ sessions ทั้งหมด |
| `/aside.md` | บันทึก context สำคัญชั่วคราว |

### Skills & Learning
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/learn.md` | ดึงรูปแบบจาก session มาเป็น skill |
| `/skill-create.md` | สร้าง skill จาก git history |
| `/skill-health.md` | ตรวจสอบสุขภาพของ skills |
| `/evolve.md` | พัฒนา skill ที่มีอยู่ให้ดีขึ้น |

### Harness & Quality
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/harness-audit.md` | ตรวจสอบประสิทธิภาพ AI harness |
| `/quality-gate.md` | ตั้ง quality gate สำหรับโปรเจกต์ |
| `/model-route.md` | กำหนด routing สำหรับ models |
| `/cost-report.md` | รายงานค่าใช้จ่าย API |

### Security
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/security-scan.md` | สแกนความปลอดภัยด้วย AgentShield |
| `/instinct-status.md` | ตรวจสอบ security instincts |

### Process Management
| คำสั่ง | หน้าที่ |
|--------|---------|
| `/pm2.md` | จัดการ processes ด้วย PM2 |
| `/loop-start.md` | เริ่ม autonomous loop |
| `/loop-status.md` | ตรวจสอบสถานะ loop |
| `/auto-update.md` | อัปเดต ECC อัตโนมัติ |
