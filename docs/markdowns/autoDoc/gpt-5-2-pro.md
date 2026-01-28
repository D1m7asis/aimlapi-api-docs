# GPT-5.2 Pro

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `openai/gpt-5-2-pro`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/openai/gpt-5-2-pro" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

GPT-5.2 Pro is an enhanced large language model developed by OpenAI, offering increased limits and preferential access to capacity compared to the standard GPT-5.2. It is optimized for demanding, high-load production scenarios where consistent performance on complex text and code generation workloads is critical.

Supporting text and code modalities, the model is suitable for tasks that require reliable, high-throughput responses, such as advanced reasoning, long-form content generation, and program synthesis or refactoring in production environments.

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

{% openapi-operation spec="gpt-5-2-pro" path="/v1/responses" method="post" %}
[OpenAPI gpt-5-2-pro](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/OpenAI/gpt-5-2-pro.json)
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
    model="openai/gpt-5-2-pro",
    input="Write a one-sentence bedtime story about a unicorn."
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
    model: 'openai/gpt-5-2-pro',
    input: 'Write a one-sentence bedtime story about a unicorn.',
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
  "model": "openai/gpt-5-2-pro"
}
```

{% endcode %}

</details>