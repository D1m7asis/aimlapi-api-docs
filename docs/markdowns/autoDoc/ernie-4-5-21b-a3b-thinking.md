# ERNIE 4.5 21B A3B Thinking

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `baidu/ernie-4.5-21b-a3b-thinking`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=baidu/ernie-4.5-21b-a3b-thinking" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

ERNIE 4.5 21B A3B Thinking is a large language model developed by Baidu (ERNIE) for advanced text and code generation. It is optimized for chat-style interaction and text-to-text tasks, supporting rich natural language understanding and synthesis.

The model provides an enhanced reasoning mode aimed at complex analytical problems, step-by-step explanations, and tasks that require deeper logical inference compared with more general-purpose conversational models.

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

Generate chat-based text completions from a list of messages.

{% openapi-operation spec="ernie-4.5-21b-a3b-thinking" path="/v1/chat/completions" method="post" %}
[OpenAPI ernie-4.5-21b-a3b-thinking](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/baidu/ernie-4.5-21b-a3b-thinking.json)
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
        "model":"baidu/ernie-4.5-21b-a3b-thinking",
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
      model: 'baidu/ernie-4.5-21b-a3b-thinking',
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
  'model': 'baidu/ernie-4.5-21b-a3b-thinking',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/baidu/ernie-4.5-21b-a3b-thinking/example-output.png',
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

<!-- Generated from AD-265 -->