# Veo 3.1 Extend Video / Veo 3.1 Fast Extend Video

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `google/veo3-1-extend-video`
* `google/veo3-1-fast-extend-video`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/google/veo-3-1-extend-video-veo-3-1-fast-extend-video" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Veo 3.1 Extend Video and Veo 3.1 Fast Extend Video are video-to-video generation models for extending existing clips while maintaining the look, style, and motion characteristics of the source footage. They operate on input videos to continue scenes, preserving continuity in composition, pacing, and camera movement.

Both variants support optional audio generation, with audio-on and audio-off modes to either extend visuals only or produce synchronized audio alongside the new video segment. The Fast Extend configuration is optimized for quicker iterations and cost-efficient workflows, making it suitable for rapid experimentation and high-volume video extension pipelines.

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

{% openapi-operation spec="veo3-1-extend-video" path="/v2/video/generations" method="post" %}
[OpenAPI veo3-1-extend-video](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/Google/veo3-1-extend-video.json)
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
        "model": "google/veo3-1-extend-video",
        "video_url": "https://storage.googleapis.com/falserverless/example_inputs/wan_animate_input_video.mp4",
        "prompt": "A lone woman strides through the neon-drenched streets of Tokyo at night.  Her crimson dress, a vibrant splash of color against the deep blues and blacks of the cityscape, flows slightly with each step. A tailored black jacket, crisp and elegant, contrasts sharply with the dress's rich texture. Medium shot:  The city hums around her, blurred lights creating streaks of color in the background. Close-up:  The fabric of her dress catches the streetlight's glow, revealing a subtle silk sheen and the intricate stitching at the hem. Her black jacket’s subtle texture is visible – a fine wool perhaps, with a matte finish. The overall mood is one of quiet confidence and mystery, a vibrant woman navigating a bustling, nocturnal landscape. High resolution 4k."
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
      "model": "google/veo3-1-extend-video",
      "video_url": "https://storage.googleapis.com/falserverless/example_inputs/wan_animate_input_video.mp4",
      "prompt": "A lone woman strides through the neon-drenched streets of Tokyo at night.  Her crimson dress, a vibrant splash of color against the deep blues and blacks of the cityscape, flows slightly with each step. A tailored black jacket, crisp and elegant, contrasts sharply with the dress's rich texture. Medium shot:  The city hums around her, blurred lights creating streaks of color in the background. Close-up:  The fabric of her dress catches the streetlight's glow, revealing a subtle silk sheen and the intricate stitching at the hem. Her black jacket’s subtle texture is visible – a fine wool perhaps, with a matte finish. The overall mood is one of quiet confidence and mystery, a vibrant woman navigating a bustling, nocturnal landscape. High resolution 4k."
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
  'model': 'google/veo3-1-extend-video',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/google/veo3-1-extend-video/example-output.png',
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

<!-- Generated from AA-267 -->