# Ollama Implementation (Local Models)

Run the English Agents School fully locally — no API key, no data sent to the cloud.

## Requirements

- [Ollama](https://ollama.ai) installed
- 16GB+ RAM recommended for 70B models
- 8GB RAM minimum for 8B models (reduced quality)

## Recommended Models

| Model | Size | Quality | Command |
|-------|------|---------|---------|
| llama3.1:70b | 40GB | Best | `ollama pull llama3.1:70b` |
| llama3.1:8b | 5GB | Good | `ollama pull llama3.1:8b` |
| mistral:7b | 4GB | Good | `ollama pull mistral:7b` |
| gemma2:27b | 16GB | Great | `ollama pull gemma2:27b` |

## Quick Start

```bash
# Pull a model
ollama pull llama3.1:8b

# Run with Professor prompt
PROMPT=$(cat open-source/prompts/professor.md)
ollama run llama3.1:8b "$PROMPT

USER: Quero uma aula de conversação"
```

## Python with Ollama API

```python
import requests
from pathlib import Path
import json

OLLAMA_URL = "http://localhost:11434/api/chat"
MODEL = "llama3.1:8b"

progress = json.loads(Path("progress.json").read_text()) if Path("progress.json").exists() else {}
system_prompt = Path("open-source/prompts/professor.md").read_text()

response = requests.post(OLLAMA_URL, json={
    "model": MODEL,
    "messages": [
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": f"Progress: {json.dumps(progress)}\n\nQuero praticar conversação"}
    ],
    "stream": False
})

print(response.json()["message"]["content"])
```

## Notes

- Local models may produce less consistent feedback than cloud models
- For daily-activities with web_search, you still need an internet connection and a search API
- Recommended minimum: llama3.1:8b for basic sessions, llama3.1:70b for full quality
