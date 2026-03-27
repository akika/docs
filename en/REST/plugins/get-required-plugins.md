---
title: Get Required Plug-ins
description: 'Gets the list of plug-ins that have been deleted from Kintone, but have already been added to Apps.'
weight: 200
tags: []
product: kintone
aliases:
  - "/en/id/b37c7fed50c6e2bc8aed0c04/"
---

Gets the list of plug-ins that have been deleted from Kintone, but have already been added to Apps.  
This can occur when a plug-in is installed, added to an App, and then proceeded to be uninstalled from the Kintone environment.

| Method | GET |
| URL | https://{subdomain}.kintone.com/k/v1/plugins/required.json |
| Authentication | [Password Authentication](/docs/common/authentication/#password-authentication), [Session Authentication](/docs/common/authentication/#session-authentication) |
| Content-Type | application/json (not needed if specifying the query with a query string) |


### Permissions {#permissions}

- No permissions are needed.

### Request Parameters {#request-parameters}

| Parameter | Type | Required | Description |
| :-- | :-- | :-- | :-- |
| offset | Integer |  | The number of plug-ins to skip from the list of required plug-ins.<br />If ignored, this value is 0. |
| limit | Integer |  | The maximum number of plug-ins to retrieve.<br />Must be between 1 and 100.<br />The default number is 100. |

### Sample Request {#sample-request}

#### [JavaScript using kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) {#using-kintone-rest-api-request}


```js
var body = {
  'offset': 1,
  'limit': 3
};
kintone.api(kintone.api.url('/k/v1/plugins/required.json', true), 'GET', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

#### curl Sample {#curl-sample}

```shell
curl -X GET 'https://{subdomain}.kintone.com/k/v1/plugins/required.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "offset": 1, "limit": 3
  }'
```

### Response Parameters {#response-parameters}

| Parameter | Type | Description |
| :-- | :-- | :-- |
| plugins | Array of Objects | A list of Plug-ins that needs to be installed. |
| plugins[].id | String | The Plugin ID. |
| plugins[].name | String | The name of the Plugin. |
| plugins[].isMarketPlugin | Boolean | States whether or not the plug-in is a Marketplace plug-in.<ul><li>`true`: The plug-in is a Marketplace plug-in.</li><li>`false`: The plug-in is not a Marketplace plug-in.</li></ul>|

### Sample Response {#sample-response}

```json,
        {
          "id":"ejgcopfamifdhmkafjgidfmgjdmiaplf",
          "name":"Plugin 2",
          "isMarketPlugin":false,
        },
        {
          "id":"fdeplpmkengkldpdlaiegpokgmaabkkb",
          "name":"Plugin 3",
          "isMarketPlugin":false,
          }
    ]
}
```
