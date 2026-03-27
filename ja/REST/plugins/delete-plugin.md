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

{{ toc }}

<!-- eslint-disable sentence-length -->
<!-- textlint-disable -->
{{< vtable >}}
| HTTPメソッド | DELETE |
| URL | https\://sample.cybozu.com/k/v1/plugin.json |
| 認証 | [パスワード認証](/id/edae2a9d04c6e7d0afffda3a/#password), [セッション認証](/id/edae2a9d04c6e7d0afffda3a/#session) |
| Content-Type | 不要（リクエストボディにパラメーターを含める場合はapplication/json） |
{{< /vtable >}}
<!-- textlint-enable -->
<!-- eslint-enable sentence-length -->

### リクエストパラメーター {#request-parameters}

| パラメーター名 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| id | 文字列 | 必須 | アンインストールするプラグインのプラグインID |

### レスポンスプロパティ {#response-properties}

なし

### 必要なアクセス権 {#permissions}

- kintoneシステム管理者権限

### サンプル {#sample}

{{< accordion-frame title="サンプルリクエスト">}}

{{< sample-code title="リクエストURL（URLにパラメーターを含める場合）" >}}

```plaintext
https://sample.cybozu.com/k/v1/plugin.json?id=djmhffjhfgmebgnmcggopedaofckljlj
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
{}
```

{{< /accordion-frame >}}

{{< accordion-frame title="サンプルコード">}}

{{< sample-code title="kintone.api()を使ったリクエスト">}}

`kintone.api()`の詳細は、次のページを参照してください。  
[kintone REST APIリクエストを送信する](/id/84b51223dd9e63a226e3e985/)

```js {iscopy="true"}
const body = {
  id: 'djmhffjhfgmebgnmcggopedaofckljlj'
};

await kintone.api(kintone.api.url('/k/v1/plugin.json'), 'DELETE', body);
```

{{< /sample-code >}}

{{< sample-code title="curlを使ったリクエスト">}}

ご利用の環境によって、curlのフォーマットは異なる場合があります。  
詳細は、次のページを参照してください。  
[curlコマンドでkintone REST APIを実行してみよう/3.API実行](/id/49f27ea50d9f50901cdef93f/#api-execution-to-post)

```shell {iscopy="true"}
curl -X DELETE 'https://sample.cybozu.com/k/v1/plugin.json' \
  -H 'X-Cybozu-Authorization: QWRtaW5pc3RyYXRvcjpjeWJvenU=' \
  -H 'Content-Type: application/json' \
  -d '{
      "id": "djmhffjhfgmebgnmcggopedaofckljlj"
  }'
```

{{< /sample-code >}}

{{< /accordion-frame >}}
