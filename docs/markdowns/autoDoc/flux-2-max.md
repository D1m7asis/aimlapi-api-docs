# FLUX.2 Max

## API Schema

{% openapi-operation spec="flux-2-max" path="/v1/images/generations" method="post" %}
[OpenAPI flux-2-max](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/image-models/black-forest-labs/flux-2-max.json)
{% endopenapi-operation %}

{% openapi-operation spec="flux-2-max" path="/images/generations" method="post" %}
[OpenAPI flux-2-max](https://raw.githubusercontent.com/aimlapi/api-docs/main/docs/api-references/image-models/black-forest-labs/flux-2-max.json)
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
        "model":"blackforestlabs/flux-2-max",
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
      model: 'blackforestlabs/flux-2-max',
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
  'model': 'blackforestlabs/flux-2-max',
  'data': [
    {
      'url': 'https://cdn.aimlapi.com/generated-images/blackforestlabs/flux-2-max/example-output.png',
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

<!-- Generated from AA-265 -->