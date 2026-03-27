---
title: "kintone内の画面のURLを組み立てる"
description: 'kintone内の画面のURLを組み立てます。'
tocEndLevel: 4
weight: 1600
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/9f2164aa03296c1ad3e42408/"
---

### kintone内の画面のURLを組み立てる {#specification}

kintone内の画面のURLを組み立て取得します。
ゲストスペース内アプリを指定した場合は、ゲストスペース用のURLが組み立てられます。

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数{#function}

##### PC／モバイル

<!-- textlint-disable prh -->
kintone.buildPageUrl(page, params)
<!-- textlint-enable prh -->

#### 引数{#parameters}

| 引数名 | 型 | 必須 | 説明 |
|:--|:--|:--|:--|
| page | 文字列 | 必須 | 画面を表す文字列<br>次のいずれかの値を指定します。<ul><li>アプリの画面<ul><li>`APP_INDEX`：一覧（PC）<br>`params.appId`の指定が必須です。`params.viewId`を指定できます。</li><li>`APP_CREATE`：作成（PC）<br>`params.appId`の指定が必須です。</li><li>`APP_DETAIL`：詳細（PC）<br>`params.appId`と`params.recordId`の指定が必須です。</li><li>`APP_EDIT`：編集（PC）<br>`params.appId`と`params.recordId`の指定が必須です。</li><li>`APP_PRINT`：印刷（PC）<br>`params.appId`と`params.recordId`の指定が必須です。</li><li>`APP_REPORT`：グラフ（PC）<br>`params.appId`と`params.reportId`の指定が必須です。</li><li>`APP_INDEX_MOBILE`：一覧（モバイル）<br>`params.appId`の指定が必須です。`params.viewId`を指定できます。</li><li>`APP_CREATE_MOBILE`：作成（モバイル）<br>`params.appId`の指定が必須です。</li><li>`APP_DETAIL_MOBILE`：詳細（モバイル）<br>`params.appId`と`params.recordId`の指定が必須です。</li><li>`APP_EDIT_MOBILE`：編集（モバイル）<br>`params.appId`と`params.recordId`の指定が必須です。</li><li>`APP_REPORT_MOBILE`：グラフ（モバイル）<br>`params.appId`と`params.reportId`の指定が必須です。</li></ul></li><li>ポータルの画面<ul><li>`PORTAL_TOP`：トップ（PC）</li><li>`PORTAL_TOP_MOBILE`：トップ（モバイル）</li></ul></li><li>スペースの画面<ul><li>`SPACE_PORTAL`：スペースポータル（PC）<br>`params.spaceId`の指定が必須です。</li><li>`SPACE_THREAD`：スレッド（PC）<br>`params.spaceId`と`params.threadId`の指定が必須です。</li><li>`SPACE_PORTAL_MOBILE`：スペースポータル（モバイル）<br>`params.spaceId`の指定が必須です。</li><li>`SPACE_THREAD_MOBILE`：スレッド（モバイル）<br>`params.spaceId`と`params.threadId`の指定が必須です。</li></ul></li><li>ピープルの画面<ul><li>`PEOPLE_TOP`：トップ（PC）<br>`params.userCode`の指定が必須です。</li><li>`PEOPLE_TOP_MOBILE`：トップ（モバイル）<br>`params.userCode`の指定が必須です。</li></ul></li><li>メッセージの画面<ul><li>`MESSAGE_TOP`：トップ（PC）<br>`params.userCode`の指定が必須です。</li><li>`MESSAGE_TOP_MOBILE`：トップ（モバイル）<br>`params.userCode`の指定が必須です。</li></ul></li><li>検索の画面<ul><li>`SEARCH_TOP`：トップ（PC）</li><li>`SEARCH_TOP_MOBILE`：トップ（モバイル）</li></ul></li><li>通知の画面<ul><li>`NOTIFICATION_TOP`：トップ（PC）</li></ul></li><li>アプリストアの画面<ul><li>`APP_MARKETPLACE_TOP`：トップ（PC）</li></ul></li></ul> |
| params | オブジェクト | 必須 | URLの組み立てに使用する引数 |
| params.appId | 文字列 | 条件必須 | アプリID<br>アプリの各画面で必須です。 |
| params.recordId | 文字列 | 条件必須 | レコードID<br>レコード詳細、レコード編集、レコード印刷の各画面で必須です。 |
| params.viewId | 文字列| 省略可 | 一覧のID |
| params.reportId | 文字列 | 条件必須 | グラフのID<br>グラフ画面で必須です。 |
| params.spaceId | 文字列 | 条件必須 | スペースID<br>スペースの各画面で必須です。 |
| params.threadId | 文字列 | 条件必須 | スレッドID<br>スレッド画面で必須です。 |
| params.userCode | 文字列 | 条件必須 | ユーザーコード<br>ピープルおよびメッセージの各画面で必須です。 |

#### 戻り値{#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の値が取得できます。

| 型 | 説明     |
|:--|:-------|
| 文字列 | 画面のURL |

#### 利用できる画面{#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](id/394dea74a167d5bca527ec3f/#available-pages)  

ただし、次の画面では利用できません。  

- 検索画面
- アプリストア
- プラグイン設定画面

#### 注意事項 {#notes}

このAPIは実行時にサーバーからデータを取得します。取得したデータは画面遷移が発生するまでキャッシュされます。  
ユーザーごとに1分当たり50回を超えるサーバーからのデータの取得があった場合、戻り値のPromiseオブジェクトが拒否（rejected）されます。
