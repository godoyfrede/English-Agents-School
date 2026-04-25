# Architecture — English Agents School

## Overview

English Agents School is a **multi-agent system** for personalized English learning. It is designed as a framework-agnostic, model-agnostic specification: the same agent definitions can run on Claude, GPT-4, Llama, Mistral, Gemini, or any model that supports system prompts and tool use.

---

## System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        STUDENT (User)                           │
└────────────────────────────┬────────────────────────────────────┘
                             │ natural language input
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    PRINCIPAL (Orchestrator)                      │
│                                                                  │
│  • Reads progress.json                                           │
│  • Interprets student intent                                     │
│  • Routes to the correct agent or skill                          │
│  • Never teaches directly                                        │
└──────────┬──────────────┬──────────────┬────────────────────────┘
           │              │              │
           ▼              ▼              ▼
┌──────────────┐  ┌──────────────┐  ┌──────────────────────────┐
│  SUPERVISOR  │  │  PROFESSOR   │  │  SKILLS (stateless)      │
│              │  │              │  │                          │
│ • Memory     │  │ • CLT method │  │ • placement-test         │
│ • Scores     │  │ • Adapts to  │  │ • progress-test          │
│ • Level mgmt │  │   CEFR level │  │ • conversation           │
│ • Reports    │  │ • Feedback   │  │ • writing-coach          │
│              │  │              │  │ • vocabulary-reading     │
│ Writes to:   │  │ Reads from:  │  │ • daily-activities       │
│ progress.json│  │ progress.json│  │                          │
└──────────────┘  └──────────────┘  └──────────────────────────┘
           │              │              │
           └──────────────┴──────────────┘
                          │
                          ▼
              ┌────────────────────┐
              │   progress.json    │
              │  (state storage)   │
              │                    │
              │  • current_level   │
              │  • scores          │
              │  • session history │
              │  • level_history   │
              │  • next_test_date  │
              └────────────────────┘
```

---

## Agent Responsibilities

### Principal (Orchestrator)
- **Single point of entry** for all student interactions
- Reads `progress.json` at session start
- Uses **routing rules** to decide who handles each request
- Does NOT hold educational content — only routing logic
- Manages session lifecycle (greeting, suggestions, closings)

### Supervisor (Memory Manager)
- **Sole writer** of level advancement decisions
- Applies the **advancement ruleset** consistently
- Records all scored sessions to `progress.json`
- Generates progress reports on demand
- Never interacts with educational content

### Professor (Teacher)
- **Sole agent that teaches**
- Adapts language, pace, and complexity to CEFR level
- Conducts three session types: conversation, writing, vocabulary/reading
- Applies CLT methodology in every session
- Sends session scores to Supervisor after each session

### Skills (Stateless Functions)
- Contain **complete workflows** for specific tasks
- Can be invoked by Principal directly (without Professor)
- Each skill reads from and writes to `progress.json`
- `daily-activities` requires `web_search` to find current content

---

## State Management

All state is stored in a single JSON file: `progress.json`.

### File location
By default: `./progress.json` in the current working directory.
Can be configured per implementation.

### Schema
Full JSON Schema at: `schemas/progress.schema.json`

### State update protocol
1. **Only Supervisor and Skills** write to `progress.json`
2. **Principal and Professor** only read from it
3. All writes are **additive** — never destructive
4. Level regressions are recorded in `level_history`, not overwritten

---

## CEFR Level Progression

```
A1 ──→ A2 ──→ B1 ──→ B2 ──→ C1 ──→ C2
 ↑             ↑             ↑
 └─────────────┴─────────────┘
     Regression possible (rare)
```

### Advancement rules (enforced by Supervisor)
| Score | Consecutive tests | Decision |
|-------|------------------|----------|
| ≥ 80% | 2nd in a row | **Advance** |
| ≥ 80% | 1st | Maintain + encourage |
| 60–79% | any | **Maintain** |
| 40–59% | any | Maintain + flag weak areas |
| < 40% | 2nd in a row | **Regress** |

---

## Communication Protocol Between Agents

Agents communicate through **structured context passing**, not direct API calls. Each agent receives:

```json
{
  "student_message": "...",
  "current_level": "B1",
  "focus": "conversation",
  "progress_summary": { ... },
  "invoking_agent": "principal"
}
```

The receiving agent returns:
```json
{
  "response": "...",
  "session_score": 78,
  "session_type": "conversation",
  "notify_supervisor": true,
  "progress_update": { ... }
}
```

---

## Tool Requirements by Agent

| Agent/Skill | file_read | file_write | web_search | web_fetch |
|---|:---:|:---:|:---:|:---:|
| Principal | ✅ | ✅ | ❌ | ❌ |
| Supervisor | ✅ | ✅ | ❌ | ❌ |
| Professor | ✅ | ❌ | ❌ | ❌ |
| placement-test | ✅ | ✅ | ❌ | ❌ |
| progress-test | ✅ | ✅ | ❌ | ❌ |
| conversation | ✅ | ✅ | ❌ | ❌ |
| writing-coach | ✅ | ✅ | ❌ | ❌ |
| vocabulary-reading | ✅ | ✅ | ❌ | ❌ |
| **daily-activities** | ✅ | ✅ | **✅** | **✅** |

---

## Design Principles

1. **Separation of concerns** — Each agent does exactly one thing
2. **State as single source of truth** — `progress.json` is the system's memory
3. **Model agnosticism** — System prompts are plain Markdown; any LLM can run them
4. **Framework agnosticism** — YAML specs can be parsed by any multi-agent framework
5. **Progressive complexity** — Difficulty always adapts to current CEFR level
6. **Bilingual adaptive** — Portuguese for guidance/feedback, English for exercises
7. **Additive state** — Progress is never deleted, only appended
