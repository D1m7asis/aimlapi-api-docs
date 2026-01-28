# DeepSeek-V3.2-Speciale

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `deepseek/deepseek-v3.2-speciale`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/deepseek/deepseek-v3.2-speciale" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

DeepSeek-V3.2-Speciale is an experimental reasoning-focused large language model developed by DeepSeek, designed around a dedicated thinking-only mode. It targets complex, multi-step reasoning tasks and workloads that require handling long contexts of up to 128K tokens, making it suitable for demanding analytical and planning scenarios.

The model works with text and code, offering improved reliability on challenging queries and support for advanced features such as tool calling and Chat Prefix/FIM-style completion as defined in the DeepSeek specification. It is primarily intended for experimentation and advanced reasoning use cases rather than broad, long-term production deployment.

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

{% openapi-operation spec="deepseek-v3.2-speciale" path="/v2/video/generations" method="post" %}
[OpenAPI deepseek-v3.2-speciale](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/DeepSeek/deepseek-v3.2-speciale.json)
{% endopenapi-operation %}

### Generate model responses for text and multi-modal inputs using the unified Responses API.

{% openapi-operation spec="deepseek-v3.2-speciale" path="/v1/responses" method="post" %}
[OpenAPI deepseek-v3.2-speciale](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/text-models-llm/DeepSeek/deepseek-v3.2-speciale.json)
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
response = requests.post(
    "https://api.aimlapi.com/v1/chat/completions",
    headers={
      "Authorization":"Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type":"application/json"
    },
    data=json.dumps({
     "model": "deepseek/deepseek-v3.2-speciale",
     "messages": [
        {
          "role": "user",
          "content": "How to learn javascript?"
        }
      ],
      "stream": False,
    })
)
data = response.json()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const response = await fetch('https://api.aimlapi.com/v1/chat/completions', {
    method: 'POST',
    headers: {
      "Authorization": "Bearer <YOUR_AIMLAPI_KEY>",
      "Content-Type": "application/json"
    },
    body: JSON.stringify({
      "model": "deepseek/deepseek-v3.2-speciale",
      "messages": [
          {
            "role": "user",
            "content": "How to learn javascript?"
          }
        ],
        "stream": false,
});
const data = await response.json();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "model": "deepseek/deepseek-v3.2-speciale"
}
```

{% endcode %}

</details>