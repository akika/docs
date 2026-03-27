---
title: "プラグインをアンインストールする"
description: "kintoneからプラグインをアンインストールします。"
tocEndLevel: 4
weight: 600
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/8c2031cc1081afd160007699/"
---

kintoneからプラグインをアンインストールします。




| HTTPメソッド | DELETE |
| URL | https\://sample.cybozu.com/k/v1/plugin.json |
| 認証 | [パスワード認証](/id/edae2a9d04c6e7d0afffda3a/#password), [セッション認証](/id/edae2a9d04c6e7d0afffda3a/#session) |
| Content-Type | 不要（リクエストボディにパラメーターを含める場合はapplication/json） |



### リクエストパラメーター {#request-parameters}

| パラメーター名 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| id | 文字列 | 必須 | アンインストールするプラグインのプラグインID |

### レスポンスプロパティ {#response-properties}

なし

### 必要なアクセス権 {#permissions}

- kintoneシステム管理者権限

### サンプル {#sample}
```plaintext
https://sample.cybozu.com/k/v1/plugin.json?id=djmhffjhfgmebgnmcggopedaofckljlj
```
```json
```

リクエストヘッダーの詳細は共通仕様を参照してください。  
[kintone REST APIの共通仕様](/id/d509b956c8f84c45e1e129ae/)
```json
{}
```
`kintone.api()`の詳細は、次のページを参照してください。  
[kintone REST APIリクエストを送信する](/id/84b51223dd9e63a226e3e985/)

```js
const body = {
  id: 'djmhffjhfgmebgnmcggopedaofckljlj'
};

await kintone.api(kintone.api.url('/k/v1/plugin.json'), 'DELETE', body);
```
ご利用の環境によって、curlのフォーマットは異なる場合があります。  
詳細は、次のページを参照してください。  
[curlコマンドでkintone REST APIを実行してみよう/3.API実行](/id/49f27ea50d9f50901cdef93f/#api-execution-to-post)

```shell
curl -X DELETE 'https://sample.cybozu.com/k/v1/plugin.json' \
  -H 'X-Cybozu-Authorization: QWRtaW5pc3RyYXRvcjpjeWJvenU=' \
  -H 'Content-Type: application/json' \
  -d '{
      "id": "djmhffjhfgmebgnmcggopedaofckljlj"
  }'
```
