---
name: folder-rules
description: กฎจัดการไฟล์และโฟลเดอร์ — กำหนดว่าไฟล์แต่ละประเภทต้องวางที่ไหนใน ~/personal-agent/ เพื่อไม่ให้ไฟล์มั่วเปะปะ
user-invocable: false
---

# Folder Rules — กฎการจัดการไฟล์

เมื่อสร้างหรือจัดการไฟล์ที่เกี่ยวกับ personal agent ให้ปฏิบัติตามกฎเหล่านี้:

## โครงสร้างโฟลเดอร์ ~/personal-agent/

```
~/personal-agent/
├── notes/                  # 📝 โน้ตส่วนตัว
├── research/               # 🔍 ผลการค้นคว้า
├── downloads/              # 📥 ไฟล์ที่ดาวน์โหลด หรือไฟล์ชั่วคราว
└── memory.jsonl            # 🧠 Knowledge Graph Memory (สร้างอัตโนมัติ)
```

## กฎ:
- **ห้ามสร้างไฟล์ตรง ~/personal-agent/ โดยตรง** — ต้องวางในโฟลเดอร์ที่เหมาะสม
- **โน้ต** → สร้างใน `~/personal-agent/notes/` เสมอ
- **ผลค้นคว้า** → บันทึกใน `~/personal-agent/research/` เสมอ
- **ไฟล์ดาวน์โหลด/ชั่วคราว** → วางใน `~/personal-agent/downloads/`
- ถ้าไม่แน่ใจว่าควรวางที่ไหน → **ถามผู้ใช้ก่อน**

## เมื่อ skill อื่นสร้างไฟล์:
- `/personal-agent:note` → สร้างใน `~/personal-agent/notes/`
- `/personal-agent:research` → บันทึกใน `~/personal-agent/research/`
- `/personal-agent:todo` → ใช้ไฟล์ `~/personal-agent/notes/TODO.md`

## หลักการ:
- ยืนยันกับผู้ใช้ก่อนเสมอ หากจะลบไฟล์หรือเขียนทับข้อมูล
- สร้างโฟลเดอร์อัตโนมัติถ้ายังไม่มี (mkdir -p)
- ไฟล์ต้องมีชื่อที่สื่อความหมาย ไม่ใช้ชื่อแบบ temp1.txt, untitled.md
