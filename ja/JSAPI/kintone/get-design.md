---
title: "デザインのバージョンを取得する"
description: "現在開いている画面のデザインのバージョンを取得します。"
tocEndLevel: 4
weight: 300
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/bb6785bc5550b8adea13db9c/"
---

### デザインのバージョンを取得する {#get-design}

現在開いている画面のデザインのバージョンを取得します。

#### 関数 {#function}

##### PC／モバイル

<!-- textlint-disable prh -->
kintone.getUiVersion()
<!-- textlint-enable prh -->

#### 引数 {#parameters}

なし

#### 戻り値 {#response}

|型|説明|
|:---|:---|
|数値|デザインのバージョン<ul><li>`1`：PCの旧デザインおよびモバイル</li><li>`2`：PCの新デザイン</li></ul>|

#### 利用できる画面 {#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](/id/394dea74a167d5bca527ec3f/#available-pages)  
ただし、プラグイン設定画面でも利用できます。
