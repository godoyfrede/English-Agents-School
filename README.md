# English Agents School

Multi-agent system for personalized English learning. Framework-agnostic and model-agnostic — run with Claude, GPT-4, Llama, Mistral, or any LLM. Use with LangChain, CrewAI, AutoGen, Ollama, or any CLI.

Developed by **Fred Godoy** · v1.0.0

---

## Two Distributions

| | Claude Cowork Plugin | Open Source Spec |
|---|---|---|
| **Location** | `fred-english-school/` | `open-source/` |
| **Format** | `.plugin` file | YAML + Markdown |
| **Works with** | Claude Cowork only | Any LLM / Any framework |
| **Installation** | Import `.plugin` in Cowork | Paste prompts, parse YAML |
| **README** | [Plugin README](fred-english-school/README.md) | [OSS README](open-source/README.md) |

---

## The System

### 3 Agents

| Agent | Role |
|-------|------|
| **Principal** | Orchestrator — entry point, routes all requests |
| **Supervisor** | Memory — tracks scores, manages CEFR levels |
| **Professor** | Teacher — conducts CLT-based English lessons |

### 6 Skills

| Skill | Purpose |
|-------|---------|
| `placement-test` | Initial CEFR assessment (A1–C2) |
| `progress-test` | Monthly evaluation + level decision |
| `conversation` | Role-play, storytelling, opinion exchange |
| `writing-coach` | Writing with V1 → feedback → V2 cycle |
| `vocabulary-reading` | Context vocabulary + reading + spaced repetition |
| `daily-activities` | Weekly homework plan with real, current content |

---

## Repository Structure

```
English-Agents-School/
├── fred-english-school/       ← Claude Cowork Plugin
│   ├── .claude-plugin/
│   ├── agents/
│   ├── skills/
│   ├── README.md
│   └── LICENSE
│
├── open-source/               ← Framework-Agnostic Specification
│   ├── agents/                  YAML agent specs
│   ├── skills/                  YAML skill specs
│   ├── prompts/                 System prompts (Markdown)
│   ├── schemas/                 JSON Schema for state
│   ├── implementations/         OpenAI, Anthropic, Ollama guides
│   └── docs/                    Architecture, methodology, how-to
│
└── README.md
```

---

## Quick Start

### Claude Cowork
1. Download `fred-english-school.plugin` from [Releases](../../releases)
2. Import in Claude Cowork
3. Say: *"Quero começar a aprender inglês"*

### Any LLM (Python)
```python
from openai import OpenAI
from pathlib import Path

client = OpenAI()  # or Anthropic, Ollama, Gemini, etc.
system = Path("open-source/prompts/professor.md").read_text()

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": system},
        {"role": "user", "content": "Quero praticar conversação"}
    ]
)
print(response.choices[0].message.content)
```

### Ollama (local, no API key)
```bash
ollama run llama3.1:8b "$(cat open-source/prompts/professor.md)

USER: Quero uma aula de conversação"
```

---

## Methodology

- **CLT** — Communicative Language Teaching: use the language, don't memorize rules
- **CEFR** — 6 international levels (A1→C2) for objective placement and progression
- **SRS** — Spaced repetition for vocabulary retention (3 → 7 → 21 → 60 days)
- **Bilingual adaptive** — Portuguese for guidance, English for exercises

---

## License

[MIT License](fred-english-school/LICENSE) — Fred Godoy, 2026
