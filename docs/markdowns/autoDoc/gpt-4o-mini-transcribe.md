# GPT-4o-Mini-Transcribe

{% columns %}
{% column width="66.66666666666666%" %}
{% hint style="info" %}
This documentation is valid for the following list of our models:

* `openai/gpt-4o-mini-transcribe`
{% endhint %}
{% endcolumn %}

{% column width="33.33333333333334%" %}
<a href="https://aimlapi.com/app/openai/gpt-4o-mini-transcribe" class="button primary">Try in Playground</a>
{% endcolumn %}
{% endcolumns %}

## Model Overview

GPT-4o-Mini-Transcribe is a compact speech-to-text model that converts spoken audio into written text, with support for both direct transcription and translation of audio into English. It is optimized for efficient, high-quality recognition across a range of common audio formats and streaming scenarios.

The model is designed for audio and text modalities and is suited to tasks such as speech-to-text transcription, audio transcription workflows, and automatic audio translation. Developed by OpenAI, it targets use cases where low-latency, lightweight transcription is needed while still handling multiple languages and varied input conditions.

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

### Create a speech-to-text job (upload or reference audio).

{% openapi-operation spec="gpt-4o-mini-transcribe" path="/v1/stt/create" method="post" %}
[OpenAPI gpt-4o-mini-transcribe](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/speech-models/OpenAI/gpt-4o-mini-transcribe.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import time
import requests

base_url = "https://api.aimlapi.com/v1"
# Insert your AIML API Key instead of <YOUR_AIMLAPI_KEY>:
api_key = "<YOUR_AIMLAPI_KEY>"

# Creating and sending a speech-to-text conversion task to the server
def create_stt():
    url = f"{base_url}/stt/create"
    headers = {
        "Authorization": f"Bearer {api_key}", 
    }

    data = {
        "model": "openai/gpt-4o-mini-transcribe",
        "url": "https://audio-samples.github.io/samples/mp3/blizzard_primed/sample-0.mp3"
    }
 
    response = requests.post(url, json=data, headers=headers)
    
    if response.status_code >= 400:
        print(f"Error: {response.status_code} - {response.text}")
    else:
        response_data = response.json()
        print(response_data)
        return response_data

# Requesting the result of the task from the server using the generation_id
def get_stt(gen_id):
    url = f"{base_url}/stt/{gen_id}"
    headers = {
        "Authorization": f"Bearer {api_key}", 
    }
    response = requests.get(url, headers=headers)
    return response.json()
    
# First, start the generation, then repeatedly request the result from the server every 10 seconds.
def main():
    stt_response = create_stt()
    gen_id = stt_response.get("generation_id")



    if gen_id:
        start_time = time.time()

        timeout = 600
        while time.time() - start_time < timeout:
            response_data = get_stt(gen_id)

            if response_data is None:
                print("Error: No response from API")
                break
        
            status = response_data.get("status")

            if status == "waiting" or status == "active":
                print("Still waiting... Checking again in 10 seconds.")
                time.sleep(10)
            else:
                print("Processing complete:/n", response_data["result"]["text"])
                return response_data
   
        print("Timeout reached. Stopping.")
        return None     


if __name__ == "__main__":
    main()
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
const axios = require("axios");

const baseUrl = "https://api.aimlapi.com/v1";
// Insert your AIML API Key instead of <YOUR_AIMLAPI_KEY>:
const apiKey = "<YOUR_AIMLAPI_KEY>";

// Creating and sending a speech-to-text conversion task to the server
async function createStt() {
  const url = `${baseUrl}/stt/create`;

  const headers = {
    Authorization: `Bearer ${apiKey}`,
  };

  const data = {
    model: "openai/gpt-4o-mini-transcribe",
    url: "https://audio-samples.github.io/samples/mp3/blizzard_primed/sample-0.mp3",
  };

  try {
    const response = await axios.post(url, data, { headers });
    console.log(response.data);
    return response.data;
  } catch (err) {
    console.error("Error:", err.response?.status, err.response?.data);
    return null;
  }
}

// Requesting the result of the task from the server using the generation_id
async function getStt(genId) {
  const url = `${baseUrl}/stt/${genId}`;

  const headers = {
    Authorization: `Bearer ${apiKey}`,
  };

  try {
    const response = await axios.get(url, { headers });
    return response.data;
  } catch (err) {
    console.error("Error fetching STT status:", err.response?.data);
    return null;
  }
}

// Polling logic
async function main() {
  const sttResponse = await createStt();
  if (!sttResponse) return;

  const genId = sttResponse.generation_id;
  if (!genId) {
    console.error("No generation_id returned");
    return;
  }

  const timeoutMs = 600_000; // 10 minutes
  const pollIntervalMs = 10_000;

  console.log("Generation started. Polling every 10 seconds...");

  const startTime = Date.now();

  while (Date.now() - startTime < timeoutMs) {
    const responseData = await getStt(genId);

    if (!responseData) {
      console.log("Error: No response from API");
      return;
    }

    const status = responseData.status;

    if (status === "waiting" || status === "active") {
      console.log("Still waiting... Checking again in 10 seconds.");
      await new Promise((r) => setTimeout(r, pollIntervalMs));
    } else {
      console.log("Processing complete:\n", responseData.result.text);
      return responseData;
    }
  }

  console.log("Timeout reached. Stopping.");
  return null;
}

main();
```

{% endcode %}{% endtab %}{% endtabs %}

<details>

<summary>Response</summary>

{% code overflow="wrap" %}

```json
{
  "model": "openai/gpt-4o-mini-transcribe"
}
```

{% endcode %}

</details>