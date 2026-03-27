---
title: レコード印刷画面を表示した後のイベント
description: 'レコード印刷画面を表示したときに発生するイベントです。'
tocEndLevel: 4
weight: 800
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/3bc9fd50e0df52db2617ae3c/"
---

レコード印刷画面を表示したときに発生するイベントです。


| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.record.print.show | レコード印刷画面を表示したとき |
| モバイル | - | - |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br />`app.record.print.show`が返ります。 |
| appId | 数値 | アプリID |
| record | オブジェクト | レコード印刷画面を表示したときのレコードのデータ<br />詳細は次のページを参照してください。<br />[フィールド形式](/id/2736678ef8d2aad09a33e8bb/) |
| recordId | 数値 | レコードID |

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)
