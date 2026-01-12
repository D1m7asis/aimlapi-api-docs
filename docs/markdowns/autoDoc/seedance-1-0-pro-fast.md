# Seedance 1.0 Pro Fast

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `bytedance/seedance-1-0-pro-fast`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=bytedance/seedance-1-0-pro-fast&mode=video" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Seedance 1.0 Pro Fast is a video generation model developed by Bytedance and provided by Segmind, optimized for rapid creation of short cinematic clips. It supports both text-to-video and image-to-video workflows, producing approximately 10-second outputs with high visual fidelity, realistic motion, and expressive lighting.

The model is well-suited for tasks such as concept visualization, creative content production, and short promotional material, where fast iteration and visually rich results from simple text descriptions or reference images are important.

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

Generate videos from prompts and/or media inputs (provider-dependent).

{% openapi-operation spec="bytedance-seedance-1-0-pro-fast" path="/v2/video/generations" method="post" %}
[OpenAPI bytedance-seedance-1-0-pro-fast](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/bytedance/bytedance-seedance-1-0-pro-fast.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v2/video/generations",
    headers={
        "Content-Type": "application/json",
        "Authorization": "Bearer <YOUR_API_KEY>",
    },
    json={
        "model": "bytedance/seedance-1-0-pro-fast",
        "prompt": "A menacing evil dragon appears in a distance above the tallest mountain, then rushes toward the camera with its jaws open, revealing massive fangs. We see it's coming."
      }
)

data = response.json()
print(data)
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
async function main() {
  const response = await fetch('https://api.aimlapi.com/v2/video/generations', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer <YOUR_API_KEY>',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      "model": "bytedance/seedance-1-0-pro-fast",
      "prompt": "A menacing evil dragon appears in a distance above the tallest mountain, then rushes toward the camera with its jaws open, revealing massive fangs. We see it's coming."
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
  'model': 'bytedance/seedance-1-0-pro-fast',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/bytedance/seedance-1-0-pro-fast/example-output.png',
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

<!-- Generated from AA-182 -->