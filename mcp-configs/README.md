# mcp-configs/

โฟลเดอร์นี้เก็บ **การตั้งค่า MCP (Model Context Protocol) servers** สำหรับเชื่อมต่อ Claude Code กับบริการภายนอก

## ภาพรวม

MCP (Model Context Protocol) เป็น protocol มาตรฐานที่ช่วยให้ Claude Code เชื่อมต่อกับ external tools และ data sources ได้ โดยไม่ต้องเขียน integration code เอง

## ไฟล์

### mcp-servers.json

ไฟล์หลักที่กำหนด MCP servers ทั้งหมดที่ ECC ใช้:

```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["@package/mcp-server"],
      "env": {
        "API_KEY": "${ENV_VAR}"
      }
    }
  }
}
```

## ประเภท MCP Servers ที่รองรับ

### Development Tools
- **GitHub** — อ่าน/เขียน issues, PRs, repositories
- **IDE** — เชื่อมต่อกับ VS Code, JetBrains

### Data & Search
- **Context7** — ค้นหาและอ่านเอกสาร library แบบ real-time
- **Exa** — web search และ fetch
- **Google Drive** — อ่าน/เขียนไฟล์ใน Google Drive

### Memory & State
- **Memory** — จัดเก็บและค้นหา entities, relations, observations

### AI Tools
- **Sequential Thinking** — วิเคราะห์ปัญหาแบบ step-by-step

## การติดตั้ง

MCP configs จะถูกคัดลอกไปยัง `~/.claude/` เมื่อรัน ECC installer:

```bash
./install.sh
# หรือ
node scripts/install-apply.js
```

## การอ้างอิง

- ดูรายละเอียด MCP servers ที่ใช้งานได้จริงใน Claude Code settings
- สามารถเพิ่ม custom MCP server ได้โดยแก้ไข `mcp-servers.json` และ merge กับ config ที่มีอยู่
