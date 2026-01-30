# Wan 2.6 – Image generation

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `alibaba/wan-2-6-image`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/alibaba/wan-2-6-image" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Wan 2.6 – Image generation is an image model for creating and editing images from text prompts and combinations of text with reference images. It supports flexible image-conditioning workflows to control composition, style, and specific visual elements while still following natural language instructions.

Developed by Alibaba (Wan), the model is suited to creative image synthesis, compositing multiple source images into a single scene, and refining or transforming existing images based on detailed prompts, making it useful for both concept exploration and production-quality visual content.

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

### Generate images from prompts and optional parameters (size, format, etc.).

{% openapi-operation spec="alibaba-wan-2-6-image" path="/v1/images/generations" method="post" %}
[OpenAPI alibaba-wan-2-6-image](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/image-models/Alibaba-Cloud/alibaba-wan-2-6-image.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import json
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/images/generations",
    headers={"Authorization":"Bearer <YOUR_AIMLAPI_KEY>","Content-Type":"application/json"},
    data=json.dumps({
        "model": "alibaba/wan-2-6-image",
        "prompt": "Combine the images so the T-Rex is wearing a business suit, sitting in a cozy small café, drinking from the mug. Blur the background slightly to create a bokeh effect.",
        "image_urls": [
            "https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/t-rex.png",
            "https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/blue-mug.jpg"
        ]
    })
)

data = response.json()
print(data)
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const response = await fetch('https://api.aimlapi.com/v1/images/generations', {
  method: 'POST',
  headers: {
    Authorization: 'Bearer <YOUR_AIMLAPI_KEY>',
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    model: 'alibaba/wan-2-6-image',
    prompt:
      'Combine the images so the T-Rex is wearing a business suit, sitting in a cozy small café, drinking from the mug. Blur the background slightly to create a bokeh effect.',
    image_urls: [
      'https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/t-rex.png',
      'https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/blue-mug.jpg',
    ],
  }),
});
const data = await response.json();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "created": 1766084513473,
  "data": [
    {
      "url": "https://cdn.aimlapi.com/alpaca/1d/19/20251219/4564f4d6/83355458-4abb7102-799b-4ee9-be09-9504406a8194.png?Expires=1766170910&OSSAccessKeyId=LTAI5tRcsWJEymQaTsKbKqGf&Signature=LQsTgsFa4tsNUSjEqUefE1BkjMg%3D"
    }
  ],
  "meta": {
    "usage": {
      "credits_used": 63000
    }
  }
}
```

{% endcode %}

</details>