---
title: レコード一覧画面のインライン編集で保存するときのイベント
description: 'レコード一覧画面でインライン編集の【保存】をクリックした後、サーバーへ保存する前に発生するイベントです。'
tocEndLevel: 4
weight: 400
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/bab2a87016ccaa3c4cc99c88/"
---

レコード一覧画面でインライン編集の【保存】をクリックした後、サーバーへ保存する前に発生するイベントです。

{{ toc }}

| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.record.index.edit.submit | レコード一覧画面でインライン編集の【保存】をクリックしたとき |
| モバイル | - | - |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br>`app.record.index.edit.submit`が返ります。 |
| appId | 文字列 | アプリID |
| recordId | 文字列 | レコードID |
| record | オブジェクト | 保存するレコードのデータ<br>詳細は次のページを参照してください。<br>[フィールド形式](/id/2736678ef8d2aad09a33e8bb/) |

### 保存処理をキャンセルする {#available-event-object-actions-cancel-save}

イベントハンドラー内で次のいずれかを実行すると、保存処理をキャンセルできます。

- [フィールドにエラーを表示する](/id/073cb99467614b140b2a9c42/#record-list-show-field-errors)
- [画面上部にエラーを表示する](/id/073cb99467614b140b2a9c42/#record-list-show-record-errors)
- `false`をreturnする。

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [フィールドの値を書き換える](/id/073cb99467614b140b2a9c42/#record-list-overwrite-field-values)
- [フィールドにエラーを表示する](/id/073cb99467614b140b2a9c42/#record-list-show-field-errors)
- [画面上部にエラーを表示する](/id/073cb99467614b140b2a9c42/#record-list-show-record-errors)
- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 制限事項 {#limitation}

- イベントオブジェクトで取得できる計算フィールドの値は、操作するレコード一覧画面にフィールドを配置しているかどうかで変わります。
  - 一覧に配置している場合：空文字列
  - 一覧に配置していない場合：再計算前の値
- スペースやスレッドの本文に貼り付けたアプリでは、利用できません。  
  [スペースのお知らせやスレッドにアプリを貼り付ける](https://jp.cybozu.help/k/ja/id/040702.html)
