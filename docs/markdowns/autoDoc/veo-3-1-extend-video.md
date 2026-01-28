# Veo 3.1 Extend Video

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `google/veo3-1-extend-video`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/google/veo3-1-extend-video" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Veo 3.1 Extend Video is a video-to-video generation model for lengthening existing clips while maintaining consistent style, pacing, and motion. It is designed to take a source video and continue the scene in a way that visually matches the original material.

Developed by Google, the model supports both video-only and video-with-audio extension workflows, allowing you to generate synchronized audio for the new segment or keep the extension silent. It is well suited for extending scenes, shots, or short clips in content creation, editing, and post-production pipelines where seamless continuity is important.

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

{% openapi-operation spec="veo3-1-extend-video" path="/v2/video/generations" method="post" %}
[OpenAPI veo3-1-extend-video](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/Google/veo3-1-extend-video.json)
{% endopenapi-operation %}

### Retrieve the generated video from the server

After sending a request for video generation, this task is added to the queue. This endpoint lets you check the status of a video generation task using its `generation_id`, obtained from the endpoint described above.\
If the video generation task status is `complete`, the response will include the final result — with the generated video URL and additional metadata.

{% openapi-operation spec="universal-video-endpoint-fetch" path="/v2/video/generations" method="get" %}
[OpenAPI universal-video-endpoint-fetch](https://raw.githubusercontent.com/aimlapi/api-docs/refs/heads/main/docs/api-references/video-models/universal-video-fetch.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests
def main():
    url = "https://api.aimlapi.com/v2/video/generations"
    payload = {
        "model": "google/veo3-1-extend-video",
        "video_url": "https://storage.googleapis.com/falserverless/model_tests/video_models/1_video.mp4",
        "prompt": "A person walks on frozen ice"
    }
    headers = {
        "Authorization": "Bearer YOUR_API_KEY",
        "Content-Type": "application/json"
    }
    response = requests.post(url, json=payload, headers=headers)
    response.raise_for_status()
    print("Generation:", response.json())
if __name__ == "__main__":
    main()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const main = async () => {
  const response = await fetch("https://api.aimlapi.com/v2/video/generations", {
    method: "POST",
    headers: {
      Authorization: "Bearer YOUR_API_KEY",
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      model: "google/veo3-1-extend-video",
      video_url: "https://storage.googleapis.com/falserverless/model_tests/video_models/1_video.mp4",
      prompt: "A person walks on frozen ice"
    }),
  });
  const result = await response.json();
  console.log("Generation:", result);
};
main().catch(console.error);
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "id": "YJaGE8Zb_9U1iecnwofXF",
  "status": "completed",
  "video": {
    "url": "https://cdn.aimlapi.com/flamingo/files/b/0a878f1c/QY1rfJ1BoMMuHc7dmQrgJ_ab50e6b79cc6494984698585894a93ee.mp4"
  }
}
```

{% endcode %}

</details>