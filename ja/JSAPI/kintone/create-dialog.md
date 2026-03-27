---
title: 'ダイアログを作成する'
description: 'ダイアログを作成します。'
tocEndLevel: 4
weight: 1310
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/6ace24e2779da218b2193bc3/"
---

### ダイアログを作成する {#create-dialog}

ダイアログを作成します。  
ダイアログ内に表示する内容は独自のカスタマイズが可能です。  

このAPIは非同期なAPIです。  
同期的に処理したい場合は、次のページを参照してください。

- [はじめようJavaScript：Promiseとasync/await](/id/dc34904c60bf584f04878073/)
- [はじめようkintone API：kintoneカスタマイズで非同期処理をする](/id/7f283857d43e6acca99eb5cb/)

#### 関数 {#function}

##### PC


kintone.createDialog(config)


#### 引数 {#parameters}

| 引数名 | 型 | 必須 | 説明 |
|:--|:--|:--|:--|
| config | オブジェクト | 必須 | ダイアログの設定 |
| config.title | 文字列 | 省略可 | タイトル文字列<br />省略した場合は表示されません。 |
| config.body | Elementオブジェクト | 省略可 | ダイアログ本文の要素<br />省略した場合は表示されません。 |
| config.showOkButton | 真偽値 | 省略可 | OKボタンを表示するかどうか<ul><li>`true`：表示する</li><li>`false`：表示しない</li></ul>省略した場合は表示されます。 |
| config.okButtonText | 文字列 | 省略可 | OKボタンに表示するテキスト<br />省略した場合はログインユーザーの言語にしたがって「OK」を意味するテキストが表示されます。 |
| config.showCancelButton | 真偽値 | 省略可 | キャンセルボタンを表示するかどうか<ul><li>`true`：表示する</li><li>`false`：表示しない</li></ul>省略した場合は表示されません。 |
| config.cancelButtonText | 文字列 | 省略可 | キャンセルボタンに表示するテキスト<br />省略した場合はログインユーザーの言語にしたがって「Cancel」を意味するテキストが表示されます。 |
| config.showCloseButton | 真偽値 | 省略可 | 閉じるボタンを表示するかどうか<ul><li>`true`：表示する</li><li>`false`：表示しない</li></ul>省略した場合は表示されません。<br />表示しない場合、Escキーでダイアログを閉じる機能も無効化されます。 |
| config.beforeClose | 関数 | 省略可 | OKボタン／キャンセルボタン／閉じるボタン／Escキーのいずれかの操作でダイアログを閉じる前に実行される関数<br />関数の引数にはユーザーが選択した操作が渡されます。<ul><li>`OK`：OKボタンをクリック</li><li>`CANCEL`：キャンセルボタンをクリック</li><li>`CLOSE`：閉じるボタンをクリック、またはEscキーを押下</li></ul>関数の戻り値として`false`、またはPromiseの解決後に`false`になる値を返した場合はダイアログを閉じません。 |

#### 戻り値 {#response}

戻り値はPromiseオブジェクトです。  
Promiseオブジェクトの解決時に次の値が取得できます。

| 戻り値 | 型 | 説明 |
|:--|:--|:--|
| show | 関数 | 作成したダイアログを表示する非同期な関数<br />引数はありません。<br />戻り値はPromiseオブジェクトです。<br />ダイアログを閉じるとPromiseオブジェクトが解決され次の値が取得できます。<ul><li>`OK`：ユーザーがOKボタンをクリックしたとき</li><li>`CANCEL`：ユーザーがキャンセルボタンをクリックしたとき</li><li>`CLOSE`：ユーザーが閉じるボタンをクリックしたとき、またはEscキーを押下したとき</li><li>`FUNCTION`：close関数が呼び出されたとき</li></ul> |
| close | 関数 | ダイアログを閉じる関数<br />引数および戻り値はありません。 |

#### 利用できる画面 {#available-pages}

##### PC

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](id/394dea74a167d5bca527ec3f/#available-pages)  

ただし、次の画面では利用できません。  

- 検索画面
- アプリストア

#### サンプルコード {#sample-code}

```javascript
const bodyElement = document.createElement('p');
bodyElement.textContent = 'このレコードを削除しますか？';

// ダイアログを作成する
const dialog = await kintone.createDialog({
  title: '確認',
  body: bodyElement,
  okButtonText: '削除する',
  showCancelButton: true,
  cancelButtonText: 'キャンセル',
  showCloseButton: true,
  beforeClose: (action) => {
    if (action === 'OK') {
      console.log('削除する');
      // 削除処理
    } else {
      console.log('削除をキャンセルしました');
    }
  }
});

// ダイアログを表示する
await dialog.show();
```

#### 注意事項 {#notes}

引数の`config.body`に指定されたElementオブジェクトは、そのままダイアログ本文の要素として組み込まれます。  
必要に応じてサニタイズ処理を行ってください。
