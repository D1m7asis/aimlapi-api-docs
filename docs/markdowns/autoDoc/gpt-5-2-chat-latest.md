# GPT-5.2 Chat Latest

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `openai/gpt-5-2-chat-latest`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/openai/gpt-5-2-chat-latest" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

GPT-5.2 Chat Latest is a large language model alias that always refers to the current stable release in the GPT-5.2 family, making it suitable for production scenarios where automatic upgrades to the latest stable behavior are acceptable. It is designed for text-based interaction and general-purpose language tasks.

Developed by OpenAI, this model supports chat-style completions and response generation with strong capabilities in reasoning, coding assistance, and analytical writing. It is intended for use cases where you want consistent, up-to-date quality without needing to track a specific version identifier.

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

{% openapi-operation spec="gpt-5-2-chat-latest" path="/v1/chat/completions" method="post" %}
[OpenAPI gpt-5-2-chat-latest](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/OpenAI/gpt-5-2-chat-latest.json)
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
     "model": "openai/gpt-5-2-chat-latest",
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
      "model": "openai/gpt-5-2-chat-latest",
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
  "model": "openai/gpt-5-2-pro"
}
```

{% endcode %}

</details>