# GPT-5.2 (OpenAI)

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `openai/gpt-5-2`
* `openai/gpt-5-2-chat-latest`
* `openai/gpt-5-2-pro`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=openai/gpt-5-2" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

GPT-5.2 is OpenAI’s flagship general-purpose language model for text and code, designed for advanced reasoning, software development, data analysis, and tool use. It improves on GPT-4.1 and GPT-5.1 with higher reasoning quality and faster responses while remaining suitable for production workloads.

The base `openai/gpt-5-2` model targets versatile everyday use, while the `openai/gpt-5-2-chat-latest` identifier tracks the current stable GPT-5.2 release. The `openai/gpt-5-2-pro` variant is intended for demanding, high-throughput production scenarios that require enhanced capacity and more stringent reliability under heavy load.

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
:black_small_square: Adjust the input field used by this model (for example, prompt, input text, instructions, media source, or other model-specific input) to match your request.

:digit_four: <sup><sub><mark style="background-color:yellow;">**(Optional)**</mark></sub></sup> **Adjust other optional parameters if needed**

Only the required parameters shown in the example are needed to run the request, but you can include optional parameters to fine-tune behavior. Below, you can find the corresponding **API schema**, which lists all available parameters and usage notes.

:digit_five: **Run your modified code**

Run your modified code inside your development environment. Response time depends on many factors, but for simple requests it rarely exceeds a few seconds.

{% hint style="success" %}
If you need a more detailed walkthrough for setting up your development environment and making a request step-by-step, feel free to use our **[Quickstart guide.](https://docs.aimlapi.com/quickstart/setting-up)**
{% endhint %}

</details>

## API Schema

{% openapi-operation spec="gpt-5-2-openai" path="/v1/chat/completions" method="post" %}
[OpenAPI gpt-5-2-openai](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/OpenAI/gpt-5-2-openai.json)
{% endopenapi-operation %}

{% openapi-operation spec="gpt-5-2-openai" path="/chat/completions" method="post" %}
[OpenAPI gpt-5-2-openai](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/OpenAI/gpt-5-2-openai.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/chat/completions",
    headers={
        "Content-Type":"application/json", 
        "Authorization":"Bearer <YOUR_AIMLAPI_KEY>",
    },
    json={
        "model":"openai/gpt-5-2",
        "messages":[
            {
                "role":"user",
                "content":"Hello"
            }
        ]
    }
)

data = response.json()
print(data)
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
async function main() {
  const response = await fetch('https://api.aimlapi.com/v1/chat/completions', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer <YOUR_AIMLAPI_KEY>',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      model: 'openai/gpt-5-2',
      messages:[
          {
              role:'user',
              content: 'Hello'
          }
      ]
    }),
  });

  const data = await response.json();
  console.log(JSON.stringify(data, null, 2));
}

main();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json5
{
  'id': 'gen-1733832000-example',
  'object': 'image',
  'created': 1733832000,
  'model': 'openai/gpt-5-2',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/openai/gpt-5-2/example-output.png',
      'revised_prompt': 'Example output for documentation.'
    }
  ],
  'usage': {
    'prompt_tokens': 0,
    'completion_tokens': 0,
    'total_tokens': 0
  }
}
```

{% endcode %}

</details>

<!-- Generated from AA-238 -->