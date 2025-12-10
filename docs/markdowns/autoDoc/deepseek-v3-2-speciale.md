# DeepSeek-V3.2-Speciale

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `deepseek/deepseek-v3.2-speciale`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %} <a href="https://aimlapi.com/app/deepseek/deepseek-v3.2-speciale" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

DeepSeek-V3.2-Speciale is an experimental large language model from DeepSeek, focused on advanced reasoning and long-context dialogue. It operates primarily in a thinking-only mode to improve accuracy on complex queries and supports contexts up to 128,000 tokens.

The model is optimized for chat-completion style interactions over text and code, including support for tool calling and Chat Prefix/FIM completion according to DeepSeek’s specification. It is exposed as a special-purpose endpoint with limited availability, making it suitable for targeted high-difficulty reasoning workloads.
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

# API Schema
> Здесь вставить схему OpenAPI


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

```json5
{'id': 'chatcmpl-deepseek-v3-2-speciale-example', 'object': 'chat.completion', 'choices': [{'index': 0, 'finish_reason': 'stop', 'logprobs': null, 'message': {'role': 'assistant', 'content': 'To learn JavaScript effectively, start with the basics of variables, functions, and control flow using a beginner-friendly tutorial. Then build small projects in the browser (like a todo list or a simple game), read other people’s code, and practice regularly. Use MDN Web Docs as a reference, and gradually explore modern topics such as ES6 features, async/await, and working with APIs.', 'refusal': null}}], 'created': 1744193377, 'model': 'deepseek/deepseek-v3.2-speciale', 'usage': {'prompt_tokens': 18, 'completion_tokens': 88, 'total_tokens': 106}}
```

{% endcode %}

</details>Generated from AD-242