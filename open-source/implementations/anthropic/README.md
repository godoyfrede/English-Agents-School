# Anthropic / Claude Implementation

Run the English Agents School using the Anthropic Claude API.

## Install

```bash
pip install anthropic tavily-python
```

## Environment Variables

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
export TAVILY_API_KEY="tvly-..."   # only needed for daily-activities
```

## Single Agent (Professor)

```python
import anthropic
from pathlib import Path
import json

client = anthropic.Anthropic()
progress = json.loads(Path("progress.json").read_text()) if Path("progress.json").exists() else {}
system_prompt = Path("../../prompts/professor.md").read_text()

response = client.messages.create(
    model="claude-sonnet-4-5",
    max_tokens=4096,
    system=system_prompt,
    messages=[
        {
            "role": "user",
            "content": f"Student progress:\n{json.dumps(progress, indent=2)}\n\nQuero praticar conversação"
        }
    ]
)
print(response.content[0].text)
```

## With Extended Thinking (C1/C2 levels)

For advanced levels, enable extended thinking for more nuanced feedback:

```python
response = client.messages.create(
    model="claude-sonnet-4-5",
    max_tokens=8000,
    thinking={"type": "enabled", "budget_tokens": 2000},
    system=system_prompt,
    messages=[{"role": "user", "content": user_message}]
)
```

## Claude Cowork Plugin

The `fred-english-school/` directory at the root of this repo is a ready-to-install Cowork plugin. No code needed — just import the `.plugin` file in the Cowork app.
