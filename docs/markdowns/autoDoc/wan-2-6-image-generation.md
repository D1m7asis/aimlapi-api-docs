# Wan 2.6 – Image generation

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `alibaba/wan-2-6-image`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/alibaba/wan-2-6-image-generation" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Wan 2.6 – Image generation is an image-focused model developed by Alibaba that supports both text-to-image and image-to-image workflows. It is designed to generate new images from natural language prompts and to apply targeted edits to existing visuals.

The model can work with mixed text and image inputs, making it suitable for use cases like style transfer, compositing multiple reference images, or refining details in a scene while preserving the overall layout. This flexibility enables creative, multi-step image-conditioning pipelines for design, illustration, and content creation tasks.

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

Generate images from prompts and optional parameters (size, format, etc.).

{% openapi-operation spec="alibaba-wan-2-6-image" path="/v1/images/generations" method="post" %}
[OpenAPI alibaba-wan-2-6-image](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/image-models/Alibaba-Cloud/alibaba-wan-2-6-image.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v1/images/generations",
    headers={
        "Content-Type":"application/json", 
        "Authorization":"Bearer <YOUR_AIMLAPI_KEY>",
    },
    json={
        "model":"alibaba/wan-2-6-image",
        "prompt": "A T-Rex relaxing on a beach, lying on a sun lounger and wearing sunglasses."
    }
)

data = response.json()
print(data)
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
async function main() {
  const response = await fetch('https://api.aimlapi.com/v1/images/generations', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer <YOUR_AIMLAPI_KEY>',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      model: 'alibaba/wan-2-6-image',
      prompt: 'A T-Rex relaxing on a beach, lying on a sun lounger and wearing sunglasses.',
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
  'model': 'alibaba/wan-2-6-image',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/alibaba/wan-2-6-image/example-output.png',
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

<!-- Generated from AD-274 -->