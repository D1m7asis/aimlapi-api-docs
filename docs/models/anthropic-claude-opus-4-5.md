# Claude 4.5 Opus

Claude Opus 4.5 — топовая модель Anthropic для сложных агентов и продвинутого кодинга с большим контекстом и сниженной ценой.

## Overview

- **Provider:** Anthropic
- **Developer:** Anthropic
- **Type:** llm
- **Model IDs:** anthropic/claude-opus-4-5
- **Modalities:** text, code, vision
- **Context Window:** 200,000 tokens
- **Supported Tasks:** text-to-text, image-to-text

## Quick Start

<snippet data-name="anthropic.messages" data-model="{{anthropic/claude-opus-4-5}}"></snippet>

## Pricing

| Provider | Input (per 1M tokens) | Output (per 1M tokens) |
|----------|----------------------|------------------------|
| Anthropic | $5 | $25 |
| AIML API | $5.25 | $26.25 |

*AIML API markup: 5%*


## Code Examples

### Python

```python
import asyncio
from anthropic import Anthropic

client = Anthropic(
    base_url="https://api.aimlapi.com/",
    auth_token="<YOUR_API_KEY>",
)


def main():
    message = client.messages.create(
        model="anthropic/claude-opus-4-5",
        max_tokens=2048,
        system="You are an AI assistant who knows everything.",
        messages=[
            {
                "role": "user",
                "content": "Hello, Claude",
            }
        ],
    )

    print("Message:", message.content)


if __name__ == "__main__":
    main()
```

### JavaScript

```javascript
const Anthropic = require('@anthropic-ai/sdk');

const api = new Anthropic({
  baseURL: 'https://api.aimlapi.com/',
  authToken: '<YOUR_API_KEY>',
});

const main = async () => {
  const message = await api.messages.create({
    model: 'anthropic/claude-opus-4-5',
    max_tokens: 2048,
    system: 'You are an AI assistant who knows everything.',
    messages: [
      {
        role: 'user',
        content: 'Tell me, why is the sky blue?',
      },
    ],
  });

  console.log('Message:', message);
};

main();
```


## API Documentation

- [API Documentation](https://ai.aimlapi.com/docs?endpoint=openai/chat-completions&model=anthropic/claude-opus-4-5)
- [JSON Schema](https://ai.aimlapi.com/docs-json?endpoint=openai/chat-completions&model=anthropic/claude-opus-4-5)


---

*Source: Jira ticket CCS-7*
