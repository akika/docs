---
title: "プラグインを更新する"
description: "kintoneに読み込んだプラグインを更新します。"
tocEndLevel: 4
weight: 500
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/4c0e93986f6a7c08033d874f/"
---

kintoneに読み込んだプラグインを更新します。

{{ toc }}

<!-- eslint-disable sentence-length -->
<!-- textlint-disable -->
{{< vtable >}}
| HTTPメソッド | PUT |
| URL | https\://sample.cybozu.com/k/v1/plugin.json |
| 認証 | [パスワード認証](/id/edae2a9d04c6e7d0afffda3a/#password), [セッション認証](/id/edae2a9d04c6e7d0afffda3a/#session) |
| Content-Type | application/json |
{{< /vtable >}}
<!-- textlint-enable -->
<!-- eslint-enable sentence-length -->

### リクエストパラメーター {#request-parameters}

| パラメーター名 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| id | 文字列 | 必須 | 更新するプラグインのプラグインID |
| fileKey | 文字列 | 必須 | ファイルをアップロードするAPIでアップロードしたプラグインファイルのファイルキー<br>[ファイルをアップロードする](/id/bb1225dd8d192245c3645a95/) |

### レスポンスプロパティ {#response-properties}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| id | 文字列 | 更新されたプラグインのプラグインID |
| version | 文字列 | プラグインのバージョン |

### 必要なアクセス権 {#permissions}

- kintoneシステム管理者権限

### サンプル {#sample}

{{< accordion-frame title="サンプルリクエスト">}}

{{< sample-code title="リクエストヘッダー" >}}

```json
{
  "X-Cybozu-Authorization": "QWRtaW5pc3RyYXRvcjpjeWJvenU=",
  "Content-Type": "application/json"
}
```

リクエストヘッダーの詳細は共通仕様を参照してください。  
[kintone REST APIの共通仕様](/id/d509b956c8f84c45e1e129ae/)

{{< /sample-code >}}

{{< sample-code title="リクエストボディ" >}}

```json
{
  "id": "djmhffjhfgmebgnmcggopedaofckljlj",
  "fileKey": "c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6"
}
```

{{< /sample-code >}}

{{< /accordion-frame >}}

{{< accordion-frame title="サンプルレスポンス">}}

```json
{
  "id": "djmhffjhfgmebgnmcggopedaofckljlj",
  "version": "1"
}
```

{{< /accordion-frame >}}

{{< accordion-frame title="サンプルコード">}}

{{< sample-code title="kintone.api()を使ったリクエスト">}}

`kintone.api()`の詳細は、次のページを参照してください。  
[kintone REST APIリクエストを送信する](/id/84b51223dd9e63a226e3e985/)

```js {iscopy="true"}
const body = {
  id: 'djmhffjhfgmebgnmcggopedaofckljlj',
  fileKey: 'c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6'
};

await kintone.api(kintone.api.url('/k/v1/plugin.json'), 'PUT', body);
```

{{< /sample-code >}}

{{< sample-code title="curlを使ったリクエスト">}}

ご利用の環境によって、curlのフォーマットは異なる場合があります。  
詳細は、次のページを参照してください。  
[curlコマンドでkintone REST APIを実行してみよう/3.API実行](/id/49f27ea50d9f50901cdef93f/#api-execution-to-post)

```shell {iscopy="true"}
curl -X PUT 'https://sample.cybozu.com/k/v1/plugin.json' \
  -H 'X-Cybozu-Authorization: QWRtaW5pc3RyYXRvcjpjeWJvenU=' \
  -H 'Content-Type: application/json' \
  -d '{
      "id": "djmhffjhfgmebgnmcggopedaofckljlj",
      "fileKey": "c15b3870-7505-4ab6-9d8d-b9bdbc74f5d6"
  }'
```

{{< /sample-code >}}

{{< /accordion-frame >}}
