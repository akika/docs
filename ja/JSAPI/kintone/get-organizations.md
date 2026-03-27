---
title: ユーザーが所属する組織を取得する
description: "ユーザーが所属する組織を取得します。"
tocEndLevel: 4
weight: 120
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/353c88fc9220005bb0ac6925/"
---

### ユーザーが所属する組織を取得する {#get-organizations}

ユーザーが所属する組織を取得します。  
ユーザーの情報を元にした分岐処理や、ユーザーの情報を表示するUIの作成などに利用できます。  
「別言語での表示名」を設定できる項目の値は、このAPIを実行するユーザーが設定した言語で返ります。  

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数 {#function}

##### PC／モバイル


kintone.user.getOrganizations(code)


#### 引数 {#parameters}

| 引数名 | 型 | 必須 | 説明 |
|:--|:--|:--|:--|
| code | 文字列 | 省略可 | 情報を取得するユーザーのログイン名<br />省略した場合はログインユーザーの情報を取得します。 |

#### 戻り値 {#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の要素をもつオブジェクトの配列が取得できます。

| プロパティ名 | 型 | 値と説明 |
| :-- | :-- | :-- |
| organization | オブジェクト | 組織情報 |
| organization.id | 文字列 | 組織ID |
| organization.code | 文字列 | 組織コード |
| organization.name | 文字列 | 組織名 |
| organization.primary | 真偽値 | 優先する組織かどうか<ul><li>`true`：優先する組織である</li><li>`false`：優先する組織ではない</li></ul> |
| title | オブジェクト | 役職情報<br /> 未設定の場合にはnullが返ります。 |
| title.id | 文字列 | 役職ID |
| title.code | 文字列 | 役職コード |
| title.name | 文字列 | 役職名 |

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

- ユーザーが所属する組織の他の情報を取得したい場合には、次のAPIを利用してください。  
[組織を取得する](/id/2db19fac4d889216ebe8c2d7/)
