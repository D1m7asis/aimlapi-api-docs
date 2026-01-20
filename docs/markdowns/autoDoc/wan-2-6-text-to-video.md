# Wan 2.6 – Text-to-Video

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `alibaba/wan-2-6-t2v`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/alibaba/wan-2-6-t2v" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Wan 2.6 – Text-to-Video is a text-to-video generation model that creates high-quality videos from a single text prompt. It is designed to produce coherent, cinematic-style motion, making it suitable for visually rich storytelling and concept visualization.

The model supports 720p and 1080p outputs and operates over text and video modalities, targeting text-to-video generation tasks where temporal consistency and visual detail are important.

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

### Submit a video generation request (create a new job).

{% openapi-operation spec="alibaba-wan-2-6-t2v" path="/v2/video/generations" method="post" %}
[OpenAPI alibaba-wan-2-6-t2v](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/Alibaba-Cloud/alibaba-wan-2-6-t2v.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

def main():
    url = "https://api.aimlapi.com/v2/video/generations"
    payload = {
        "model": "alibaba/wan-2-6-t2v",
        "prompt": "A DJ on the stand is playing, around a World War II battlefield, lots of explosions, thousands of dancing soldiers, between tanks shooting, barbed wire fences, lots of smoke and fire, black and white old video: hyper realistic, photorealistic, photography, super detailed, very sharp, on a very white background"
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
      model: 'alibaba/wan-2-6-t2v',
      prompt: 'A DJ on the stand is playing, around a World War II battlefield, lots of explosions, thousands of dancing soldiers, between tanks shooting, barbed wire fences, lots of smoke and fire, black and white old video: hyper realistic, photorealistic, photography, super detailed, very sharp, on a very white background',
    }),
  }).then((res) => res.json());
  console.log('Generation:', response);
};
main();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "id": "N36BMqdLR8Zm5WgE68xwK",
  "status": "completed",
  "video": {
    "url": "https://cdn.aimlapi.com/albatrosse/1d/31/20251219/7f086db1/8d5ff143-8dae-40cc-91bc-45063bf14347.mp4?Expires=1766170840&OSSAccessKeyId=LTAI5tKPD3TMqf2Lna1fASuh&Signature=tzjTHpsJnznD1rCD2AGK%2BOekI7M%3D"
  }
}
```

{% endcode %}

</details>

<!-- Generated from AD-273 -->