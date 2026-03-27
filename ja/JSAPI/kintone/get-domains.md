---
title: "ドメイン情報を取得する"
description: 'ドメイン情報を取得します。'
tocEndLevel: 4
weight: 500
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/eac269672d461b7707c1dec0/"
---

### ドメイン情報を取得する {#get-domain}

ドメイン情報を取得します。

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数{#function}

##### PC／モバイル


kintone.getDomain()


#### 引数{#parameters}

なし

#### 戻り値{#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の値が取得できます。

| プロパティ名 | 型 | 値と説明 |
|:--|:--|:--|
| subdomain  | 文字列 | サブドメイン名 |
| baseDomain | 文字列 | ドメイン名<br />ご利用の環境に応じて以下のいずれかの値が返ります。<ul><li>`cybozu.com`</li><li>`cybozu.cn`</li><li>`kintone.com`</li></ul> |

#### 利用できる画面{#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](id/394dea74a167d5bca527ec3f/#available-pages)  
プラグイン設定画面でも利用できます。

ただし、次の画面では利用できません。  

- 検索画面
- アプリストア
