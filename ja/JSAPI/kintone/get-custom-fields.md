---
title: ユーザーのカスタマイズ項目を取得する
description: "ユーザーのカスタマイズ項目を取得します。"
tocEndLevel: 4
weight: 140
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/f8d0671d656d2c0ae4dd05d0/"
---

### ユーザーのカスタマイズ項目を取得する {#get-custom-fields}

ユーザーのカスタマイズ項目を取得します。  
ユーザーの情報を元にした分岐処理や、ユーザーの情報を表示するUIの作成などに利用できます。  
ログインユーザーのカスタマイズ項目を取得するときは、非公開のカスタマイズ項目も取得できます。

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数 {#function}

##### PC／モバイル

<!-- textlint-disable prh -->
kintone.user.getCustomFields(code)
<!-- textlint-enable prh -->

#### 引数 {#parameters}

| 引数名 | 型 | 必須 | 説明 |
|:--|:--|:--|:--|
| code | 文字列 | 省略可 | 情報を取得するユーザーのログイン名<br>省略した場合はログインユーザーの情報を取得します。 |

#### 戻り値 {#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の要素をもつオブジェクトの配列が取得できます。

| プロパティ名 | 型 | 値と説明 |
| :-- | :-- | :-- |
| code | 文字列 | 項目コード |
| name | 文字列 | 項目名 |
| type | 文字列 | タイプ<br><ul><li>`SINGLE_LINE_TEXT`：文字列1行</li><li>`USER_SELECT`：ユーザー選択</li></ul>  |
| value | 文字列／オブジェクト | 保存された値<br>`type`によってデータの型が変わります。<br><ul><li>`SINGLE_LINE_TEXT`の場合：文字列</li><li>`USER_SELECT`の場合：オブジェクト</li></ul> |
| value.code | 文字列 | 保存されたユーザーのコード<br>`type`が`USER_SELECT`の場合のみ存在します。 |
| value.name | 文字列 | 保存されたユーザーの名前<br>`type`が`USER_SELECT`の場合のみ存在します。  |
| visibility | 文字列 | 公開／非公開の設定<ul><li>`PUBLIC`：公開</li><li>`PRIVATE`：非公開</li></ul>  |

#### 利用できる画面 {#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](/id/394dea74a167d5bca527ec3f/#available-pages)  

ただし、次の画面では利用できません。  

- 検索画面
- アプリストア
- プラグイン設定画面

#### 注意事項 {#notes}

このAPIは実行時にサーバーからデータを取得します。取得したデータは画面遷移が発生するまでキャッシュされます。  
ユーザーごとに1分当たり50回を超えるサーバーからのデータの取得があった場合、戻り値のPromiseオブジェクトが拒否（rejected）されます。
