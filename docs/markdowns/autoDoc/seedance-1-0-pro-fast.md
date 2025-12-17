# Seedance 1.0 Pro Fast

## API Schema

{% openapi-operation spec="seedance-1-0-pro-fast" path="/v2/video/generations" method="post" %}
[OpenAPI seedance-1-0-pro-fast](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/bytedance/seedance-1-0-pro-fast.json)
{% endopenapi-operation %}

{% openapi-operation spec="seedance-1-0-pro-fast" path="/v1/video/generations" method="post" %}
[OpenAPI seedance-1-0-pro-fast](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/bytedance/seedance-1-0-pro-fast.json)
{% endopenapi-operation %}

{% openapi-operation spec="seedance-1-0-pro-fast" path="/video/generations" method="post" %}
[OpenAPI seedance-1-0-pro-fast](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/video-models/bytedance/seedance-1-0-pro-fast.json)
{% endopenapi-operation %}

## Code Example

{% tabs %}{% tab title="Python" %}{% code overflow="wrap" %}

```python
import requests

response = requests.post(
    "https://api.aimlapi.com/v2/video/generations",
    headers={
        "Content-Type": "application/json",
        "Authorization": "Bearer <YOUR_API_KEY>",
    },
    json={
        "model": "bytedance/seedance-1-0-pro-fast",
        "prompt": "A menacing evil dragon appears in a distance above the tallest mountain, then rushes toward the camera with its jaws open, revealing massive fangs. We see it's coming."
      }
)

data = response.json()
print(data)
```

{% endcode %}{% endtab %}{% tab title="JavaScript" %}{% code overflow="wrap" %}

```javascript
async function main() {
  const response = await fetch('https://api.aimlapi.com/v2/video/generations', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer <YOUR_API_KEY>',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      "model": "bytedance/seedance-1-0-pro-fast",
      "prompt": "A menacing evil dragon appears in a distance above the tallest mountain, then rushes toward the camera with its jaws open, revealing massive fangs. We see it's coming."
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
  'model': 'bytedance/seedance-1-0-pro-fast',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/bytedance/seedance-1-0-pro-fast/example-output.png',
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

<!-- Generated from AA-182 -->