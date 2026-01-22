# GPT-5.2

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `openai/gpt-5-2`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/openai/gpt-5-2" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

GPT-5.2 is a flagship general-purpose large language model developed by OpenAI, optimized for high-quality reasoning, code generation, data analysis, and robust tool interaction. It is designed to handle both natural language and programming languages, making it suitable for complex analytical and engineering workloads.

As the successor to GPT-4.1 and GPT-5.1, it targets production use cases that demand stronger reasoning quality and faster responses, serving as a primary engine for sophisticated chat-driven systems, intelligent agents, and other text-centric applications where reliability and depth of understanding are essential.

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

### Generate chat-based text completions from a list of messages.

{% openapi-operation spec="gpt-5-2" path="/v1/chat/completions" method="post" %}
[OpenAPI gpt-5-2](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/OpenAI/gpt-5-2.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/chat/completions",
    headers={
      "Authorization":"Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type":"application/json"
    },
    data=json.dumps({
     "model": "openai/gpt-5-2",
     "messages": [
        {
          "role": "user",
          "content": "How to learn python?"
        }
      ],
      "stream": False,
    })
)

data = response.json()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const response = await fetch('https://api.aimlapi.com/v1/chat/completions', {
    method: 'POST',
    headers: {
      "Authorization": "Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type": "application/json"
    },
    body: JSON.stringify({
      "model": "openai/gpt-5-2",
      "messages": [
          {
            "role": "user",
            "content": "How to learn typescript?"
          }
        ],
        "stream": false,
});

const data = await response.json()
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "model": "openai/gpt-5-2"
}
```

{% endcode %}

</details>

<!-- Generated from AA-238 -->