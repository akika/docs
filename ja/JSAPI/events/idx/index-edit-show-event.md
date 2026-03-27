---
title: "レコード一覧画面のインライン編集を開始したときのイベント"
description: 'レコード一覧画面のインライン編集で、任意のレコードのインライン編集が開始された時に発生するイベントです。'
tocEndLevel: 4
weight: 200
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/8d1bc2d35a1aaa39cf7d2d85/"
---

レコード一覧画面のインライン編集で、任意のレコードのインライン編集を開始したときに発生するイベントです。

{{ toc }}

| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.record.index.edit.show | レコード一覧画面で、レコードのインライン編集を開始したとき |
| モバイル | なし | なし |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br>`app.record.index.edit.show`が返ります。 |
| appId | 数値 | アプリID |
| recordId | 文字列 | レコードID |
| record | オブジェクト | インライン編集開始時のレコードのデータ<br>詳細は次のページを参照してください。<br>[フィールド形式](/id/2736678ef8d2aad09a33e8bb/) |

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [フィールドの編集可／不可を設定する](/id/073cb99467614b140b2a9c42/#record-list-enable-disable-field-edits)
- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 制限事項 {#limitation}

- スペースやスレッドの本文に貼り付けたアプリでは、利用できません。  
  [スペースのお知らせやスレッドにアプリを貼り付ける](https://jp.cybozu.help/k/ja/id/040702.html)
