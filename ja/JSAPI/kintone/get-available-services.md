---
title: "cybozu.comの他のサービスを利用可能かどうかを取得する"
description: 'cybozu.comの他のサービスを利用可能かどうかを取得します。'
tocEndLevel: 4
weight: 400
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/1f712ed39f52b4d9faacf7c6/"
---

### cybozu.comの他のサービスを利用可能かどうかを取得する {#get-available-services}

cybozu.comの他のサービスを利用可能かどうかを取得します。

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数{#function}

##### PC／モバイル

<!-- textlint-disable prh -->
kintone.getAvailableServices()
<!-- textlint-enable prh -->

#### 引数{#parameters}

なし

#### 戻り値{#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の値が取得できます。

| プロパティ名 | 型 | 値と説明 |
|:--|:--|:--|
| garoon | 真偽値 | Garoonが利用可能かどうか<ul><li>`true`：利用できる</li><li>`false`：利用できない</li></ul> |
| office | 真偽値 | サイボウズ Officeが利用可能かどうか<ul><li>`true`：利用できる</li><li>`false`：利用できない</li></ul> |
| <!--textlint-disable prh -->mailwise<!--textlint-enable prh --> | 真偽値 | メールワイズが利用可能かどうか<ul><li>`true`：利用できる</li><li>`false`：利用できない</li></ul> |

#### 利用できる画面{#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](id/394dea74a167d5bca527ec3f/#available-pages)  

ただし、次の画面では利用できません。  

- 検索画面
- アプリストア
- プラグイン設定画面
