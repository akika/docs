---
title: "グラフ画面を表示した後のイベント"
description: 'グラフ画面を表示したときに発生するイベントです。'
tocEndLevel: 4
weight: 700
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/e5329a3897c9395484e66d97/"
---

グラフ画面を表示したときに発生するイベントです。


| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | app.report.show | グラフ画面を表示したとき |
| モバイル | mobile.app.report.show | グラフ画面を表示したとき |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br />次の値が返ります。<ul><li>PC：`app.report.show`</li><li>モバイル：`mobile.app.report.show`</li></ul> |
| appId | 数値 | アプリID |

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 補足 {#note}

- モバイルに対応していない、次のグラフを表示するときもイベントが発生します。
  - クロス集計
  - 表
  - 定期レポート

- スペースに貼り付けたアプリでは利用できません。
