---
title: "利用可能なAPIの種類を取得する"
description: '利用可能なAPIの種類を取得します。'
tocEndLevel: 4
weight: 600
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/c84294d596a06e40d449a3a5/"
---

### 利用可能なAPIの種類を取得する {#get-available-api-types}

利用可能なAPIの種類を取得します。

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数{#function}

##### PC／モバイル


kintone.getAvailableApiTypes()


#### 引数{#parameters}

なし

#### 戻り値{#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の値が取得できます。

| 型 | 説明  |
|:--|:--|
| 配列（文字列） | 利用可能なAPIの種類を表す文字列の配列<ul><li>`CORE`：一般に利用可能なAPI</li><li>`WIDE`：ワイドコース専用API</li></ul>配列に含まれる値の順序は保証されません。 |

#### 利用できる画面{#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](id/394dea74a167d5bca527ec3f/#available-pages)  
プラグイン設定画面でも利用できます。

ただし、次の画面では利用できません。  

- 検索画面
- アプリストア
