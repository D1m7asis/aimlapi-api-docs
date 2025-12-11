# Qwen Text Embedding v4

# Qwen Text Embedding v4

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `alibaba/qwen-text-embedding-v4`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=alibaba/qwen-text-embedding-v4" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Qwen Text Embedding v4 is a universal text embedding model developed by Qwen / Alibaba and served via Alibaba Cloud Model Studio. It produces dense vector representations for text inputs and supports configurable embedding dimensions ranging from 64 to 2048, making it adaptable to different latency, storage, and accuracy requirements.

The model is designed for multilingual scenarios, with support for over 100 languages, and is suitable for a wide range of semantic tasks such as semantic search, retrieval-augmented generation (RAG), clustering, similarity matching, and other embedding-based workflows.

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
If you need a more detailed walkthrough for setting up your development environment and making a request step-by-step, feel free to use our **[Quickstart guide.](https://docs.aimlapi.com/quickstart/setting-up)**
{% endhint %}

</details>

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests
response = requests.post(
    "https://api.aimlapi.com/v1/embeddings",
    headers={
      "Authorization":"Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type":"application/json"
    },
    data=json.dumps({
      "model": "alibaba/qwen-text-embedding-v4",
      "input": "The quick brown fox jumps over the lazy dog.",
      "dimensions": 1024
    })
)
data = response.json()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const response = await fetch('https://api.aimlapi.com/v1/embeddings', {
    method: 'POST',
    headers: {
      "Authorization": "Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type": "application/json"
    },
    body: JSON.stringify({
      "model": "alibaba/qwen-text-embedding-v4",
      "input": "The quick brown fox jumps over the lazy dog.",
      "dimensions": 1024
});
const data = await response.json();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json5
{'id': 'embd-1744193377-PR9oTu6vDabN9nj0VUUX', 'object': 'list', 'model': 'alibaba/qwen-text-embedding-v4', 'data': [{'object': 'embedding', 'index': 0, 'embedding': [0.0123, -0.0456, 0.0789, 0.0012, -0.0345]}], 'usage': {'prompt_tokens': 9, 'total_tokens': 9}}
```

{% endcode %}

</details>

<!-- Generated from AA-187 -->