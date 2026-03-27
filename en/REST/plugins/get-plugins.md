---
title: Get Installed Plug-ins
description: 'Gets the list of plug-ins imported into Kintone.'
weight: 100
tags: []
product: kintone
aliases:
  - "/en/id/cccd73361f8b0eb88505a7d5/"
---

Gets the list of plug-ins imported into Kintone.

| Method | GET |
| URL | https://{subdomain}.kintone.com/k/v1/plugins.json |
| Authentication | [Password Authentication](/docs/common/authentication/#password-authentication), [Session Authentication](/docs/common/authentication/#session-authentication) |
| Content-Type | application/json (not needed if specifying the query with a query string) |


### Permissions {#permissions}

- No permissions are needed.

### Request Parameters {#request-parameters}

| Parameter | Type | Required | Description |
| :-- | :-- | :-- | :-- |
| offset | Integer |  | The number of plug-ins to skip from the list of installed plug-ins.<br />If ignored, this value is 0. |
| limit | Integer |  | The maximum number of plug-ins to retrieve.<br />Must be between 1 and 100.<br />The default number is 100. |
| ids | Array of strings |  | The plug-in ids. The maximum limit of ids that can be specified is 100.<br />If `null` or an empty array is specified, this parameter will be ignored, and a list of plug-ins will be returned. |

### Sample Request {#sample-request}

#### [JavaScript using kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) {#using-kintone-rest-api-request}

**Sample when the `ids` parameter is ignored**


```js
var body = {
  'offset': 1,
  'limit': 3
};
kintone.api(kintone.api.url('/k/v1/plugins.json', true), 'GET', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

**Sample when the `ids` parameter is specified**


```js
var body = {
  'ids': ['nldmflmpgchoodanjholbdewsdjkhpban', 'jdkslfbeksonbmvkelsodkfyquxnsja']
};
kintone.api(kintone.api.url('/k/v1/plugins.json', true), 'GET', body, function(resp) {
  // success
  console.log(resp);
}, function(error) {
  // error
  console.log(error);
});
```

#### curl Sample {#curl-sample}

**Sample when the `ids` parameter is ignored**

```shell
curl -X GET 'https://{subdomain}.kintone.com/k/v1/plugins.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "offset": 1, "limit": 3
  }'
```

**Sample when the `ids` parameter is specified**

```shell
curl -X GET 'https://{subdomain}.kintone.com/k/v1/plugins.json' \
  -H 'X-Cybozu-Authorization:{AuthorizationCode}' \
  -H 'Content-Type: application/json' \
  -d '{
    "ids": ["nldmflmpgchoodanjholbdewsdjkhpban", "jdkslfbeksonbmvkelsodkfyquxnsja"]
  }'

### Response Parameters {#response-parameters}

| Parameter | Type | Description |
| :-- | :-- | :-- |
| plugins | Array of Objects | A list of plug-ins added to the App.<br />Plug-ins are listed in descending order of the datetime they are added.|
| plugins[].id | String | The plug-in ID. |
| plugins[].name | String | The name of the plug-in. |
| plugins[].isMarketPlugin | Boolean | States whether or not the plug-in is a Marketplace plug-in.<ul><li>`true`: The plug-in is a Marketplace plug-in.</li><li>`false`: The plug-in is not a Marketplace plug-in.</li></ul> |
| plugins[].version | String | The version number of the plug-in. |
| plugins[].description | String | The Plug-in description. If there is no description, an empty string will be returned. |

### Sample Response {#sample-response}

```json,
        {
          "id":"ejgcopfamifdhmkafjgidfmgjdmiaplf",
          "name":"Plugin 2",
          "isMarketPlugin":false,
          "version":"2",
          "description": "Description of Plugin 2"
        },
        {
          "id":"fdeplpmkengkldpdlaiegpokgmaabkkb",
          "name":"Plugin 3",
          "isMarketPlugin":false,
          "version":"4.5.1",
          "description": "Description of Plugin 3"
          }
    ]
}
```
