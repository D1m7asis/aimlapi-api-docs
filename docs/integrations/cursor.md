# Cursor

## Overview

[Cursor](https://www.cursor.com/) is an AI-native IDE that bundles an OpenAI- and Azure OpenAI–compatible chat experience alongside code editing tools. You can connect Cursor to AI/ML API through the Azure pathway to route all traffic to a single deployment while keeping the interface familiar for your team.

For further information about Cursor, explore the official resources:

* [Cursor Docs – Azure OpenAI](https://docs.cursor.com/advanced/azure-openai)
* [Cursor Community](https://cursor.com/discord)

***

## Integration via Cursor (Azure flow)

### Prerequisites

* AI/ML API key from the [dashboard](https://aimlapi.com/app/keys)
* Cursor Desktop application (latest release)
* Network access to `https://api.aimlapi.com`

***

### Connection Setup

{% hint style="warning" %}
Double-check that you configure Cursor under **Settings → Models → Azure**, not the OpenAI tab.
{% endhint %}

1. Open **Cursor → Settings → Models → Azure**.
2. Fill the connection fields as shown below:

   * **Base URL**

     ```
     https://api.aimlapi.com
     ```

   * **Deployment Name**

     ```
     google/gemini-2.5-pro
     ```

   * **API Key** – paste your AI/ML API key exactly as issued (no extra spaces).

3. Click **Verify** to validate the connection.
4. In the chat model picker, enable a friendly alias such as `gpt-4o` so that teammates only see a clean model list while the deployment continues to point to `google/gemini-2.5-pro`.

> ⚠️ Keep the Base URL exactly `https://api.aimlapi.com`; do **not** append `/v2/azure` or `/openai`.

***

### Optional smoke test

Cursor automatically builds Azure-compatible requests. You can confirm the setup by sending a manual request:

```bash
curl -sS -X POST \
  "https://api.aimlapi.com/openai/deployments/google/gemini-2.5-pro/chat/completions?api-version=2024-12-01-preview" \
  -H "Api-Key: YOUR_AIMLAPI_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [
      {"role":"system","content":"You are a helpful coding assistant."},
      {"role":"user","content":"Give me a one-line Python function to merge two dicts."}
    ]
  }'
```

A successful response returns `choices[0].message.content` with the assistant's reply.

***

### GUI Integration

Cursor’s chat view and composer will automatically use the alias (Model ID) you enabled. To keep things tidy for teams:

* Reuse the same alias (for example, `gpt-4o`) across workspaces.
* Store the Base URL and deployment mapping in your internal documentation.
* If the alias list looks incorrect, toggle Azure off and on, click **Verify**, and restart Cursor to refresh the cache.

***

## ✅ Supported AIMLAPI Models

All chat-compatible models served by AIMLAPI are supported through Cursor’s Azure flow, including:

* **Mistralai** – `Mistral-7B-Instruct`, `Mixtral-8x7B`
* **Meta** – `Meta-LLaMA-3.1`, `LLaMA-3.3`
* **Anthropic** – `Claude-3.5-Haiku`
* **NVIDIA** – `Nemotron-70B`
* **Google, xAI, Alibaba, Cohere, DeepSeek** – available through the unified `https://api.aimlapi.com` endpoint.

📘 View [our full text (chat) model catalog](../api-references/text-models-llm/#complete-text-model-list).

***

## ⚙️ Supported Parameters

Cursor sends standard OpenAI-compatible parameters. No AIMLAPI-specific overrides are required:

* `model`
* `messages`
* `temperature`
* `max_tokens`
* `stream`
* `tools`

***

## 🧠 Supported Call Features

<table><thead><tr><th width="289">Feature</th><th>Cursor (Azure flow)</th><th>Notes</th></tr></thead><tbody><tr><td>Synchronous calls</td><td>✅</td><td>Standard chat completions.</td></tr><tr><td>Asynchronous use</td><td>🟡</td><td>Handled via Cursor queues; streaming updates appear inline.</td></tr><tr><td>Tool Calling</td><td>✅</td><td>Forwarded through AI/ML API when tools are defined.</td></tr><tr><td>Streaming</td><td>✅</td><td>Cursor streams assistant tokens in the chat panel.</td></tr><tr><td>Threads</td><td>❌</td><td>Azure flow does not expose Threads API.</td></tr><tr><td>Local tools</td><td>✅</td><td>Available through Cursor Composer actions.</td></tr></tbody></table>
