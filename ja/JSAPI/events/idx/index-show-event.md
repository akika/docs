---
title: レコード一覧画面を表示した後のイベント
description: 'レコード一覧画面を表示したときに発生するイベントです。'
tocEndLevel: 4
weight: 100
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/a7cfce771ab828cfb4d654cf/"
---

レコード一覧画面を表示したときに発生するイベントです。


| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.record.index.show | 共通<ul><li>レコード一覧画面を表示したとき</li><li>レコード一覧画面でページ送りしたとき</li><li>レコード一覧画面の絞り込み条件を適用したとき</li><li>レコード一覧画面でカテゴリーを変更したとき</li></ul>表形式のとき<ul><li>レコード一覧画面でフィールド名をクリックし、ソートしたとき</li></ul>カレンダー形式のとき<ul><li>レコード一覧画面で年または月を変更したとき</li></ul> |
| モバイル | mobile.app.record.index.show | 共通<ul><li>レコード一覧画面の表示したとき</li><li>レコード一覧画面でページ送りしたとき</li><li>レコード一覧画面の絞り込み条件を適用したとき</li><li>レコード一覧画面でカテゴリーを変更したとき</li></ul>表形式のとき<ul><li>レコード一覧画面でフィールド名をクリックし、ソートしたとき</li></ul>カレンダー形式のとき<ul><li>レコード一覧画面で年または月を変更したとき</li></ul> |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列  | イベントタイプ<br />次の値が返ります。<ul><li>PC：`app.record.index.show`</li><li>モバイル：`mobile.app.record.index.show`</li></ul> |
| appId | 数値 | アプリID |
| viewId | 数値 | 一覧ID |
| viewName | 文字列 | 一覧名 |
| viewType | 文字列 | レコード一覧の表示形式<ul><li>`list`：表形式</li><li>`calendar`：カレンダー形式</li><li>`custom`：カスタマイズ</li></ul> |
| records | 配列またはオブジェクト | レコード情報<br />`viewType`の値によって異なります。<ul><li>「list」のとき：レコードのデータの配列</li><li>「calendar」のとき：キーを日付文字列にもつレコードのデータの配列のオブジェクト</li><li>「custom」で、ページネーションがtrueのとき：レコードのデータの配列</li><li>「custom」で、ページネーションがfalseのとき：空配列</li></ul>レコードのデータの詳細は、次のページを参照してください。<br />[フィールド形式](/id/2736678ef8d2aad09a33e8bb/) |
| date | 文字列  | 日付<br />`viewType`の値によって異なります。<ul><li>「calendar」のとき：カレンダー形式の表示月<br />例：`2013-06`</li><li>「calendar」以外のとき：「null」</li></ul> |
| offset | 数値  | オフセット<br />`viewType`の値によって異なります。<ul><li>「list」のとき：一覧のオフセット数</li><li>「calendar」のとき：「null」</li><li>「custom」で、ページネーションがtrueのとき：一覧のオフセット数</li><li>「custom」で、ページネーションがfalseのとき：`0`</li></ul>|
| size | 数値  | レコード数<br />`viewType`の値によって異なります。<ul><li>「list」のとき：一覧のレコード数</li><li>「calendar」のとき：「null」</li><li>「custom」で、ページネーションがtrueのとき：一覧のレコード数</li><li>「custom」で、ページネーションがfalseのとき：`0`</li></ul>|

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 制限事項 {#limitation}

- スペースやスレッドの本文に貼り付けたアプリでは、利用できません。  
  [スペースのお知らせやスレッドにアプリを貼り付ける](https://jp.cybozu.help/k/ja/id/040702.html)
