# AI/ML API Documentation



## Overview

# Overview

The **AI/ML API** provides a unified, enterprise‑grade platform for accessing **300+ AI models**, including leading systems such as **DeepSeek**, **Google Gemini**, **OpenAI ChatGPT**, **Anthropic Claude**, **StabilityAI**, and many others. Designed for reliability, scalability, and developer‑friendliness, the API supports production workloads with **high uptime**, **high rate limits**, and a consistent interface across all model families.

This overview introduces the core concepts, capabilities, and model categories available through the platform.

---

## Key Features

- **300+ AI models in one API**  
  Access state‑of‑the‑art models for text, code, images, audio, embeddings, search, reasoning, and more.

- **Unified interface**  
  A consistent request/response structure across all model providers simplifies integration and switching.

- **Enterprise‑grade performance**  
  High throughput, predictable latency, and reliable uptime suitable for mission‑critical applications.

- **Multiple model families**  
  Support for industry‑leading AI systems including:
  - DeepSeek R1 and V-series  
  - Google Gemini  
  - OpenAI ChatGPT and o-series  
  - Anthropic Claude  
  - StabilityAI and other generative media models  

- **Flexible integration**  
  Compatible with REST and streaming APIs, plus official SDKs in popular languages.

---

## Core Capabilities

The API provides a rich set of AI functionalities, each backed by multiple model options.

### Completion & Chat Models  
Power conversational agents, assistants, interactive reasoning, and natural language workflows. Supports both single‑turn and multi‑turn chat.

### Thinking & Reasoning Models  
Access models optimized for long‑form reasoning, planning, analysis, and advanced chain‑of‑thought performance.

### Code Generation  
Generate, refactor, debug, and explain source code across major programming languages.

### Embeddings  
Create vector embeddings for semantic search, retrieval‑augmented generation (RAG), recommendation, and clustering.

### Image‑to‑Text (Vision)  
Process and interpret images, extract structured information, and perform multimodal understanding.

### Function Calling  
Let models interact with your application by returning structured JSON results that match predefined functions.

### Web Search  
Enable models to retrieve up‑to‑date online information to improve accuracy and relevance.

### Streaming Mode  
Stream tokens in real time for responsive chat UIs or step‑by‑step model output.

### Audio Models (Music & Vocal)  
Advanced audio generation for music, vocals, and sound design using models such as:
- **Stable Audio**  
- **MiniMax Music Legacy**

---

## Model Categories

The API organizes its 300+ models into several high‑level categories for easier exploration:

- Text and Chat Models  
- Reasoning Models  
- Code Models  
- Embedding Models  
- Image and Vision Models  
- Audio Models (Music/Vocal/Speech)  
- Experimental and Specialized Models  

For a detailed comparison across performance, pricing, and capabilities, refer to the model comparison guide.

---

## Developer Experience

### Quickstart  
Get up and running in minutes with a simple API key setup and step‑by‑step instructions.

### Multi‑language SDK Support  
Official SDKs cover the most common development environments, with consistent design and usage patterns.

### Clear Error Handling  
Standardized error formats and troubleshooting guidance help ensure smooth production deployments.

---

## Documentation Structure

This overview is part of a larger documentation set designed for clarity and scalability:

- **Quickstart** – setup guide and supported SDKs  
- **Capabilities** – deep dives into each feature category  
- **API References** – endpoints, schemas, parameters, examples  
- **Model Overviews** – audio, vision, reasoning, and more  
- **Error Messages** – standard error types and handling  
- **Guides & Tutorials** – best practices and patterns  

---

## Next Steps

To get started:

1. Visit the Quickstart section to set up your API key.  
2. Explore the supported SDKs.  
3. Choose a model aligned with your use case.  
4. Make your first API call—either chat, completion, vision, audio, or embeddings.

The AI/ML API provides everything you need to build scalable, intelligent applications with the latest AI models.



## Pricing

```markdown
## Pricing

AI/ML API uses a simple **usage‑based pricing model** designed to scale from hobby projects to large‑scale production workloads. You only pay for the resources you consume, with no fixed monthly commitments or minimums.

### Free Tier

All new accounts automatically receive access to the **Free Tier**, allowing you to explore the platform, prototype, and integrate core features at no cost.  
According to the Free Tier policy (`docs/faq/free-tier.md`):

- Includes a monthly allotment of **free inference credits**.  
- Supports select **base models** for text generation, embeddings, and lightweight inference tasks.  
- Automatically renews each month while your usage remains within Free Tier limits.  
- Ideal for testing API requests, latency, and output quality before upgrading.

You can monitor your real‑time usage in the dashboard:  
https://aimlapi.com/app/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration

### Pro Models and Paid Usage

For production workloads or advanced capabilities, the API provides access to **Pro Models** (`docs/faq/pro-models.md`). These models offer:

- Higher performance and faster inference  
- Larger context windows  
- Access to premium model families  
- Enterprise‑grade reliability and throughput  
- Priority routing under load

Pro Models are billed based on **actual tokens or compute consumed**, depending on the model type (LLMs, embeddings, vision models, etc.).

### How Billing Works

- Each API call consumes a measurable amount of compute or tokens.  
- Usage is aggregated and billed at the end of the billing cycle.  
- You can set soft or hard usage limits to avoid unexpected charges.  
- Detailed usage analytics are available in your dashboard.

### Getting Started with Pricing

You can explore full pricing details and model‑specific rates in the documentation:  
https://docs.aimlapi.com/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration

To begin using the API or activate Pro Models, visit the dashboard:  
https://aimlapi.com/app/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration
```



## Code Examples

```markdown
## Python Example (OpenAI‑compatible `openai` client)

```python
# Docs:
# https://docs.aimlapi.com/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration
# Dashboard:
# https://aimlapi.com/app/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration

from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY",
    base_url="https://api.aimlapi.com/v1"
)

resp = client.chat.completions.create(
    model="aimlapi-chat-model",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain vector embeddings simply."}
    ]
)

print(resp.choices[0].message["content"])
```

---

## JavaScript Example (OpenAI‑compatible `openai` client)

```javascript
// Docs:
// https://docs.aimlapi.com/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration
// Dashboard:
// https://aimlapi.com/app/?utm_source=aimlapi-api-docs&utm_medium=github&utm_campaign=integration

import OpenAI from "openai";

const client = new OpenAI({
  apiKey: process.env.AIMLAPI_KEY,
  baseURL: "https://api.aimlapi.com/v1"
});

async function run() {
  const resp = await client.chat.completions.create({
    model: "aimlapi-chat-model",
    messages: [
      { role: "system", content: "You are a helpful assistant." },
      { role: "user", content: "Give me 3 ideas for an AI project." }
    ]
  });

  console.log(resp.choices[0].message.content);
}

run();
```

---
```markdown