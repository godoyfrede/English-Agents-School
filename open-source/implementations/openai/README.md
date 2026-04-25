# OpenAI Implementation

Run the English Agents School using the OpenAI API (or any OpenAI-compatible endpoint).

## Install

```bash
pip install openai tavily-python
```

## Environment Variables

```bash
export OPENAI_API_KEY="sk-..."
export TAVILY_API_KEY="tvly-..."   # only needed for daily-activities
```

## Single Agent (Professor)

```python
from openai import OpenAI
from pathlib import Path
import json

client = OpenAI()
progress = json.loads(Path("progress.json").read_text()) if Path("progress.json").exists() else {}
system_prompt = Path("../../prompts/professor.md").read_text()

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": f"Progress: {json.dumps(progress)}\n\nQuero praticar conversação"}
    ]
)
print(response.choices[0].message.content)
```

## Full Orchestrated System

See `HOW_TO_IMPLEMENT.md` in the docs folder for the complete implementation guide.
