---
title: ショートカットキーの有効／無効の状態を取得する
description: "ショートカットキーの有効／無効の状態を取得します。"
tocEndLevel: 4
weight: 1700
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/63da494f91aec0007a9df204/"
---

### ショートカットキーの有効／無効の状態を取得する {#specification}

ショートカットキーの有効／無効の状態を取得します。  

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数 {#function}

##### PC

<!-- textlint-disable prh -->
kintone.getKeyboardShortcuts()
<!-- textlint-enable prh -->

#### 引数 {#parameters}

なし

#### 戻り値 {#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の要素をもつオブジェクトが取得できます。

| プロパティ名 | 型 | 値と説明 |
| :-- | :-- | :-- |
| <ショートカット名> | 真偽値 | ショートカットキーが有効かどうか<br>現在開いている画面で使用可能なすべてのショートカットキーに対して、次の値が返ります。<ul><li>`true`：ショートカットキーが有効になっている</li><li>`false`：ショートカットキーが無効になっている</li></ul>ショートカット名は[ショートカットキーの有効／無効を切り替える](/id/8cb62c20ccce8501dd4e4499/)の`config.<ショートカット名>`と同じです。|

#### 利用できる画面 {#available-pages}

##### PC

- レコード一覧画面
- レコード詳細画面
- レコード編集画面
- レコード追加画面
