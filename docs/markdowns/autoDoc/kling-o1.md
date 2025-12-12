# Kling O1

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

Kling O1 is a family of image and video generation and editing models developed by Kling AI and available via fal.ai. The suite targets high-quality, photorealistic visual content creation across both images and videos, supporting vision-focused workflows.

Within this family, Kling Image O1 specializes in detailed, photorealistic image creation and editing, while the Kling Video O1 variants support generating and modifying videos from text prompts, reference images, or source videos. Common use cases include advertisements, promotional material, short clips, and social media content spanning tasks such as text-to-image, image-to-image, reference-to-video, image-to-video, and various video-to-video transformations.

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

def main():
    url = "https://api.aimlapi.com/v2/video/generations"
    payload = {
        "model": "klingai/video-o1-video-to-video-reference",
        "prompt": "A powerful, matte black jeep, its robust frame contrasting with the lush green surroundings, navigates a winding jungle road, kicking up small clouds of dust and loose earth from its tires.",
        "video_url": "https://storage.googleapis.com/falserverless/example_inputs/krea_wan_14b_v2v_input.mp4",
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
      model: 'klingai/video-o1-video-to-video-reference',
      prompt: 'A powerful, matte black jeep, its robust frame contrasting with the lush green surroundings, navigates a winding jungle road, kicking up small clouds of dust and loose earth from its tires.',
      video_url: 'https://storage.googleapis.com/falserverless/example_inputs/krea_wan_14b_v2v_input.mp4',
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
{'id': 'gen-1744193377-EXAMPLEID123456789', 'object': 'video.generation', 'model': 'klingai/video-o1-video-to-video-reference', 'created': 1744193377, 'status': 'processing', 'output_url': null, 'meta': {'prompt': 'A powerful, matte black jeep, its robust frame contrasting with the lush green surroundings, navigates a winding jungle road, kicking up small clouds of dust and loose earth from its tires.', 'video_url': 'https://storage.googleapis.com/falserverless/example_inputs/krea_wan_14b_v2v_input.mp4', 'duration_seconds': 8}, 'usage': {'input_tokens': 0, 'output_tokens': 0, 'total_tokens': 0}}
```

{% endcode %}

</details>

<!-- Generated from AA-228 -->