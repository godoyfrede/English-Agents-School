# How to Implement — English Agents School

This guide explains how to use the agent specifications in this repository to build a working English learning system with any LLM or framework.

---

## What This Repository Provides

| File type | Location | Purpose |
|---|---|---|
| Agent specs | `agents/*.yaml` | Define each agent's role, routing, and behavior |
| Skill specs | `skills/*.yaml` | Define each skill's structure, tools, and outputs |
| System prompts | `prompts/*.md` | Ready-to-use system prompts for each agent/skill |
| JSON Schema | `schemas/progress.schema.json` | Validates the student state file |
| Docs | `docs/` | Architecture, methodology, and this guide |

---

## Minimum Requirements

To run this system you need:

1. **An LLM** with support for system prompts (any model)
2. **Tool use / function calling** (for file I/O; web search only for `daily-activities`)
3. **A way to switch system prompts** between agents (most frameworks support this)
4. **A writable file system** to store `progress.json`

---

## Option 1 — Manual System Prompt Injection (Any CLI)

The simplest possible implementation. Works with any LLM that accepts a system prompt.

### Setup

1. Pick the agent you want to run (e.g., `Professor`)
2. Open `prompts/professor.md`
3. Paste it as the system prompt in your CLI or API call
4. Attach `progress.json` as file context if your CLI supports it

### Example with Claude CLI

```bash
claude --system-prompt "$(cat prompts/professor.md)" \
       --file progress.json \
       "Quero uma aula de conversação"
```

### Example with OpenAI CLI

```bash
openai api chat.completions.create \
  -m gpt-4o \
  --system "$(cat prompts/professor.md)" \
  --message "Quero uma aula de conversação"
```

### Example with Ollama

```bash
ollama run llama3.1 "$(cat prompts/professor.md)

USER: Quero uma aula de conversação"
```

**Limitation:** In manual mode, you need to manually switch system prompts between agents and manually update `progress.json`.

---

## Option 2 — Python Implementation (LangChain / Any Framework)

### Basic structure

```python
import json
from pathlib import Path
from openai import OpenAI  # or anthropic, or any SDK

PROGRESS_FILE = Path("progress.json")
PROMPTS_DIR = Path("open-source/prompts")

def load_prompt(name: str) -> str:
    return (PROMPTS_DIR / f"{name}.md").read_text()

def load_progress() -> dict:
    if PROGRESS_FILE.exists():
        return json.loads(PROGRESS_FILE.read_text())
    return {"student": "Student", "current_level": None}

def save_progress(data: dict):
    PROGRESS_FILE.write_text(json.dumps(data, indent=2, ensure_ascii=False))

def run_agent(agent_name: str, user_message: str, progress: dict) -> str:
    client = OpenAI()  # swap for any provider
    system_prompt = load_prompt(agent_name)
    context = f"Student progress:\n{json.dumps(progress, indent=2)}"

    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {"role": "system", "content": system_prompt},
            {"role": "user", "content": f"{context}\n\n{user_message}"}
        ]
    )
    return response.choices[0].message.content

# Orchestration loop
def main():
    progress = load_progress()
    user_input = input("You: ")

    # Route via Principal
    routing_response = run_agent("principal", user_input, progress)
    print(f"Principal: {routing_response}")

    # The Principal's response contains routing decision
    # In a full implementation, parse the routing and invoke the correct agent

if __name__ == "__main__":
    main()
```

---

## Option 3 — CrewAI

