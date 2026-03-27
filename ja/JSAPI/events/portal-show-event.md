---
title: "ポータル画面を表示した後のイベント"
description: 'ポータル画面を表示したときに発生するイベントです。'
tocEndLevel: 4
weight: 900
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/8dac51519b826f2b22c709af/"
---

ポータル画面を表示したときに発生するイベントです。

{{ toc }}

| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | portal.show | ポータル画面を表示したとき |
| モバイル | mobile.portal.show | ポータル画面を表示したとき |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| type | 文字列 | イベントタイプ<br>次の値が返ります。<ul><li>PC：`portal.show`</li><li>モバイル：`mobile.portal.show`</li></ul> |

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 補足 {#note}

- 表示対象に設定されているウィジェットがすべて描画されたあとに、イベントが発生します。
- ゲストユーザーのポータル画面では発生しません。
- 2枚目以降のポータル画面では発生しません。
