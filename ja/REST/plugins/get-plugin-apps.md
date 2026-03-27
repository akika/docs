---
title: "プラグインを追加しているアプリの一覧を取得する"
description: "プラグインを追加しているアプリ情報の一覧を取得します。"
tocEndLevel: 4
weight: 300
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/d756f228bad9ca044866aed0/"
---

プラグインを追加しているアプリ情報の一覧を取得します。




| HTTPメソッド | GET |
| URL | https\://sample.cybozu.com/k/v1/plugin/apps.json |
| 認証 | [パスワード認証](/id/edae2a9d04c6e7d0afffda3a/#password), [セッション認証](/id/edae2a9d04c6e7d0afffda3a/#session) |
| Content-Type | 不要（リクエストボディにパラメーターを含める場合はapplication/json）|



### リクエストパラメーター {#request-parameters}

| パラメーター名 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| id | 文字列 | 必須 | プラグインID |
| offset | 数値または文字列 | 省略可 | 取得した一覧からスキップする数。<br />省略すると、0が設定されます。 |
| limit | 数値または文字列 | 省略可 | 取得するアプリ数の上限。<br />1から500までの数値を指定できます。<br />省略すると、100が設定されます。 |

### レスポンスプロパティ {#response-properties}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| apps | 配列（オブジェクト） | プラグインが追加されているアプリ情報の配列<br />並び順は、アプリIDの昇順です。<br />追加しているアプリが存在しない場合は、空配列が返ります。  |
| apps[].id | 文字列 | アプリID |
| apps[].name | 文字列 | アプリ名 |

### 必要なアクセス権 {#permissions}

- cybozu.com共通管理者

### サンプル {#sample}
```plaintext
https://sample.cybozu.com/k/v1/plugin/apps.json?id=djmhffjhfgmebgnmcggopedaofckljlj&offset=1&limit=1
```
```json
```

リクエストヘッダーの詳細は共通仕様を参照してください。  
[kintone REST APIの共通仕様](/id/d509b956c8f84c45e1e129ae/)
```json
  ]
}
```
`kintone.api()`の詳細は、次のページを参照してください。  
[kintone REST APIリクエストを送信する](/id/84b51223dd9e63a226e3e985/)

```js
const body = {
  id: 'djmhffjhfgmebgnmcggopedaofckljlj',
  limit: 1,
};

await kintone.api(kintone.api.url('/k/v1/plugin/apps.json', true), 'GET', body);
```
ご利用の環境によって、curlのフォーマットは異なる場合があります。  
詳細は、次のページを参照してください。  
[curlコマンドでkintone REST APIを実行してみよう/3.API実行](/id/49f27ea50d9f50901cdef93f/#api-execution-to-post)

```shell
curl -X GET 'https://sample.cybozu.com/k/v1/plugin/apps.json' \
  -H 'X-Cybozu-Authorization: QWRtaW5pc3RyYXRvcjpjeWJvenU=' \
  -H 'Content-Type: application/json' \
  -d '{
    "id": "djmhffjhfgmebgnmcggopedaofckljlj",
    "limit": 1
  }'
```
### 補足 {#notes}

- プラグインの追加を反映する前のアプリ情報も取得できます。
