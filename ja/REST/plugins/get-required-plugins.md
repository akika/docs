---
title: "インストールが必要なプラグインの一覧を取得する"
description: "kintoneにインストールが必要なプラグインの情報を取得します。"
tocEndLevel: 4
weight: 200
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/56524ae67a377d756e329bd2/"
---

kintoneにインストールが必要なプラグインの一覧を取得します。




| HTTPメソッド | GET |
| URL | https\://sample.cybozu.com/k/v1/plugins/required.json |
| 認証 | [パスワード認証](/id/edae2a9d04c6e7d0afffda3a/#password), [セッション認証](/id/edae2a9d04c6e7d0afffda3a/#session) |
| Content-Type | 不要（リクエストボディにパラメーターを含める場合はapplication/json）|



### リクエストパラメーター {#request-parameters}

| パラメーター名 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| offset | 数値または文字列 | 省略可 | 取得する一覧からスキップする数。<br />省略すると、0が設定されます。 |
| limit | 数値または文字列 | 省略可 | 取得するプラグイン数の上限。<br />1から100までの数値を指定できます。<br />省略すると、100が設定されます。 |

### レスポンスプロパティ {#response-properties}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| plugins | 配列（オブジェクト） | インストールが必要なプラグインの一覧<br /><br />並び順は、プラグインIDの昇順です。<br />プラグインが存在しない場合は、空配列が返ります。 |
| plugins[].id | 文字列 | プラグインID |
| plugins[].name | 文字列 | プラグインの名前<br />取得できない場合は`null`が返ります。 |
| plugins[].isMarketPlugin | 真偽値 | プラグインストアのプラグインかどうか<ul><li>`true`：プラグインストアのプラグインである</li><li>`false`：プラグインストアのプラグインではない</li></ul> |

### 必要なアクセス権 {#permissions}

なし

### サンプル {#sample}
```plaintext
https://sample.cybozu.com/k/v1/plugins/required.json?offset=1&limit=1
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
  limit: 1,
};

await kintone.api(kintone.api.url('/k/v1/plugins/required.json', true), 'GET', body);
```
ご利用の環境によって、curlのフォーマットは異なる場合があります。  
詳細は、次のページを参照してください。  
[curlコマンドでkintone REST APIを実行してみよう/3.API実行](/id/49f27ea50d9f50901cdef93f/#api-execution-to-post)

```shell
curl -X GET 'https://sample.cybozu.com/k/v1/plugins/required.json' \
  -H 'X-Cybozu-Authorization: QWRtaW5pc3RyYXRvcjpjeWJvenU=' \
  -H 'Content-Type: application/json' \
  -d '{
    "limit": 1
  }'
```
