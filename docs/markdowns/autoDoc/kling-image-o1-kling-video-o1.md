# Kling Image O1 / Kling Video O1

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `klingai/image-o1`
* `klingai/video-o1-reference-to-video`
* `klingai/video-o1-image-to-video`
* `klingai/video-o1-video-to-video-edit`
* `klingai/video-o1-video-to-video-reference`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=klingai/image-o1" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Kling Image O1 is a high-quality image generation and editing model from Kling AI, accessible via the fal ai platform. It is optimized for photorealistic people, product photography, and stylized scenes, making it suitable for marketing visuals, e-commerce assets, and creative design workflows.

Kling Video O1 is a family of video models designed for reference-to-video, image-to-video, and video-to-video editing tasks. It targets ads, promos, short clips, and social content, producing smooth motion and maintaining consistent style and identity across frames for professional-looking video outputs.

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

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/images/generations",
    headers={"Authorization":"Bearer <YOUR_AIMLAPI_KEY>","Content-Type":"application/json"},
    data=json.dumps({
        "model": "klingai/image-o1",
        "prompt": "Combine the images so the T-Rex is wearing a business suit, sitting in a cozy small café, drinking from the mug. Blur the background slightly to create a bokeh effect.",
        "image_urls": [
            "https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/t-rex.png",
            "https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/blue-mug.jpg",
        ],
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
      "model": "klingai/image-o1",
      "prompt": "Combine the images so the T-Rex is wearing a business suit, sitting in a cozy small café, drinking from the mug. Blur the background slightly to create a bokeh effect.",
      "image_urls": [
        "https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/t-rex.png",
        "https://raw.githubusercontent.com/aimlapi/api-docs/main/reference-files/blue-mug.jpg",
      ],

    })
});

const data = await response.json();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json5
{
  'created': 1733915540,
  'data': [
    {
      'b64_json': null,
      'url': 'https://aimlapi-public-prod.s3.amazonaws.com/kling/image-o1/generated-image-example.png',
      'revised_prompt': 'Combine the provided images so that the T-Rex is wearing a business suit and sitting in a cozy small café, drinking from the blue mug. Apply a subtle background blur to create a warm bokeh effect while keeping the T-Rex and mug in sharp focus.'
    }
  ],
  'model': 'klingai/image-o1',
  'object': 'image',
  'usage': {
    'prompt_tokens': 0,
    'completion_tokens': 0,
    'total_tokens': 0
  }
}
```

{% endcode %}

</details>

<!-- Generated from AA-228 -->