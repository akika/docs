---
title: "インストール済みのプラグインの一覧を取得する"
description: "kintoneに読み込んだプラグインの情報を取得します。"
tocEndLevel: 4
weight: 100
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/ace5777d9375efed42500278/"
---

kintoneに読み込んだプラグインの一覧を取得します。

{{ toc }}

<!-- eslint-disable sentence-length -->
<!-- textlint-disable -->
{{< vtable >}}
| HTTPメソッド | GET |
| URL | https\://sample.cybozu.com/k/v1/plugins.json |
| 認証 | [パスワード認証](/id/edae2a9d04c6e7d0afffda3a/#password), [セッション認証](/id/edae2a9d04c6e7d0afffda3a/#session) |
| Content-Type | 不要（リクエストボディにパラメーターを含める場合はapplication/json）|
{{< /vtable >}}
<!-- textlint-enable -->
<!-- eslint-enable sentence-length -->

### リクエストパラメーター {#request-parameters}

| パラメーター名 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| offset | 数値または文字列 | 省略可 | 取得する一覧の先頭からスキップする数。<br>省略すると、0が設定されます。 |
| limit | 数値または文字列 | 省略可 | 取得するプラグイン数の上限。<br>1から100までの数値を指定できます。<br>省略すると、100が設定されます。 |
| ids | 配列 | 省略可 | 取得対象のプラグインID。<br>最大100件指定できます。 |

### レスポンスプロパティ {#response-properties}

| プロパティ名 | 型 | 説明 |
|:--|:--|:--|
| plugins | 配列（オブジェクト） | 読み込んだプラグインの一覧<br>並び順は、インストールした日時の降順です。<br>プラグインが存在しない場合は、空配列が返ります。 |
| plugins[].id | 文字列 | プラグインID |
| plugins[].name | 文字列 | プラグインの名前 |
| plugins[].description | 文字列 | プラグインの説明 |
| plugins[].isMarketPlugin | 真偽値 | プラグインストアのプラグインかどうか<ul><li>`true`：プラグインストアのプラグインである</li><li>`false`：プラグインストアのプラグインではない</li></ul> |
| plugins[].version | 文字列 | プラグインのバージョン |

### 必要なアクセス権 {#permissions}

なし

### サンプル {#sample}

{{< accordion-frame title="サンプルリクエスト">}}

{{< sample-code title="リクエストURL（URLにパラメーターを含める場合）" >}}

```plaintext
https://sample.cybozu.com/k/v1/plugins.json?offset=1&limit=1
```

{{< /sample-code >}}

{{< sample-code title="リクエストヘッダー（URLにパラメーターを含める場合）" >}}

```json
{
  "X-Cybozu-Authorization": "QWRtaW5pc3RyYXRvcjpjeWJvenU="
}
```

リクエストヘッダーの詳細は共通仕様を参照してください。  
[kintone REST APIの共通仕様](/id/d509b956c8f84c45e1e129ae/)

{{< /sample-code >}}

{{< /accordion-frame >}}

{{< accordion-frame title="サンプルレスポンス">}}

```json
{
  "plugins": [
    {
      "id": "djmhffjhfgmebgnmcggopedaofckljlj",
      "name": "サンプルプラグイン",
      "description": "プラグインの説明",
      "isMarketPlugin": false,
      "version": "1.0.0"
    }
  ]
}
```

{{< /accordion-frame >}}

{{< accordion-frame title="サンプルコード">}}

{{< sample-code title="kintone.api()を使ったリクエスト">}}

`kintone.api()`の詳細は、次のページを参照してください。  
[kintone REST APIリクエストを送信する](/id/84b51223dd9e63a226e3e985/)

```js {iscopy="true"}
const body = {
  limit: 1,
};

await kintone.api(kintone.api.url('/k/v1/plugins.json', true), 'GET', body);
```

{{< /sample-code >}}

{{< sample-code title="curlを使ったリクエスト">}}

ご利用の環境によって、curlのフォーマットは異なる場合があります。  
詳細は、次のページを参照してください。  
[curlコマンドでkintone REST APIを実行してみよう/3.API実行](/id/49f27ea50d9f50901cdef93f/#api-execution-to-post)

```shell {iscopy="true"}
curl -X GET 'https://sample.cybozu.com/k/v1/plugins.json' \
  -H 'X-Cybozu-Authorization: QWRtaW5pc3RyYXRvcjpjeWJvenU=' \
  -H 'Content-Type: application/json' \
  -d '{
    "limit": 1
  }'
```

{{< /sample-code >}}

{{< /accordion-frame >}}
