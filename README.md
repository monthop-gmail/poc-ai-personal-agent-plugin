# Personal Agent — Claude Code Plugin

Plugin ที่เปลี่ยน [Claude Code](https://claude.com/claude-code) ให้เป็น **ผู้ช่วยส่วนตัว** — จัดการโน้ต, TODO, ค้นคว้า, เช็คระบบ, จำข้อมูลข้ามเซสชัน

## Install

ใน Claude Code พิมพ์:

```
/plugin marketplace add monthop-gmail/poc-ai-personal-agent-plugin
/plugin install personal-agent@monthop-tools
```

จากนั้นสร้างไฟล์ `CLAUDE.md` ในโฟลเดอร์ที่จะใช้งาน เพื่อกำหนดให้ Claude เป็นผู้ช่วยส่วนตัว:

```markdown
# ผู้ช่วยส่วนตัว (Personal Agent)

คุณคือ AI ผู้ช่วยส่วนตัว ช่วยเจ้าของในเรื่องงานประจำวัน, ค้นคว้าข้อมูล, เขียนโค้ด และเพิ่มประสิทธิภาพการทำงานทั่วไป

## บุคลิก
- ตอบภาษาเดียวกับที่ผู้ใช้พูด (ค่าเริ่มต้น: ภาษาไทย)
- กระชับ ตรงประเด็น
- กระตือรือร้น — แนะนำขั้นตอนถัดไปเมื่อเหมาะสม
- เป็นมิตร แต่มีประสิทธิภาพ

## แนวทางการทำงาน
- ยืนยันกับผู้ใช้ก่อนเสมอ หากจะลบไฟล์หรือเขียนทับข้อมูล
- เมื่อค้นคว้าข้อมูล ให้อ้างอิงแหล่งที่มา
- สำหรับงานหลายขั้นตอน ให้วางแผนก่อน แล้วค่อยลงมือทำ
- ใช้ระบบ memory เพื่อจำข้อมูลสำคัญข้ามเซสชัน
- ถ้าไม่แน่ใจ ให้ถามแทนการเดา

## เมื่อเริ่มเซสชันใหม่
ให้รัน /personal-agent:session-start โดยอัตโนมัติ
```

> ปรับบุคลิกและภาษาได้ตามต้องการ — นี่คือตัวอย่างเริ่มต้น

## Commands

| คำสั่ง | ใช้ทำอะไร |
|--------|----------|
| `/personal-agent:session-start` | เริ่มเซสชัน — ทักทาย สรุปสถานะ เช็คงานค้าง |
| `/personal-agent:daily-summary` | สรุปสถานะระบบประจำวัน |
| `/personal-agent:check-services` | เช็ค Docker, CPU, memory, disk, network |
| `/personal-agent:research [หัวข้อ]` | ค้นคว้าข้อมูลจากเว็บ |
| `/personal-agent:note [add/find/read]` | จัดการโน้ตส่วนตัว |
| `/personal-agent:todo [add/done/list]` | จัดการ TODO list |
| `/personal-agent:quick-task [อะไรก็ได้]` | งานด่วนเบ็ดเตล็ด |

## Features

- **Auto Memory** — จำข้อมูลสำคัญข้ามเซสชันโดยอัตโนมัติ (markdown + Knowledge Graph)
- **On Session Start** — เปิดมาก็สรุปสถานะ + งานค้างให้เลย
- **Folder Rules** — ไฟล์ไม่มั่วเปะปะ agent รู้ว่าอะไรวางที่ไหน
- **MCP Memory** — จำความสัมพันธ์ระหว่างคน/โปรเจค/เทคโนโลยี
- **9 Skills** — 7 user-invocable + 2 auto-invoked
- **Plugin Format** — ติดตั้ง/ถอนผ่าน `/plugin` command มาตรฐาน

## Structure

```
.claude-plugin/
├── plugin.json              ← plugin metadata
└── marketplace.json         ← marketplace catalog

skills/
├── session-start/SKILL.md   ← เริ่มเซสชัน (user-invocable)
├── auto-memory/SKILL.md     ← บันทึก memory อัตโนมัติ (auto-invoked)
├── folder-rules/SKILL.md    ← กฎจัดการไฟล์ (auto-invoked)
├── daily-summary/SKILL.md
├── check-services/SKILL.md
├── note/SKILL.md
├── todo/SKILL.md
├── research/SKILL.md
└── quick-task/SKILL.md

.mcp.json                    ← MCP memory server
```

## Uninstall

```
/plugin uninstall personal-agent@monthop-tools
```

## Related

- [poc-ai-personal-agent](https://github.com/monthop-gmail/poc-ai-personal-agent) — Docker version (standalone)

## License

MIT
