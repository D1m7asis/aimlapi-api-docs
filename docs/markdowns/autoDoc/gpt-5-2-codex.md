# GPT-5.2-Codex

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `openai/gpt-5-2-codex`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/openai/gpt-5-2-codex" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

GPT-5.2-Codex is a large language model developed by OpenAI, specialized for advanced coding and long-horizon software engineering tasks. It is designed to handle complex, multi-step workflows such as refactoring extensive codebases, implementing features across many files, and supporting agentic coding systems that require sustained reasoning over large contexts.

The model accepts both text and image inputs and produces text outputs, enabling scenarios like interpreting code snippets, diagrams, and UI screenshots alongside natural language instructions. With support for adjustable reasoning effort and a context window of up to 400,000 tokens, it is well suited for large-scale code understanding, generation, and modification in demanding engineering environments.

## How to Make a Call

<details>

<summary>Step-by-Step Instructions</summary>

:digit_one: **Setup You Can’t Skip**

- [**Create an Account**](https://aimlapi.com/app/sign-up): Visit the AI/ML API website and create an account (if you don’t have one yet).  
- [**Generate an API Key**](https://aimlapi.com/app/keys): After logging in, navigate to your account dashboard and generate your API key. Ensure the key is enabled on the UI.  

:digit_two: **Copy the code example**

At the bottom of this page, you'll find a code example that shows how to structure the request. Choose the code snippet in your preferred programming language and copy it into your development environment.

:digit_three: **Modify the code example**

- Replace `<YOUR_AIMLAPI_KEY>` with your actual AI/ML API key.  
- Adjust the input field used by this model (for example, prompt, input text, instructions, media source, or other model-specific input) to match your request.  

:digit_four: <sup><sub><mark style="background-color:yellow;">**(Optional)**</mark></sub></sup> **Adjust other optional parameters if needed**

Only the required parameters shown in the example are needed to run the request, but you can include optional parameters to fine-tune behavior. Below, you can find the corresponding **API schema**, which lists all available parameters and usage notes.

:digit_five: **Run your modified code**

Run your modified code inside your development environment. Response time depends on many factors, but for simple requests it rarely exceeds a few seconds.

{% hint style="success" %}
If you need a more detailed walkthrough for setting up your development environment and making a request step-by-step, feel free to use our **[Quickstart guide.](https://docs.aimlapi.com/quickstart/setting-up)**
{% endhint %}

</details>

## API Schema

### Generate model responses for text and multi-modal inputs using the unified Responses API.

{% openapi-operation spec="gpt-5-2-codex" path="/v1/responses" method="post" %}
[OpenAPI gpt-5-2-codex](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/OpenAI/gpt-5-2-codex.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import os
from openai import OpenAI

client = OpenAI(
    base_url="https://api.aimlapi.com/v1",
    api_key="<YOUR_API_KEY>",    
)

response = client.responses.create(
    model="openai/gpt-5-2-codex",
    input="What is the fastest sorting algoritm?"
)

print(response.output_text)
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const { OpenAI } = require('openai');

const api = new OpenAI({
  baseURL: 'https://api.aimlapi.com/v1',
  apiKey: '<YOUR_API_KEY>',
});

const main = async () => {
  const response = await client.responses.create({
    model: 'openai/gpt-5-2-codex',
    input: 'What is the fastest sorting algoritm?',
  });

  console.log(response.output_text);
};

main();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "id": "lBNur4b8_DN_HSXdYGyfV",
  "object": "response",
  "created_at": 1769012533,
  "status": "completed",
  "background": false,
  "billing": {
    "payer": "developer"
  },
  "completed_at": 1769012542,
  "error": null,
  "frequency_penalty": 0,
  "incomplete_details": null,
  "instructions": null,
  "max_output_tokens": null,
  "max_tool_calls": null,
  "model": "gpt-5.2-codex",
  "output": [
    {
      "id": "rs_04c03e65e8ed6780006970fd3566f881a3ab2d37c108489ca3",
      "type": "reasoning",
      "summary": []
    },
    {
      "id": "msg_04c03e65e8ed6780006970fd3a2c1881a3a325484c5ac17a59",
      "type": "message",
      "status": "completed",
      "content": [
        {
          "type": "output_text",
          "annotations": [],
          "logprobs": [],
          "text": "There isn’t a single “fastest” sorting algorithm for all cases.\n\n- **For comparison-based sorting**, the theoretical lower bound is **O(n log n)**. Algorithms like **Quicksort**, **Mergesort**, **Heapsort**, or **Timsort** are typically used, with Quicksort often fastest in practice on average.\n- **For special cases** (like sorting integers in a limited range), **non‑comparison sorts** such as **Counting Sort** or **Radix Sort** can run in **O(n)** and be faster.\n\nSo the “fastest” depends on the data type, size, memory constraints, and how the data is distributed."
        }
      ],
      "role": "assistant"
    }
  ],
  "parallel_tool_calls": true,
  "presence_penalty": 0,
  "previous_response_id": null,
  "prompt_cache_key": null,
  "prompt_cache_retention": null,
  "reasoning": {
    "effort": "medium",
    "summary": null
  },
  "safety_identifier": null,
  "service_tier": "default",
  "store": true,
  "temperature": 1,
  "text": {
    "format": {
      "type": "text"
    },
    "verbosity": "medium"
  },
  "tool_choice": "auto",
  "tools": [],
  "top_logprobs": 0,
  "top_p": 0.98,
  "truncation": "disabled",
  "usage": {
    "input_tokens": 14,
    "input_tokens_details": {
      "cached_tokens": 0
    },
    "output_tokens": 274,
    "output_tokens_details": {
      "reasoning_tokens": 128
    },
    "total_tokens": 288
  },
  "user": null,
  "metadata": {},
  "output_text": "There isn’t a single “fastest” sorting algorithm for all cases.\n\n- **For comparison-based sorting**, the theoretical lower bound is **O(n log n)**. Algorithms like **Quicksort**, **Mergesort**, **Heapsort**, or **Timsort** are typically used, with Quicksort often fastest in practice on average.\n- **For special cases** (like sorting integers in a limited range), **non‑comparison sorts** such as **Counting Sort** or **Radix Sort** can run in **O(n)** and be faster.\n\nSo the “fastest” depends on the data type, size, memory constraints, and how the data is distributed."
}
```

{% endcode %}

</details>