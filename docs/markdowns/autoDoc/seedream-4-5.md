# Seedream 4.5

# Seedream 4.5

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `bytedance/seedream-4-5`
* `seedream-4-5-251128`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=seedream-4-5-251128" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Seedream 4.5 is ByteDance’s latest image generation model, developed by the Seedream Team and served via ByteDance / BytePlus. It supports both vision and text modalities, with a focus on high-quality text-to-image and image-to-image synthesis as well as image editing and multi-image instruction.

The model emphasizes improved editing consistency, portrait and face quality, fine-grained text rendering, multi-image fusion, and robust logical scene understanding. It is designed for commercial visual content workflows such as e-commerce product imagery, advertising creatives, film and game concept art, and architectural visualization.

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

{% openapi-operation spec="seedream-4-5" path="/v1/images/generations" method="post" %}
[OpenAPI seedream-4-5](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/image-models/ByteDance/seedream-4-5.json)
{% endopenapi-operation %}

{% openapi-operation spec="seedream-4-5" path="/images/generations" method="post" %}
[OpenAPI seedream-4-5](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/image-models/ByteDance/seedream-4-5.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/images/generations",
    headers={"Authorization":"Bearer <YOUR_AIMLAPI_KEY>","Content-Type":"application/json"},
    data=json.dumps({
        "model": "bytedance/seedream-4-5",
        "prompt": "Mount Fuji with cherry blossoms in the foreground, clear sky, peaceful spring day, soft natural light, realistic landscape.",
    })
)

data = response.json()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const response = await fetch('https://api.aimlapi.com/v1/images/generations', {
    method: 'POST',
    headers: {
      "Authorization": "Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type": "application/json"
    },
    body: JSON.stringify({
        "model": "bytedance/seedream-4-5",
        "prompt": "Mount Fuji with cherry blossoms in the foreground, clear sky, peaceful spring day, soft natural light, realistic landscape.",
    })
});

const data = await response.json();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json5
{'created': 1733905732, 'data': [{'b64_json': None, 'url': 'https://image.pollinations.ai/prompt/Mount%20Fuji%20with%20cherry%20blossoms%20in%20the%20foreground,%20clear%20sky,%20peaceful%20spring%20day,%20soft%20natural%20light,%20realistic%20landscape.'}], 'model': 'bytedance/seedream-4-5', 'object': 'image.completion', 'usage': {'completion_tokens': 300, 'prompt_tokens': 42, 'total_tokens': 342}}
```

{% endcode %}

</details>

<!-- Generated from AA-224 -->