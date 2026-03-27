---
title: イベント処理の記述方法
description: 'イベント処理の記述方法を説明しています。'
tocEndLevel: 4
weight: 100
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/37f50c8d618067d42eee8050/"
---

### イベントハンドラーを登録する {#register-event-handlers}

kintoneで発生するさまざまなイベントとイベントハンドラーを紐付けると、任意の処理を実行できます。

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](/id/394dea74a167d5bca527ec3f/#available-pages)  
プラグイン設定画面でも利用できます。  
ただし、スペースの本文に貼り付けたアプリでは利用できません。

#### 関数 {#register-event-handlers-function}

##### PC／モバイル


kintone.events.on(type, handler)


#### パラメーター名 {#register-event-handlers-parameters}

| 引数 | 型 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| type | 文字列または配列（文字列） | 必須 |イベントハンドラーを紐付けるイベントのタイプ<br />イベントごとに異なります。詳しくは、それぞれのイベントページを確認してください。 |
| handler | 関数 | 必須 | イベント発生時に実行されるイベントハンドラー<br />イベントハンドラーの引数として渡されるイベントオブジェクトは、イベントごとに異なります。詳しくは、それぞれのイベントページを確認してください。<br />Promiseに対応したイベントの場合、イベントハンドラーの内で`Promise`オブジェクトをreturnすることで、非同期処理の完了を待ってからフォームの値に応じた制御ができます。 |

#### 戻り値 {#register-event-handlers-response}

なし

#### サンプルコード {#register-event-handlers-sample-code}

```js
kintone.events.on('app.record.index.show', (event) => {
  console.log(event);
});

// 複数のイベントで同じイベントハンドラーを登録する場合
kintone.events.on(['app.record.create.show', 'app.record.edit.show'], (event) => {
  console.log(event);
});
```

### イベントハンドラーを削除する {#remove-event-handlers}

イベントに紐付けたハンドラーを削除します。

利用できる画面は、全体カスタマイズの適用画面に従います。  
[kintone全体のカスタマイズが適用される画面](/id/394dea74a167d5bca527ec3f/#available-pages)  
プラグイン設定画面でも利用できます。  
ただし、スペースの本文に貼り付けたアプリでは利用できません。

#### 関数 {#remove-event-handlers-function}

##### PC／モバイル


kintone.events.off(type, handler)


#### 引数 {#remove-event-handlers-parameters}

| パラメーター名 | 指定する値 | 必須 | 説明 |
| :-- | :-- | :-- | :-- |
| type | 文字列または文字列の配列 | 省略可 | イベントハンドラーを紐付けるイベントのタイプ<br />イベントごとに異なります。詳しくは、それぞれのイベントページを確認してください。 |
| handler | 関数 | 省略可 | イベント発生時に実行されるイベントハンドラー<br />イベントハンドラーの引数として渡されるイベントオブジェクトは、イベントごとに異なります。詳しくは、それぞれのイベントページを確認してください。<br />Promiseに対応したイベントの場合、イベントハンドラーの内で`Promise`オブジェクトをreturnすることで、非同期処理の完了を待ってからフォームの値に応じた制御ができます。<ul><li>handlerを省略した場合はtypeで指定したタイプのすべてのイベントハンドラーが削除されます。</li><li>typeも省略した場合（引数に何も書かなかった場合）はすべてのタイプのすべてのイベントハンドラーが削除されます。</li></ul> |

#### 戻り値 {#remove-event-handlers-response}

次のいずれかが返ります。

- `true`：ひとつでも削除に成功した場合
- `false`：削除対象のイベントハンドラーがひとつも見つからなかった場合

#### サンプルコード {#remove-event-handlers-sample-code}

```js
const handler = (event) => {
  console.log(event);
};
kintone.events.on('app.record.index.show', handler);

// 指定されたイベントタイプから指定されたハンドラーを削除する
kintone.events.off('app.record.index.show', handler);

// 指定されたイベントタイプからすべてのハンドラーを削除する
kintone.events.off('app.record.index.show');

// すべてのイベントタイプからすべてのハンドラーを削除する
kintone.events.off();
```

### 注意事項 {#limitations}

- 2017年5月版時点で確認している、アプリのJavaScriptファイルの読み込み順は次のとおりです。  
  同じアプリに、アプリのJavaScriptファイル、プラグインのJavaScriptファイルが適用されている場合：
    1. アプリのJavaScriptファイル
    2. プラグインのJavaScriptファイル
- イベントハンドラーは追加されていくのみで、上書きされることはありません。  
  これはJavaScript全般の仕様で、kintone JavaScript APIでもこの仕様に準じます。  
  上書きしたい場合は、設定済みのイベントハンドラーを削除した後に、新しいイベントを登録してください。
- 同じアプリに同じ名前のカテゴリーが存在する場合は、キー名に「カテゴリー」を含むオブジェクトをreturnすると、意図しないカテゴリーを選択することがあります。  
  意図しないカテゴリーを選択する場合は、「カテゴリー」プロパティを削除してからreturnしてください。  
  この現象が発生するイベントは、次のとおりです。
  - レコード一覧画面
    - `app.record.index.edit.submit`
    - `app.record.index.edit.change.フィールドコード`
  - レコード追加画面
    - `app.record.create.show`
    - `app.record.create.submit`
    - `app.record.create.change.フィールドコード`
    - `mobile.app.record.create.show`
    - `mobile.app.record.create.submit`
    - `mobile.app.record.create.change.フィールドコード`
  - レコード編集画面
    - `app.record.edit.show`
    - `app.record.edit.submit`
    - `app.record.edit.change.フィールドコード`
    - `mobile.app.record.edit.show`
    - `mobile.app.record.edit.submit`
    - `mobile.app.record.edit.change.フィールドコード`
  - レコード詳細画面
    - `app.record.detail.process.proceed`
