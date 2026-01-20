# Wan 2.6 – Text-to-Video

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `alibaba/wan-2-6-t2v`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/alibaba/wan-2-6-text-to-video" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Wan 2.6 – Text-to-Video is a generative video model developed by Alibaba (Wan) and provided through Alibaba Cloud’s Model Studio. It creates complete video clips from a single text prompt, focusing on high-quality rendering with coherent, cinematic-style motion throughout the sequence.

The model supports 720p and 1080p video output, making it suitable for tasks like concept visualization, cinematic prototyping, marketing assets, and creative content generation where smooth motion and visual consistency are important.

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

{% openapi-operation spec="alibaba-wan-2-6-t2v" path="/v2/video/generations" method="post" %}
[OpenAPI alibaba-wan-2-6-t2v](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/Alibaba-Cloud/alibaba-wan-2-6-t2v.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python

```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript

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
  'model': 'alibaba/wan-2-6-t2v',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/alibaba/wan-2-6-t2v/example-output.png',
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

<!-- Generated from AD-273 -->