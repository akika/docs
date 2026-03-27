---
title: ログインユーザーの情報を取得する
description: "ページを表示しているユーザーのユーザー情報を取得します。"
tocEndLevel: 4
weight: 100
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/77c07915d060850bf7497995/"
---

### ログインユーザーの情報を取得する {#get-login-user}

ログインしているユーザーの情報を取得します。  
ゲストユーザーの情報も取得できます。

#### 関数 {#function}

##### PC／モバイル

<!-- textlint-disable prh -->
kintone.getLoginUser()
<!-- textlint-enable prh -->

#### 引数 {#parameters}

なし

#### 戻り値 {#response}

| プロパティ名 | 型 | 値と説明 |
| :-- | :-- | :-- |
| id | 文字列 | システムが自動採番したユーザーID |
| code | 文字列 | ログイン名<br>ゲストユーザーの場合は「Email」です。 |
| name | 文字列 | 表示名<br>ゲストユーザーの場合は「名前」です。 |
| email | 文字列 | メールアドレス |
| url | 文字列 | URL<br>ゲストユーザーの場合は空文字列です。 |
| employeeNumber | 文字列 | 従業員ID<br> ゲストユーザーの場合は空文字列です。 |
| phone | 文字列 | 電話番号 |
| mobilePhone | 文字列 | 携帯番号<br>ゲストユーザーの場合は空文字列です。 |
| extensionNumber | 文字列 | 内線番号<br>ゲストユーザーの場合は空文字列です。 |
| timezone | 文字列 | タイムゾーン |
| isGuest | 真偽値 | ゲストユーザーかどうか<ul><li>`true`：ゲストユーザー</li><li>`false`：ゲストユーザーでない</li></ul> |
| language | 文字列 | 言語とタイムゾーンで設定されたユーザーの言語<ul><li>`ja`：日本語</li><li>`en`：英語</li><li>`zh`：中国語（簡体字）</li><li> `zh-TW`：中国語（繁体字）</li><li>`es`：スペイン語</li><li>`pt-BR`：ポルトガル語（ブラジル）</li><li>`th`：タイ語</li></ul>その他の対応していないロケールは`en`が返ります。|

#### 利用できる画面 {#available-pages}

##### PC／モバイル

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](/id/394dea74a167d5bca527ec3f/#available-pages)  
ただし、プラグイン設定画面でも利用できます。

#### 注意事項 {#notes}

- ユーザー情報の詳細を取得したい場合には、次のAPIを利用してください。  
[ユーザーを取得する](/id/f31ce2157b6070e0173ec477/)
