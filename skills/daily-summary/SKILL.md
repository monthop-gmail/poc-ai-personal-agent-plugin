---
name: daily-summary
description: สรุปสถานะระบบประจำวัน — git activity, Docker, disk, งานค้าง
user-invocable: true
---

สรุปสถานะประจำวัน:

1. เช็ค git activity ใน repos ที่อยู่ใน home directory (commit ล่าสุดของวันนี้)
2. เช็ค Docker containers ที่รันอยู่และสถานะ (ถ้ามี docker)
3. เช็คพื้นที่ดิสก์และทรัพยากรระบบ
4. เช็คว่ามี task หรือ TODO ค้างอยู่ไหม (ดูจาก ~/personal-agent/notes/TODO.md)
5. สรุปทั้งหมดในรูปแบบที่อ่านง่าย กระชับ เป็นภาษาไทย
