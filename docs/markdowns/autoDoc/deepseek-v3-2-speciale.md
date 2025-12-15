# DeepSeek-V3.2-Speciale

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `deepseek/deepseek-v3.2-speciale`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/deepseek/deepseek-v3.2-speciale" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

DeepSeek-V3.2-Speciale is an experimental large language model developed by DeepSeek, optimized for complex reasoning and long-context chat-based workflows. It supports text and code generation, with a context window of up to 128,000 tokens, and is designed to operate in a thinking-focused mode for structured, multi-step problem solving.

The model is well suited for chat completion, agent-style behaviors, and tasks that benefit from explicit reasoning traces, robust handling of difficult queries, and integration with tools following the DeepSeek specification, including tool calling and Chat Prefix/FIM-style completion.

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

## API Schema

{% openapi-operation spec="deepseek-v3-2-speciale" path="/v1/chat/completions" method="post" %}
[OpenAPI deepseek-v3-2-speciale](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/DeepSeek/deepseek-v3-2-speciale.json)
{% endopenapi-operation %}

{% openapi-operation spec="deepseek-v3-2-speciale" path="/chat/completions" method="post" %}
[OpenAPI deepseek-v3-2-speciale](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/DeepSeek/deepseek-v3-2-speciale.json)
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
        "model":"deepseek/deepseek-v3.2-speciale",
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
      model: 'deepseek/deepseek-v3.2-speciale',
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
  'model': 'deepseek/deepseek-v3.2-speciale',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/deepseek/deepseek-v3.2-speciale/example-output.png',
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

<!-- Generated from AD-242 -->