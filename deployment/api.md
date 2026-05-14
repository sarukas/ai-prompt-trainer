# Deployment: Anthropic API

Use this trainer via the Anthropic API by passing `CLAUDE.md` as the system prompt.

## Basic setup

```python
import anthropic

with open('CLAUDE.md', 'r') as f:
    system_prompt = f.read()

client = anthropic.Anthropic()

response = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=8096,
    system=system_prompt,
    messages=[
        {"role": "user", "content": "Your question here"}
    ]
)
print(response.content[0].text)
```

## Recommended models

| Model | Use case |
|-------|----------|
| `claude-opus-4-5` | Best coaching quality; nuanced technique recommendations |
| `claude-sonnet-4-5` | Good balance of quality and cost for interactive sessions |
| `claude-haiku-3-5` | Sufficient for scoring and basic feedback; fast and cheap for high-volume |

## Adding reference files to context

Reference docs are not auto-loaded. Pass them in the messages array when relevant:

```python
with open('docs/techniques-library.md', 'r') as f:
    techniques = f.read()

response = client.messages.create(
    model="claude-sonnet-4-5",
    max_tokens=8096,
    system=system_prompt,
    messages=[
        {
            "role": "user",
            "content": f"Reference material:\n\n{techniques}\n\n---\n\nMy question: {user_question}"
        }
    ]
)
```

## Prompt caching (recommended for multi-turn sessions)

Cache the system prompt and reference docs to reduce cost on long conversations:

```python
response = client.messages.create(
    model="claude-sonnet-4-5",
    max_tokens=8096,
    system=[
        {
            "type": "text",
            "text": system_prompt,
            "cache_control": {"type": "ephemeral"}
        }
    ],
    messages=conversation_history
)
```

The system prompt qualifies for caching (>1024 tokens). On a 10-turn session this reduces input token cost by ~80%.

## Adaptations required

Remove from `CLAUDE.md` before using as API system prompt:
- Tool selection guide (no Perplexity/BrightData access)
- Shell/file size instructions (no filesystem)
- References to `deployment/` files (irrelevant in API context)

Replace the factual validation line with:
```
- For factual claims, state your confidence level and note that external verification is recommended
```
