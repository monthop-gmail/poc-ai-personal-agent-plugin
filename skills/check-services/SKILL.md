---
name: check-services
description: เช็คสถานะบริการ — Docker containers, CPU, memory, disk, network
user-invocable: true
---

เช็คสถานะบริการทั้งหมดและรายงาน:

1. แสดง Docker containers ทั้งหมดด้วย `docker ps` — แสดงชื่อ, สถานะ, พอร์ต และ uptime (ถ้ามี docker)
2. เช็คทรัพยากรระบบ (CPU, หน่วยความจำ, ดิสก์)
3. เช็คการเชื่อมต่อเครือข่าย (ping google.com)
4. แจ้งเตือนหากมีบริการที่ล่มหรือมีปัญหา
5. รายงานในรูปแบบตาราง กระชับ เป็นภาษาไทย
