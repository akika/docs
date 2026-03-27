---
title: レコード一覧画面でレコードを削除する前のイベント
description: 'レコード一覧画面で【削除】をクリックしてポップアップの【削除する】をクリックした後、サーバーへ保存する前に発生するイベントです。'
tocEndLevel: 4
weight: 600
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/886240ad14145f8817ceb086/"
---

レコード一覧画面で【削除】をクリックしてポップアップの【削除する】をクリックした後、サーバーへ保存する前に発生するイベントです。

{{ toc }}

| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.record.index.delete.submit | レコード一覧画面で【削除】をクリックしてポップアップの【削除する】をクリックしたとき |
| モバイル | - | - |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br>`app.record.index.delete.submit`が返ります。 |
| appId | 数値 | アプリID |
| recordId | 数値 | レコードID |
| record | オブジェクト | 削除するレコードのデータ<br>詳細は次のページを参照してください。<br>[フィールド形式](/id/2736678ef8d2aad09a33e8bb/) |

### 削除処理をキャンセルする {#available-event-object-actions-cancel-delete}

イベントハンドラー内で次のどちらかを実行すると、削除処理をキャンセルできます。

- [画面上部にエラーを表示する](/id/073cb99467614b140b2a9c42/#record-list-show-record-errors)
- `false`をreturnする。

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [画面上部にエラーを表示する](/id/073cb99467614b140b2a9c42/#record-list-show-record-errors)
- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 制限事項 {#limitation}

- スペースやスレッドの本文に貼り付けたアプリでは、利用できません。  
  [スペースのお知らせやスレッドにアプリを貼り付ける](https://jp.cybozu.help/k/ja/id/040702.html)
