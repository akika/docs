---
title: Uninstall Plug-in
description: 'Uninstalls a plug-in from the Kintone environment.'
weight: 600
tags: []
product: kintone
aliases:
  - "/en/id/de82183fad700dac84f1e0fa/"
---

Uninstalls a plug-in from the Kintone environment.

{{< vtable >}}
| Method | DELETE |
| URL | https://{subdomain}.kintone.com/k/v1/plugin.json |
| Authentication | [Password Authentication](/docs/common/authentication/#password-authentication), [Session Authentication](/docs/common/authentication/#session-authentication) |
| Content-Type | application/json |
{{< /vtable >}}

{{ toc }}

### Permissions {#permissions}

- Only Kintone Administrators can use this API.

### Request Parameters {#request-parameters}

| Parameter | Type | Required | Description |
| :-- | :-- | :-- | :-- |
| id | String | Yes | The ID of the plug-in. |

### Sample Request {#sample-request}

#### [JavaScript using kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) {#javascript-using-kintone-api}
<!-- eslint-disable strict -->
```js
var body = {
  'id': 'djmhffjhfgmebgnmcggopedaofckljlj'
};

kintone.api(kintone.api.url('/k/v1/plugin.json', true), 'DELETE', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

#### curl Sample {#curl-sample}

```shell
curl -X DELETE 'https://{subdomain}.kintone.com/k/v1/plugin.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "id": "djmhffjhfgmebgnmcggopedaofckljlj"
  }'
```

### Response Parameters {#response-parameters}

An empty JSON object will be returned.

### Sample Response {#sample-response}

```json
{}
```
