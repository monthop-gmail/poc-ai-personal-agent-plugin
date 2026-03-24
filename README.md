# Personal Agent — Claude Code Plugin

Plugin ที่เปลี่ยน [Claude Code](https://claude.com/claude-code) ให้เป็น **ผู้ช่วยส่วนตัว** — จัดการโน้ต, TODO, ค้นคว้า, เช็คระบบ, จำข้อมูลข้ามเซสชัน

## Install

ใน Claude Code พิมพ์:

```
/plugin marketplace add monthop-gmail/poc-ai-personal-agent-plugin
/plugin install personal-agent@monthop-tools
```

เสร็จ!

## Commands

| คำสั่ง | ใช้ทำอะไร |
|--------|----------|
| `/personal-agent:daily-summary` | สรุปสถานะระบบประจำวัน |
| `/personal-agent:check-services` | เช็ค Docker, CPU, memory, disk, network |
| `/personal-agent:research [หัวข้อ]` | ค้นคว้าข้อมูลจากเว็บ |
| `/personal-agent:note [add/find/read]` | จัดการโน้ตส่วนตัว |
| `/personal-agent:todo [add/done/list]` | จัดการ TODO list |
| `/personal-agent:quick-task [อะไรก็ได้]` | งานด่วนเบ็ดเตล็ด |

## Features

- **6 Skills** — ใช้งานได้ทันทีจาก Claude Code ทุก project
- **MCP Memory** — จำข้อมูลข้ามเซสชันผ่าน Knowledge Graph
- **Plugin Format** — ติดตั้ง/ถอนผ่าน `/plugin` command มาตรฐาน
- **Namespace** — skills อยู่ใน `personal-agent:` ไม่ชนกับ plugin อื่น

## Structure

```
.claude-plugin/
├── plugin.json              ← plugin metadata
└── marketplace.json         ← marketplace catalog

skills/
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
