---
title: Get Plug-in Apps
description: 'Gets Apps that have the specified plug-In added.'
weight: 300
tags: []
product: kintone
aliases:
  - "/en/id/8de597953d50849caa37b659/"
---

Gets Apps that have the specified plug-in added.

| Method | GET |
| URL | https://{subdomain}.kintone.com/k/v1/plugin/apps.json |
| Authentication | [Password Authentication](/docs/common/authentication/#password-authentication), [Session Authentication](/docs/common/authentication/#session-authentication) |
| Content-Type | application/json (not needed if specifying the query with a query string) |


### Permissions {#permissions}

- Only Kintone Administrators can use this API.

### Request Parameters {#request-parameters}

| Parameter | Type | Required | Description |
| :-- | :-- | :-- | :-- |
| id | String | Yes | The ID of the plug-in. |
| offset | Integer |  | The number of plug-ins to skip from the list of plug-ins.<br />If ignored, this value is 0. |
| limit | Integer |  | The maximum number of plug-ins to retrieve.<br />Must be between 1 and 500.<br />The default number is 100. |

### Sample Request {#sample-request}

#### [JavaScript using kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) {#using-kintone-rest-api-request}


```js
var body = {
  'id': 'djmhffjhfgmebgnmcggopedaofckljlj',
  'offset': 1,
  'limit': 3
};
kintone.api(kintone.api.url('/k/v1/plugin/apps.json', true), 'GET', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

#### curl Sample {#curl-sample}

```shell
curl -X GET 'https://{subdomain}.kintone.com/k/v1/plugin/apps.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "id": "djmhffjhfgmebgnmcggopedaofckljlj", "offset": 1, "limit": 3
  }'
```

### Response Parameters {#response-parameters}

| Parameter | Type | Description |
| :-- | :-- | :-- |
| apps | Array of Objects | A list of objects containing the plug-in ID and name.<br />Objects are listed in ascending order of their App IDs. |
| apps[].id | String | The App ID. |
| apps[].name | String | The name of the App. |

### Sample Response {#sample-response}

```json,
        {
            "id": "2",
            "name": "App 2"
        },
        {
            "id": "3",
            "name": "App 3"
        }
    ]
}
```
