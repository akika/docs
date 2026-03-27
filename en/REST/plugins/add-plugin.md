---
title: Install Plug-in
description: 'Imports a plug-in into Kintone.'
weight: 400
tags: []
product: kintone
aliases:
  - "/en/id/802755caa3777330aa26f910/"
---

Imports a plug-in into Kintone.

{{< vtable >}}
| Method | POST |
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
| fileKey | String | Yes | The fileKey representing an uploaded file. Use the following API to upload the file and retrieve the fileKey:<br>[Upload File](/docs/kintone/rest-api/files/upload-file/) |

### Sample Request {#sample-request}

#### [JavaScript using kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) {#javascript-using-kintone-api}
<!-- eslint-disable strict -->
```js
var body = {
  'fileKey': 'c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6'
};

kintone.api(kintone.api.url('/k/v1/plugin.json', true), 'POST', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

#### curl Sample {#curl-sample}

```shell
curl -X POST 'https://{subdomain}.kintone.com/k/v1/plugin.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "fileKey": "c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6"
  }'
```

### Response Parameters {#response-parameters}

| Parameter | Type | Description |
| :-- | :-- | :-- |
| id | String | The installed plug-in ID. |
| version | String | The version number of the plug-in. |

### Sample Response {#sample-response}

```json
{
  "id": "djmhffjhfgmebgnmcggopedaofckljlj",
  "version": "1.0.0"
}
```
