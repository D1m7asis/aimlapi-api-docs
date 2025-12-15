# Kling Video O1 — Reference to Video (Kling AI)

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `klingai/video-o1-reference-to-video`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=klingai/video-o1-reference-to-video" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Kling Video O1 — Reference to Video is a video generation model developed by Kling AI that creates short clips from a sequence of reference images and a text prompt. It is designed to translate visual references and textual instructions into coherent video outputs while preserving style, character identity, and visual consistency.

The model supports video, vision, and text modalities, and is particularly suited for use cases such as promotional clips, character-driven content, and stylized sequences where maintaining a stable look across frames is important.

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

{% openapi-operation spec="v2.1-standard-image-to-video-pair" path="/v2/generate/video/kling/generation" method="get" %}
[OpenAPI v2.1-standard-image-to-video-pair](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/kling/v2.1-standard-image-to-video-pair.json)
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
        "model": "klingai/video-o1-reference-to-video",
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
      "model": "klingai/video-o1-reference-to-video",
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
  'model': 'klingai/video-o1-reference-to-video',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/klingai/video-o1-reference-to-video/example-output.png',
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

<!-- Generated from AA-255 -->