```python
from crewai import Agent, Task, Crew
from crewai_tools import FileReadTool, FileWriteTool

from pathlib import Path

def load_prompt(name):
    return Path(f"open-source/prompts/{name}.md").read_text()

# Define agents
principal = Agent(
    role="English School Director",
    goal="Route student requests to the correct agent or skill",
    backstory=load_prompt("principal"),
    tools=[FileReadTool(file_path="progress.json")]
)

supervisor = Agent(
    role="Academic Supervisor",
    goal="Track student progress and manage CEFR level advancement",
    backstory=load_prompt("supervisor"),
    tools=[FileReadTool(file_path="progress.json"), FileWriteTool()]
)

professor = Agent(
    role="English Professor",
    goal="Teach English using CLT methodology, adapted to student's CEFR level",
    backstory=load_prompt("professor"),
    tools=[FileReadTool(file_path="progress.json")]
)

# Define tasks
conversation_task = Task(
    description="Conduct a conversation practice session adapted to the student's level",
    expected_output="A structured conversation session with feedback and score",
    agent=professor
)

# Run
crew = Crew(agents=[principal, supervisor, professor], tasks=[conversation_task])
result = crew.kickoff()
```

---

## Option 4 — AutoGen (Microsoft)

```python
import autogen
from pathlib import Path

config_list = [{"model": "gpt-4o", "api_key": "your-key"}]

llm_config = {"config_list": config_list}

def load_prompt(name):
    return Path(f"open-source/prompts/{name}.md").read_text()

principal = autogen.AssistantAgent(
    name="Principal",
    system_message=load_prompt("principal"),
    llm_config=llm_config,
)

professor = autogen.AssistantAgent(
    name="Professor",
    system_message=load_prompt("professor"),
    llm_config=llm_config,
)

supervisor = autogen.AssistantAgent(
    name="Supervisor",
    system_message=load_prompt("supervisor"),
    llm_config=llm_config,
)

user = autogen.UserProxyAgent(
    name="Student",
    human_input_mode="ALWAYS",
    code_execution_config=False,
)

# Start conversation
user.initiate_chat(principal, message="Quero começar a aprender inglês")
```

---

## Option 5 — Claude Code (Claude-specific CLI)

The `fred-english-school/` directory at the root of this repository contains a ready-to-install Claude Cowork plugin. See the [Cowork plugin README](../fred-english-school/README.md).

For Claude Code CLI:
```bash
cd your-project
claude --system-prompt "$(cat open-source/prompts/principal.md)"
```

---

## Implementing `web_search` for daily-activities

The `daily-activities` skill requires web search. Here's how to wire it:

```python
# With Tavily (recommended)
from tavily import TavilyClient

tavily = TavilyClient(api_key="your-key")

def web_search(query: str) -> str:
    results = tavily.search(query=query, max_results=3)
    return "\n".join([f"- {r['title']}: {r['url']}" for r in results["results"]])

# Pass as a tool to your LLM
tools = [{
    "type": "function",
    "function": {
        "name": "web_search",
        "description": "Search the web for current content",
        "parameters": {
            "type": "object",
            "properties": {
                "query": {"type": "string"}
            },
            "required": ["query"]
        }
    }
}]
```

---

## progress.json Initialization

If no `progress.json` exists, create it with this template:

```json
{
  "student": "Your Name",
  "current_level": null,
  "placement_date": null,
  "last_progress_test": null,
  "next_progress_test": null,
  "scores": {
    "placement": null,
    "progress_tests": []
  },
  "skill_sessions": {
    "conversation": {"sessions": 0, "last_session": null, "avg_score": null},
    "writing": {"sessions": 0, "last_session": null, "avg_score": null},
    "vocabulary_reading": {"sessions": 0, "last_session": null, "avg_score": null}
  },
  "activities_completed": [],
  "level_history": [],
  "notes": []
}
```

Validate against `schemas/progress.schema.json` using any JSON Schema validator.

---

## Supported Models (tested or compatible)

| Model | Provider | Notes |
|---|---|---|
| Claude 3.5 / 3.7 Sonnet | Anthropic | Full support, extended thinking optional |
| GPT-4o | OpenAI | Full support |
| GPT-4o-mini | OpenAI | Suitable for Professor/Supervisor only |
| Llama 3.1 70B+ | Meta / Ollama | Works locally, web_search needs manual tool |
| Mistral Large | Mistral AI | Full support |
| Gemini 1.5 Pro | Google | Full support |
| Gemini 1.5 Flash | Google | Suitable for Professor/Supervisor |

**Minimum recommended:** 8K context, tool use / function calling support.
