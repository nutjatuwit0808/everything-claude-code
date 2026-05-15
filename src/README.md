# src/

โฟลเดอร์นี้เก็บ **Python source code** ของ ECC core — ระบบ LLM pipeline และ CLI สำหรับสร้างและรัน AI workflows

## ภาพรวม

`src/` เป็น Python package (`ecc`) ที่ทำหน้าที่เป็น core engine สำหรับ:
- เชื่อมต่อกับ LLM providers (Claude, OpenAI, Gemini ฯลฯ)
- สร้างและรัน prompt pipelines
- จัดการ tools ที่ AI สามารถใช้ได้
- CLI interface สำหรับรัน workflows

## โครงสร้าง

```
src/
└── llm/
    ├── __init__.py
    ├── __main__.py     — Entry point: python -m src.llm
    ├── cli/            — CLI commands และ argument parsing
    ├── core/           — Business logic หลัก
    ├── prompt/         — Prompt building และ template management
    ├── providers/      — LLM provider adapters (Claude, OpenAI ฯลฯ)
    └── tools/          — Tool definitions ที่ AI ใช้ได้
```

## Components

### providers/
Adapters สำหรับ LLM providers ต่าง ๆ:
- `claude` — Anthropic Claude API
- `openai` — OpenAI API  
- รองรับ provider ใหม่ได้โดยสร้าง adapter ที่ implement interface เดียวกัน

### prompt/
ระบบจัดการ prompts:
- Template rendering
- Context injection
- Prompt caching support

### tools/
Tool definitions ที่ AI สามารถเรียกใช้ได้ในระหว่าง pipeline รวมถึง:
- File operations
- Search
- Code execution

### cli/
Command-line interface สำหรับรัน ECC จาก terminal

## การรัน

```bash
python -m src.llm --help
```

## Tests

Python tests อยู่ใน `tests/`:
```bash
pytest tests/test_builder.py
pytest tests/test_executor.py
pytest tests/test_provider_tools.py
pytest tests/test_templates.py
```

## ความสัมพันธ์กับ ecc2/

`src/` คือ Python implementation ที่ใช้งานอยู่ในปัจจุบัน ส่วน `ecc2/` คือ Rust control-plane prototype (alpha) ที่อยู่ระหว่างพัฒนาเพื่อแทนที่ในอนาคต
