# Kling 2.6 Pro image-to-video

# Kling 2.6 Pro image-to-video

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `klingai/video-v2-6-pro-image-to-video`
* `klingai/video-v2-6-pro-text-to-video`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/?model=klingai/video-v2-6-pro-image-to-video" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Kling 2.6 Pro is a next-generation cinematic video generation model from KlingAI, served via fal.ai. It is designed to produce smooth, realistic motion and highly detailed visuals, with native audio generation to create coherent audiovisual clips.

The model supports both image-to-video animation and text-to-video generation, making it suitable for promos, advertisements, social media content, and rapid video mockups. It operates over visual and audio modalities and is optimized for creative video synthesis workflows.

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

{% openapi-operation spec="kling-2-6-pro-image-to-video" path="/v2/video/generations" method="post" %}
{% endopenapi-operation %}

{% openapi-operation spec="kling-2-6-pro-image-to-video" path="/v1/video/generations" method="post" %}
{% endopenapi-operation %}

{% openapi-operation spec="kling-2-6-pro-image-to-video" path="/video/generations" method="post" %}
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

def main():
    url = "https://api.aimlapi.com/v2/video/generations"
    payload = {
        "model": "klingai/video-v2-6-pro-image-to-video",
        "prompt": "A jellyfish in the ocean",
        "image_url": "https://upload.wikimedia.org/wikipedia/commons/3/35/Maldivesfish2.jpg",
    }
    headers = {"Authorization": "Bearer <YOUR_API_KEY>", "Content-Type": "application/json"}

    response = requests.post(url, json=payload, headers=headers)
    print("Generation:", response.json())


if __name__ == "__main__":
    main()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const main = async () => {
  const response = await fetch('https://api.aimlapi.com/v2/video/generations', {
    method: 'POST',
    headers: {
      Authorization: 'Bearer <YOUR_API_KEY>',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      model: 'klingai/video-v2-6-pro-image-to-video',
      prompt: 'A jellyfish in the ocean',
      image_url: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Maldivesfish2.jpg',
    }),
  }).then((res) => res.json());

  console.log('Generation:', response);
};

main()
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json5
{'id': 'gen-video-1744193377-AbCdEfGhIjKl', 'object': 'video.generation', 'model': 'klingai/video-v2-6-pro-image-to-video', 'created': 1744193377, 'status': 'succeeded', 'output': {'video_url': 'https://cdn.aimlapi.com/video/gen-video-1744193377-AbCdEfGhIjKl.mp4', 'thumbnail_url': 'https://cdn.aimlapi.com/video/gen-video-1744193377-AbCdEfGhIjKl.jpg', 'duration_seconds': 5, 'has_audio': true}, 'usage': {'input_tokens': 0, 'output_tokens': 0, 'prompt_tokens': 0, 'completion_tokens': 0, 'total_tokens': 0}}
```

{% endcode %}

</details>

<!-- Generated from AA-232 -->