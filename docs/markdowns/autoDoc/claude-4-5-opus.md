# Claude 4.5 Opus

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `anthropic/claude-opus-4-5`
  {% endhint %}
  {% endcolumn %}

{% column width="33.33333333333334%" %} <a href="https://aimlapi.com/app/?model=claude-opus-4-5-20251101" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

Claude 4.5 Opus is Anthropic’s flagship large language model designed for complex agents and advanced coding scenarios. It provides high intelligence, strong reasoning capabilities, and support for large context windows, making it suitable for demanding production workloads.

The model supports text, code, and vision modalities, with up to 200,000 tokens of context and is optimized for text-to-text and image-to-text (vision) tasks. It is developed and maintained by Anthropic and is intended for applications that require reliable, high-capacity multimodal understanding.
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
If you need a more detailed walkthrough for setting up your development environment and making a request step-by-step, feel free to use our **Quickstart guide**:  
https://docs.aimlapi.com/quickstart/setting-up
{% endhint %}

</details>

# API Schema
>Здесь вставить схему OpenAPI


## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

``python
import asyncio
from anthropic import Anthropic

client = Anthropic(
    base_url="https://api.aimlapi.com/",
    auth_token="<YOUR_API_KEY>",
)


def main():
    message = client.messages.create(
        model="anthropic/claude-opus-4-5",
        max_tokens=2048,
        system="You are an AI assistant who knows everything.",
        messages=[
            {
                "role": "user",
                "content": "Hello, Claude",
            }
        ],
    )

    print("Message:", message.content)


if __name__ == "__main__":
    main()
``

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

``javascript
const Anthropic = require('@anthropic-ai/sdk');

const api = new Anthropic({
  baseURL: 'https://api.aimlapi.com/',
  authToken: '<YOUR_API_KEY>',
});

const main = async () => {
  const message = await api.messages.create({
    model: 'anthropic/claude-opus-4-5',
    max_tokens: 2048,
    system: 'You are an AI assistant who knows everything.',
    messages: [
      {
        role: 'user',
        content: 'Tell me, why is the sky blue?',
      },
    ],
  });

  console.log('Message:', message);
};

main();
``

{% endcode %}{% endtab %}{% endtabs %}Done!