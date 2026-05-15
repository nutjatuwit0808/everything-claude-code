# assets/

โฟลเดอร์นี้เก็บ **static assets** ทั้งหมดของโปรเจกต์ — รูปภาพ, icons, และสื่อต่าง ๆ ที่ใช้ใน documentation และ UI

## ภาพรวม

Assets ใน folder นี้ถูกอ้างอิงจาก README.md และเอกสารอื่น ๆ ของโปรเจกต์ รวมถึงใช้ใน ECC Dashboard GUI

## โครงสร้าง

```
assets/
├── hero.png              — รูปหลักของโปรเจกต์ (ใช้ใน README.md)
└── images/
    ├── guides/           — รูปสำหรับคู่มือ (shorthand, longform, security guides)
    └── security/         — รูปสำหรับ security documentation
```

## การใช้งาน

Assets ถูกอ้างอิงด้วย relative path จาก markdown files:

```markdown
![Hero](assets/hero.png)
![Guide](assets/images/guides/shorthand-guide.png)
```

## หมายเหตุ

- ใช้ไฟล์รูปแบบ PNG/JPG สำหรับรูปภาพทั่วไป
- รูปภาพควรมีขนาดเหมาะสมกับการแสดงผลบน GitHub
- ห้ามเก็บไฟล์ binary ขนาดใหญ่ที่ไม่ใช่ documentation assets
