---
title: スペースのポータル画面を表示した後のイベント
description: 'スペースのポータル画面を表示したときに発生するイベントです。'
tocEndLevel: 4
weight: 1000
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/98715f80d1158b8e45fb717a/"
---

スペースのトップ画面を表示したときに発生するイベントです。


| | イベントタイプ | イベントが発生するタイミング |
| :-- | :-- | :-- |
| PC | space.portal.show | スペースのポータル画面を表示したとき |
| モバイル | mobile.space.portal.show | スペースのポータル画面を表示したとき |

### イベントオブジェクトのプロパティ {#properties-of-the-event-object}

| プロパティ名 | 型 | 説明 |
| :-- | :-- | :-- |
| spaceId | 文字列 | スペースID |
| type | 文字列 | イベントタイプ<br />次の値が返ります。<ul><li>PC：`space.portal.show`</li><li>モバイル：`mobile.space.portal.show`</li></ul> |

### イベントオブジェクトで実行できる操作 {#available-event-object-actions}

- [Promise対応](/id/073cb99467614b140b2a9c42/#support-promise)

### 補足 {#note}

- 表示対象に設定されているウィジェットがすべて描画されたあとに、イベントが発生します。
- 「スペースのポータルと複数にスレッドを使用する」が有効のスペースのみで発生します。
- ゲストスペースのポータル画面では発生しません。
