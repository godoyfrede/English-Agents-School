# English Agents School — Open Source Specification

A **framework-agnostic, model-agnostic** multi-agent system for personalized English learning. Build it with Claude, GPT-4, Llama, Mistral, Gemini, or any LLM. Run it with LangChain, CrewAI, AutoGen, Ollama, or any CLI.

Developed by **Fred Godoy** · v1.0.0

---

## What This Is

A complete specification for a team of 3 AI agents and 6 skills that work together to teach English:

- **Agents defined as YAML** — parse with any framework
- **System prompts as Markdown** — paste into any LLM
- **State as JSON** — store anywhere (file system, DB, cloud)
- **Skills as structured workflows** — implement in any language

---

## The Agent Team

| Agent | Role | System Prompt |
|-------|------|---------------|
| **Principal** | Orchestrator — routes every request to the right agent | `prompts/principal.md` |
| **Supervisor** | Memory — records scores, manages CEFR levels, generates reports | `prompts/supervisor.md` |
| **Professor** | Teacher — conducts CLT-based lessons, adapts to student level | `prompts/professor.md` |

---

## The Skills

| Skill | Purpose | Requires Web Search |
|-------|---------|:-------------------:|
| `placement-test` | Initial CEFR level assessment (A1–C2) | No |
| `progress-test` | Monthly progress check + level decision | No |
| `conversation` | CLT role-play, storytelling, opinion exchange | No |
| `writing-coach` | Writing exercises with V1→feedback→V2 cycle | No |
| `vocabulary-reading` | Vocabulary in context + reading + spaced repetition | No |
| `daily-activities` | Weekly homework plan with real, current content | **Yes** |

---

## Quick Start

### 1. Minimal — Paste a prompt

```bash
# Using any CLI — paste prompts/professor.md as system prompt
# Then send: "Quero uma aula de conversação"
```

### 2. Python — OpenAI-compatible

```python
from openai import OpenAI
from pathlib import Path

client = OpenAI()  # works with any OpenAI-compatible endpoint

system_prompt = Path("prompts/professor.md").read_text()

response = client.chat.completions.create(
    model="gpt-4o",       # or claude-3-5-sonnet, llama3.1, etc.
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "Quero praticar conversação hoje"}
    ]
)
print(response.choices[0].message.content)
```

### 3. Ollama — Local models

```bash
ollama run llama3.1:70b \
  "$(cat prompts/professor.md)

USER: Quero uma aula de escrita"
```

### 4. Claude Cowork Plugin

See the [`fred-english-school/`](../fred-english-school/) directory for the ready-to-install Cowork plugin.

---

## Repository Structure

```
open-source/
├── agents/                      # Agent specifications (YAML)
│   ├── principal.yaml           # Orchestrator
│   ├── supervisor.yaml          # Memory & progress manager
│   └── professor.yaml           # English teacher
│
├── skills/                      # Skill specifications (YAML)
│   ├── placement-test.yaml
│   ├── progress-test.yaml
│   ├── conversation.yaml
│   ├── writing-coach.yaml
│   ├── vocabulary-reading.yaml
│   └── daily-activities.yaml
│
├── prompts/                     # Ready-to-use system prompts (Markdown)
│   ├── principal.md
│   ├── supervisor.md
│   ├── professor.md
│   └── skills/
│       ├── placement-test.md
│       ├── progress-test.md
│       ├── conversation.md
│       ├── writing-coach.md
│       ├── vocabulary-reading.md
│       └── daily-activities.md
│
├── schemas/
│   └── progress.schema.json     # JSON Schema for student state
│
├── implementations/             # Reference implementations
│   ├── openai/README.md
│   ├── anthropic/README.md
│   └── ollama/README.md
│
└── docs/
    ├── ARCHITECTURE.md          # System design & agent communication
    ├── METHODOLOGY.md           # CLT, CEFR, SRS — educational approach
    └── HOW_TO_IMPLEMENT.md      # Integration guides for all frameworks
```

---

## Methodology

Built on three evidence-based approaches:

**CLT — Communicative Language Teaching**
Language is learned by using it, not by memorizing rules. Every session is a real communicative situation.

**CEFR — Common European Framework**
Six internationally recognized levels (A1→C2) provide objective criteria for placement and advancement.

**SRS — Spaced Repetition System**
Vocabulary is reviewed at increasing intervals (3 → 7 → 21 → 60 days) to maximize retention.

→ Full details: [`docs/METHODOLOGY.md`](docs/METHODOLOGY.md)

---

## Student State (progress.json)

All state is stored in a single JSON file. Every agent reads from it; only Supervisor and Skills write to it.

```json
{
  "student": "Fred",
  "current_level": "B1",
  "placement_date": "2026-04-25",
  "next_progress_test": "2026-05-25",
  "scores": {
    "placement": { "total": 48, "date": "2026-04-25" },
    "progress_tests": []
  },
  "skill_sessions": {
    "conversation": { "sessions": 3, "avg_score": 72 },
    "writing": { "sessions": 2, "avg_score": 68 },
    "vocabulary_reading": { "sessions": 4, "avg_score": 81 }
  }
}
```

→ Full schema: [`schemas/progress.schema.json`](schemas/progress.schema.json)

---

## Compatible Models

Works with any model that supports system prompts and tool use:

| Model | Provider |
|-------|----------|
| Claude 3.5 / 3.7 Sonnet | Anthropic |
| GPT-4o / GPT-4o-mini | OpenAI |
| Llama 3.1 70B+ | Meta (via Ollama) |
| Mistral Large | Mistral AI |
| Gemini 1.5 Pro / Flash | Google |

→ Implementation guides: [`docs/HOW_TO_IMPLEMENT.md`](docs/HOW_TO_IMPLEMENT.md)

---

## Compatible Frameworks

| Framework | Type |
|-----------|------|
| LangChain | Multi-agent orchestration |
| CrewAI | Role-based agents |
| AutoGen | Conversational multi-agent |
| Ollama | Local model runner |
| Any OpenAI-compatible API | Direct API calls |
| Claude Code / Cowork | Anthropic tools |

---

## License

[MIT License](../fred-english-school/LICENSE) — Fred Godoy, 2026

Free to use, modify, and distribute. Attribution appreciated.

---

*English Agents School v1.0.0 — Open Source Specification*
*Built by Fred Godoy*
