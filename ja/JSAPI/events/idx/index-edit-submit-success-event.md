---
title: レコード一覧画面のインライン編集に成功したときのイベント
description: 'レコード一覧画面でインライン編集の【保存】をクリックした後、サーバーへの保存が成功したときに発生するイベントです。'
tocEndLevel: 4
weight: 500
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/043bc028a700e0c7e78cae46/"
---

レコード一覧画面でインライン編集の【保存】をクリックした後、サーバーへの保存が成功したときに発生するイベントです。


| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.record.index.edit.submit.success | レコード一覧画面でインライン編集の【保存】をクリックした後、サーバーへの保存が成功したとき |
| モバイル | - | - |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br />`app.record.index.edit.submit.success`が返ります。 |
| appId | 数値 | アプリID |
| recordId | 文字列 | レコードID |
| record | オブジェクト | 保存したレコードのデータ<br />詳細は次のページを参照してください。<br />[フィールド形式](/id/2736678ef8d2aad09a33e8bb/) |

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [指定したURLに遷移する](/id/073cb99467614b140b2a9c42/#record-list-specify-the-url-property)
- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 制限事項 {#limitation}

- スペースやスレッドの本文に貼り付けたアプリでは、利用できません。  
  [スペースのお知らせやスレッドにアプリを貼り付ける](https://jp.cybozu.help/k/ja/id/040702.html)
