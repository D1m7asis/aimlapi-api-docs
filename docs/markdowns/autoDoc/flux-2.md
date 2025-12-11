# Flux 2

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `blackforestlabs/flux-2`
* `blackforestlabs/flux-2-edit`
* `blackforestlabs/flux-2-lora`
* `blackforestlabs/flux-2-lora-edit`
* `blackforestlabs/flux-2-pro`
* `blackforestlabs/flux-2-pro-edit`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=blackforestlabs/flux-2" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Flux 2 is an image generation model from Black Forest Labs, available via fal.ai, designed for high-quality text-to-image, image-to-image, and image editing workflows. It supports both text and visual modalities and includes specialized variants for LoRA-based customization and professional-grade rendering.

The model family targets use cases such as detailed illustrations, promotional imagery, and artistic scenes, with multiple variants (`base`, `edit`, `lora`, `pro`) optimized for different generation and editing scenarios.

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

{% openapi-operation spec="flux-2" path="/v1/images/generations" method="post" %}
{% endopenapi-operation %}

{% openapi-operation spec="flux-2" path="/images/generations" method="post" %}
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/images/generations",
    headers={"Authorization":"Bearer <YOUR_AIMLAPI_KEY>","Content-Type":"application/json"},
    data=json.dumps({
        "model": "blackforestlabs/flux-2",
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
        "model": "blackforestlabs/flux-2",
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
{'id': 'img-1744193377-AbCdEfGhIjKlMnOpQrSt', 'object': 'image', 'created': 1744193377, 'model': 'blackforestlabs/flux-2', 'data': [{'url': 'https://cdn.aimlapi.com/images/blackforestlabs/flux-2/sample-image.png', 'b64_json': null}],'usage': {'prompt_tokens': 0, 'completion_tokens': 0, 'total_tokens': 0}}
```

{% endcode %}

</details>

<!-- Generated from AA-223 -->