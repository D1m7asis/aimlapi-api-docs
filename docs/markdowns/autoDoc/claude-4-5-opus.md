# Claude 4.5 Opus

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `anthropic/claude-opus-4-5`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %} <a href="https://aimlapi.com/app/?model=claude-opus-4-5-20251101" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Claude 4.5 Opus is Anthropic’s flagship large language model, optimized for complex agents, advanced coding tasks, and other high-difficulty reasoning workloads. It provides maximum reasoning depth and extended thinking capabilities compared to earlier Opus versions.

The model supports text, code, and vision modalities, with a context window of up to 200,000 tokens. It is well suited for text-to-text and image-to-text (vision) tasks in production environments where high intelligence and long-context handling are required.

## How to Make a Call

<details>

<summary>Step-by-Step Instructions</summary>

:digit_one: **Setup You Can’t Skip**

:black_small_square: [**Create an Account**](https://aimlapi.com/app/sign-up): Visit the AI/ML API website and create an account (if you don’t have one yet).  
:black_small_square: [**Generate an API Key**](https://aimlapi.com/app/keys): After logging in, navigate to your account dashboard and generate your API key. Ensure the key is enabled on the UI.

:digit_two: **Copy the code example**

At the bottom of this page, you'll find a code example that shows how to structure the request. Choose the code snippet in your preferred programming language and copy it into your development environment.

:digit_three: **Modify the code example**

:black_small_square: Replace `<YOUR_AIMLAPI_KEY>` with your actual AI/ML API key.  
:black_small_square: Insert your question or request into the `content` field—this is what the model will respond to.

:digit_four: <sup><sub><mark style="background-color:yellow;">**(Optional)**</mark></sub></sup> **Adjust other optional parameters if needed**

Only `model` and `messages` are required parameters for this model (and they are already correctly set in the example), but you can include optional parameters to fine-tune behavior. Below, you can find the corresponding **API schema**, which lists all available parameters and usage notes.

:digit_five: **Run your modified code**

Run your modified code inside your development environment. Response time depends on many factors, but for simple prompts it rarely exceeds a few seconds.

{% hint style="success" %}
If you need a more detailed walkthrough for setting up your development environment and making a request step-by-step, feel free to use our [**Quickstart guide.**](https://docs.aimlapi.com/quickstart/setting-up)
{% endhint %}

</details>


# API Schema
>Здесь вставить схему OpenAPI



```md
## Code Example

### Python (requests)

```python
import requests
import json

API_URL = "https://api.your-ml-service.com/v1/predict"
API_KEY = "YOUR_API_KEY"

headers = {
    "Authorization": f"Bearer {API_KEY}",
    "Content-Type": "application/json",
}

payload = {
    "model": "your-model-name",
    "input": {
        # Replace with the specific fields your model expects
        "text": "Classify this sentence",
        "metadata": {
            "language": "en"
        }
    },
    # Optional: model-specific configuration
    "params": {
        "temperature": 0.2,
        "top_p": 0.9
    }
}

response = requests.post(API_URL, headers=headers, data=json.dumps(payload))
response.raise_for_status()

result = response.json()
print(json.dumps(result, indent=2))
```

---

### JavaScript (Node.js, fetch)

```js
import fetch from "node-fetch";

const API_URL = "https://api.your-ml-service.com/v1/predict";
const API_KEY = "YOUR_API_KEY";

async function runInference() {
  const payload = {
    model: "your-model-name",
    input: {
      // Replace with the specific fields your model expects
      text: "Classify this sentence",
      metadata: {
        language: "en",
      },
    },
    // Optional: model-specific configuration
    params: {
      temperature: 0.2,
      top_p: 0.9,
    },
  };

  const response = await fetch(API_URL, {
    method: "POST",
    headers: {
      Authorization: `Bearer ${API_KEY}`,
      "Content-Type": "application/json",
    },
    body: JSON.stringify(payload),
  });

  if (!response.ok) {
    const errorBody = await response.text();
    throw new Error(`Request failed: ${response.status} - ${errorBody}`);
  }

  const result = await response.json();
  console.log(JSON.stringify(result, null, 2));
}

runInference().catch(console.error);
```

---

### curl

```bash
API_KEY="YOUR_API_KEY"

curl -X POST "https://api.your-ml-service.com/v1/predict" 
  -H "Authorization: Bearer ${API_KEY}" 
  -H "Content-Type: application/json" 
  -d '{
    "model": "your-model-name",
    "input": {
      "text": "Classify this sentence",
      "metadata": {
        "language": "en"
      }
    },
    "params": {
      "temperature": 0.2,
      "top_p": 0.9
    }
  }'
```

---

### Response example

```json
{
  "id": "req_abc123",
  "model": "your-model-name",
  "created": 1733741250,
  "input": {
    "text": "Classify this sentence",
    "metadata": {
      "language": "en"
    }
  },
  "output": {
    "label": "positive",
    "score": 0.94,
    "explanation": "The text contains positive sentiment."
  },
  "usage": {
    "input_tokens": 14,
    "output_tokens": 22,
    "total_tokens": 36
  }
}
```
```