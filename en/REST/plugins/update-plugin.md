---
title: Update Plug-in
description: 'Updates an imported plug-in in Kintone.'
weight: 500
tags: []
product: kintone
aliases:
  - "/en/id/6c757147cfb0fbb14509b61b/"
---

Updates an imported plug-in in the Kintone environment.

| Method | PUT |
| URL | https://{subdomain}.kintone.com/k/v1/plugin.json |
| Authentication | [Password Authentication](/docs/common/authentication/#password-authentication), [Session Authentication](/docs/common/authentication/#session-authentication) |
| Content-Type | application/json |


### Permissions {#permissions}

- Only Kintone Administrators can use this API.

### Request Parameters {#request-parameters}

| Parameter | Type | Required | Description |
| :-- | :-- | :-- | :-- |
| id | String | Yes | The ID of the plug-in to be updated. |
| fileKey | String | Yes | The fileKey representing an uploaded file. Use the following API to upload the file and retrieve the fileKey:<br />[Upload File](/docs/kintone/rest-api/files/upload-file/) |

### Sample Request {#sample-request}

#### [JavaScript using kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) {#javascript-using-kintone-api}

```js
var body = {
  'id': 'djmhffjhfgmebgnmcggopedaofckljlj',
  'fileKey': 'c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6'
};

kintone.api(kintone.api.url('/k/v1/plugin.json', true), 'PUT', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

#### curl Sample {#curl-sample}

```shell
curl -X PUT 'https://{subdomain}.kintone.com/k/v1/plugin.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "id": "djmhffjhfgmebgnmcggopedaofckljlj", "fileKey": "c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6"
  }'
```

### Response Parameters {#response-parameters}

| Parameter | Type | Description |
| :-- | :-- | :-- |
| id | String | The plug-in ID of the updated plug-in. |
| version | String | The version number of the plug-in. |

### Sample Response {#sample-response}

```json
```
