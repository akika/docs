---
title: "イベントオブジェクトで実行できる操作"
description: "kintoneのイベントオブジェクトで実行できる操作を説明します。"
tocEndLevel: 3
weight: 200
product: kintone
type: single
layout: single-sidebar-accordion
aliases:
  - "/ja/id/073cb99467614b140b2a9c42/"
---

kintoneのイベントオブジェクトで実行できる操作を説明します。


### レコード一覧画面のイベント {#record-list-events}

| | [表示するとき](/id/a7cfce771ab828cfb4d654cf/) | [インライン編集を開始するとき](/id/8d1bc2d35a1aaa39cf7d2d85/) | [フィールドの値を変更するとき](/id/d7b246ea0d5a2789a92f6b35/) | [保存するとき](/id/bab2a87016ccaa3c4cc99c88/) | [保存した後](/id/043bc028a700e0c7e78cae46/) | [削除するとき](/id/886240ad14145f8817ceb086/) |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| [フィールドの値を書き換える](#record-list-overwrite-field-values)  | ✕ | ✕ | ◯ | ◯ | ✕ | ✕ |
| [フィールドの編集可／不可を設定する](#record-list-enable-disable-field-edits)  | ✕  | ◯ | ◯ | ✕ | ✕ | ✕ |
| [フィールドにエラーを表示する](#record-list-show-field-errors)  | ✕ | ✕ | ◯ | ◯ | ✕ | ✕ |
| [画面上部にエラーを表示する](#record-list-show-record-errors) | ✕ | ✕ | ◯ | ◯ | ✕ | ◯ |
| [指定したURLに遷移する](#record-list-specify-the-url-property)  | ✕  | ✕ | ✕ | ✕ | ◯ | ✕ |
| [Promise対応](#support-promise) | ◯ | ◯ | ✕  | ◯ | ✕ | ◯ |
 レコード一覧画面のイベントでフィールドの値を書き換える操作には、[非対応フィールド](#record-list-overwrite-field-values-unsupported-fields)があります。 
 レコード一覧画面のイベントでフィールドの編集可／不可を設定する操作には、[非対応フィールド](#record-list-enable-disable-field-edits-unsupported-fields)があります。 
 レコード一覧画面のイベントでフィールドにエラーを表示する操作には、[非対応フィールド](#record-list-show-field-errors-unsupported-fields)があります。 
#### フィールドの値を書き換える {#record-list-overwrite-field-values}

フィールドの値を書き換えるには、イベントハンドラー内でレコードのフィールドの値を変更し、イベントオブジェクトをreturnします。

- フィールドの編集を不可に設定しても、値を書き換えることができます。  
  [フィールドの編集可／不可を設定する](#record-list-enable-disable-field-edits)
- 編集権限のないフィールドの値を書き換えた場合、フィールドの値を変更できません。  
- 同じイベントタイプの複数のハンドラーが登録されている場合、最後のハンドラーがreturnした値を基準に反映されます。  
  最後に実行されるハンドラーがイベントオブジェクトをreturnしない場合、フィールドの値は反映されません。

##### 非対応フィールド {#record-list-overwrite-field-values-unsupported-fields}

次のフィールドは、フィールドの値を書き換えてreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行
- 添付ファイル
- ルックアップ
- ルックアップコピー先フィールド

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、文字列1行（フィールドコード：`文字列_0`）の値を書き換える例です。

```js
kintone.events.on('app.record.index.edit.change.ドロップダウン_0', (event) => {
  const record = event.record;
  record['文字列_0'].value = 'この文字列で上書き';
  return event;
});
```

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）の値を書き換える例です。

```js
kintone.events.on('app.record.index.edit.change.ドロップダウン_0', (event) => {
  const tableRow = event.record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].value = 'テーブルの1行目を上書き';
  return event;
});
```

#### フィールドの編集可／不可を設定する {#record-list-enable-disable-field-edits}

フィールドに編集可／不可を設定するには、イベントハンドラー内でフィールドの`disabled`プロパティに真偽値を設定して、イベントオブジェクトをreturnします。

- 編集可にするとき：「false」
- 編集不可にするとき：「true」

編集権限のないフィールドの`disabled`プロパティに「false」を設定しても、フィールドは編集可になりません。

##### 非対応フィールド {#record-list-enable-disable-field-edits-unsupported-fields}

次のフィールドの値は、編集可／不可を設定してreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）の値が変更されたとき、文字列1行（フィールドコード：`文字列_0`）を編集不可にする例です。

```js
kintone.events.on('app.record.index.edit.change.ドロップダウン_0', (event) => {
  const record = event.record;
  record['文字列_0'].disabled = true;
  return event;
});
```

#### フィールドにエラーを表示する {#record-list-show-field-errors}

フィールドにエラーメッセージを表示するには、イベントハンドラー内でフィールドの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-list-overwrite-field-values)  
  [フィールドの編集可／不可を設定する](#record-list-enable-disable-field-edits)
- 設定したメッセージを消すには「null」を設定します。

##### 非対応フィールド {#record-list-show-field-errors-unsupported-fields}

次のフィールドは、エラーメッセージを設定しても、エラーは発生しません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、文字列1行（フィールドコード：`文字列_0`）にエラーを表示する例です。

```js
kintone.events.on('app.record.index.edit.change.ドロップダウン_0', (event) => {
  const record = event.record;
  record['文字列_0'].error = 'エラーです！';
  return event;
});
```

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）にエラーを表示する例です。

```js
kintone.events.on('app.record.index.edit.change.ドロップダウン_0', (event) => {
  const tableRow = event.record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].error = 'エラーです！';
  return event;
});
```

#### 画面上部にエラーを表示する {#record-list-show-record-errors}

画面上部にエラーメッセージを表示するには、イベントハンドラー内でeventの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-list-overwrite-field-values)  
  [フィールドの編集可／不可を設定する](#record-list-enable-disable-field-edits)

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、画面上部にエラーを表示する例です。

```js
kintone.events.on('app.record.create.change.ドロップダウン_0', (event) => {
  event.error = 'エラーです！';
  return event;
});
```

#### 指定したURLに遷移する {#record-list-specify-the-url-property}

イベント処理後に指定したURLへ遷移するには、イベントハンドラー内で`url`プロパティに遷移するURLを設定して、イベントオブジェクトをreturnします。

- 「null」を設定すると、画面の遷移は発生しません。

##### サンプルコード

レコードの保存成功後に「https\://cybozu.co.jp」へ遷移する例です。

```js
kintone.events.on('app.record.index.edit.submit.success', (event) => {
  event.url = 'https://cybozu.co.jp';
  return event;
});
```

### レコード詳細画面のイベント {#record-details-events}

| | [表示するとき](/id/12aad5aeaa4c1b4f3ff384b8/) | [削除するとき](/id/8bc93e47b3daa8eeb65b810b/) | [プロセス管理でアクションを実行するとき](/id/ef0771670e41ce94b25cce7a/) |
| :--- | :--- | :--- | :--- |
| [フィールドの値を書き換える](#record-details-overwrite-field-values)  | ✕ | ✕ | ◯ |
| [画面上部にエラーを表示する](#record-details-show-record-errors) | ✕ | ◯ | ◯ |
| [Promise対応](#support-promise) | ◯ | ◯ | ◯ |
 レコード詳細画面のイベントでフィールドの値を書き換える操作には、[非対応フィールド](#record-details-overwrite-field-values-unsupported-fields)があります。 
#### フィールドの値を書き換える {#record-details-overwrite-field-values}

フィールドの値を書き換えるには、イベントハンドラー内でレコードのフィールドの値を変更し、イベントオブジェクトをreturnします。

- 値を書き換えるには、レコードの編集権限が必要です。
- ラジオボタンフィールドに空文字列を指定した場合、ラジオボタンの初期値に設定されている選択肢が選ばれます。
- 編集権限のないフィールドの値を書き換えた場合、フィールドの値を変更できません。  
- 同じイベントタイプの複数のハンドラーが登録されている場合、最後のハンドラーがreturnした値を基準に反映されます。  
  最後に実行されるハンドラーがイベントオブジェクトをreturnしない場合、フィールドの値は反映されません。

##### 非対応フィールド {#record-details-overwrite-field-values-unsupported-fields}

次のフィールドは、フィールドの値を書き換えてreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行
- 添付ファイル
- ルックアップ
- ルックアップコピー先フィールド

##### サンプルコード

プロセスのアクションを実行して次のステータスに変わったとき、文字列1行（フィールドコード：`文字列_0`）の値を書き換える例です。

```js
kintone.events.on('app.record.detail.process.proceed', (event) => {
  const record = event.record;
  record['文字列_0'].value = 'この文字列で上書き';
  return event;
});
```

プロセスのアクション実行後、次のステータスに変わったとき、テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）の値を書き換える例です。

```js
kintone.events.on('app.record.detail.process.proceed', (event) => {
  const record = event.record;
  const tableRow = record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].value = 'テーブルの1行目を上書き';
  return event;
});
```

#### 画面上部にエラーを表示する {#record-details-show-record-errors}

画面上部にエラーメッセージを表示するには、イベントハンドラー内でフィールドの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-details-overwrite-field-values)  
- PCのみで利用できます。

##### サンプルコード

レコード詳細画面でレコードを削除するとき、レコードにエラーを表示する例です。

```js
kintone.events.on('app.record.detail.delete.submit', (event) => {
  event.error = 'エラーです';
  return event;
});
```

### レコード追加画面のイベント {#record-create-events}

| | [表示するとき](/id/6a31504b599c450eb14a4a00/) | [フィールドの値を変更するとき](/id/3a1f2cd8fce89e4c74d66dac/) | [保存するとき](/id/3764737cfb553b8da2064315/) | [保存した後](/id/73fe105cd172f6b35f80d416/) |
| :-- | :-- | :-- | :- | :--  |
| [フィールドの値を書き換える](#record-create-overwrite-field-values)  | ◯  | ◯ | ◯ | ✕ |
| [フィールドの編集可／不可を設定する](#record-create-enable-disable-fields)  | ◯ | ◯ | ✕ | ✕ |
| [フィールドにエラーを表示する](#record-create-show-field-errors)  | ◯ | ◯ | ◯ | ✕ |
| [画面上部にエラーを表示する](#record-create-show-record-errors) | ◯ | ◯  | ◯ | ✕ |
| [ルックアップを自動取得する](#record-create-run-lookup-fields) | ◯ | ◯  | ✕ | ✕ |
| [ルックアップのコピー先のフィールドの値を自動でクリアする](#record-create-clear-lookup-fields) | ◯ | ◯  | ✕ | ✕ |
| [値を変更したフィールドやテーブル行のフィールドデータを取得する](#record-create-get-the-object-of-the-edited-field-or-table-row) | ✕ | ◯  | ✕ | ✕ |
| [指定したURLに遷移する](#record-create-specify-the-url-property) | ✕ | ✕  | ✕ | ◯ |
| [Promise対応](#support-promise) | ◯ | ✕  | ◯ | ◯ |
 レコード追加画面のイベントでフィールドの値を書き換える操作には、[非対応フィールド](#record-create-overwrite-field-values-unsupported-fields)があります。 
 レコード追加画面を表示した後のイベントでフィールドの値を書き換える操作では、ルックアップフィールドの値を変更できます。 
 レコード追加画面のイベントでフィールドの編集可／不可を設定する操作には、[非対応フィールド](#record-create-enable-disable-fields-unsupported-fields)があります。 
 レコード追加画面のイベントでフィールドにエラーを表示する操作には、[非対応フィールド](#record-create-show-field-errors-unsupported-fields)があります。 
#### フィールドの値を書き換える {#record-create-overwrite-field-values}

フィールドの値を書き換えるには、イベントハンドラー内でレコードのフィールドの値を変更し、イベントオブジェクトをreturnします。

- フィールドの編集を不可に設定しても、フィールドの値を書き換えることができます。  
  [フィールドの編集可／不可を設定する](#record-create-enable-disable-fields)
- 編集権限のないフィールドの値を書き換えた場合、フィールドの値を変更できません。  
- 同じイベントタイプの複数のハンドラーが登録されている場合、最後のハンドラーがreturnした値を基準に反映されます。  
  最後に実行されるハンドラーがイベントオブジェクトをreturnしない場合、フィールドの値は反映されません。

##### 非対応フィールド {#record-create-overwrite-field-values-unsupported-fields}

次のフィールドは、フィールドの値を書き換えてreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行
- 添付ファイル
- ルックアップ
- ルックアップコピー先フィールド

##### サンプルコード

文字列1行（フィールドコード：`文字列_0`）に初期値をセットする例です。

```js
kintone.events.on('app.record.create.show', (event) => {
  const record = event.record;
  record['文字列_0'].value = 'この文字列で上書き';
  return event;
});
```

次のことを行う例です。

- テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）に初期値を設定する。
- テーブルの末尾に行を追加する。

```js
kintone.events.on('app.record.create.show', (event) => {
  const record = event.record;
  const tableRow = record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].value = 'テーブルの1行目を上書き';

  // テーブルの末尾に行を追加する
  const newRow = {
    value: {
      文字列_1: {
        type: 'SINGLE_LINE_TEXT', // テーブルの行を追加するには、フィールドタイプを指定する必要がある
        value: 'テーブルに追加する行',
      },
    },
  };
  tableRow.push(newRow);
  return event;
});
```

#### フィールドの編集可／不可を設定する {#record-create-enable-disable-fields}

フィールドに編集可／不可を設定するには、イベントハンドラー内でフィールドの`disabled`プロパティに真偽値を設定して、イベントオブジェクトをreturnします。

- 編集可にするとき：「false」
- 編集不可にするとき：「true」

編集権限のないフィールドの`disabled`プロパティに「false」を設定しても、フィールドは編集可になりません。

##### 非対応フィールド {#record-create-enable-disable-fields-unsupported-fields}

次のフィールドの値は、編集可／不可を設定してreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）の値が変更されたとき、文字列1行（フィールドコード：`文字列_0`）を編集不可にする例です。

```js
kintone.events.on('app.record.create.change.ドロップダウン_0', (event) => {
  const record = event.record;
  record['文字列_0'].disabled = true;
  return event;
});
```

#### フィールドにエラーを表示する {#record-create-show-field-errors}

フィールドにエラーメッセージを表示するには、イベントハンドラー内でフィールドの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-create-overwrite-field-values)  
  [フィールドの編集可／不可を設定する](#record-create-enable-disable-fields)
- 設定したメッセージを消すには「null」を設定します。

##### 非対応フィールド {#record-create-show-field-errors-unsupported-fields}

次のフィールドは、エラーメッセージを設定しても、エラーは発生しません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、文字列1行（フィールドコード：`文字列_0`）にエラーを表示する例です。

```js
kintone.events.on('app.record.create.change.ドロップダウン_0', (event) => {
  const record = event.record;
  record['文字列_0'].error = 'このエラーメッセージを表示';
  return event;
});
```

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）にエラーを表示する例です。

```js
kintone.events.on('app.record.create.change.ドロップダウン_0', (event) => {
  const record = event.record;
  const tableRow = record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].error = 'テーブルの1行目にエラーを表示';
  return event;
});
```

#### 画面上部にエラーを表示する {#record-create-show-record-errors}

画面上部にエラーメッセージを表示するには、イベントハンドラー内でフィールドの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-create-overwrite-field-values)  
  [フィールドの編集可／不可を設定する](#record-create-enable-disable-fields)

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、画面上部にエラーを表示する例です。

```js
kintone.events.on('app.record.create.change.ドロップダウン_0', (event) => {
  event.error = 'エラーです！';
  return event;
});
```

#### ルックアップを自動取得する {#record-create-run-lookup-fields}

ルックアップのコピー先の値を自動で設定するには、ルックアップフィールドの`lookup`プロパティに「UPDATE」または「true」を設定して、イベントオブジェクトをreturnします。

- ルックアップの検索結果が1件の場合のみ、自動取得できます。

##### サンプルコード

レコード追加画面を開いたとき、ルックアップ（フィールドコード：`ルックアップ_0`）に値を設定してデータを取得する例です。

```js
kintone.events.on('app.record.create.show', (event) => {
  const record = event.record;
  record['ルックアップ_0'].value = '0001';
  record['ルックアップ_0'].lookup = true;
  // またはrecord['ルックアップ'].lookup = 'UPDATE';
  return event;
});
```

#### ルックアップのコピー先のフィールドの値を自動でクリアする {#record-create-clear-lookup-fields}

ルックアップのコピー先の値を自動でクリアするには、ルックアップフィールドの`lookup`プロパティに「CLEAR」を設定して、イベントオブジェクトをreturnします。

##### サンプルコード

レコード追加画面を開いたとき、ルックアップ（フィールドコード：`ルックアップ_0`）のコピー先のフィールドの値を空にする例です。

```js
kintone.events.on('app.record.create.show', (event) => {
  const record = event.record;
  record['ルックアップ_0'].lookup = 'CLEAR';
  return event;
});
```

#### 値を変更したフィールドやテーブル行のフィールドデータを取得する {#record-create-get-the-object-of-the-edited-field-or-table-row}

変更のあったフィールドやテーブル行のフィールドのデータを取得します。

- `row`プロパティは、テーブル内のイベント時のみ取得できます。
- テーブル内の行を削除した際には、`row`プロパティは「null」になります。

##### サンプルコード

レコード追加画面で、ドロップダウン（フィールドコード：`ドロップダウン_0`）の値が変更されたときの、変更のあったテーブルの行データを取得する例です。


```js
kintone.events.on('app.record.create.change.ドロップダウン_0', (event) => {
  const row = event.changes.row;
  const field = event.changes.field;
  return event;
});
```

#### 指定したURLに遷移する {#record-create-specify-the-url-property}

イベント処理後に指定したURLへ遷移するには、イベントハンドラー内で`url`プロパティに遷移するURLを設定して、イベントオブジェクトをreturnします。

- 「null」を設定すると、画面の遷移は発生しません。

##### サンプルコード

レコードの保存成功後に「https\://cybozu.co.jp」へ遷移する例です。

```js
kintone.events.on('app.record.create.submit.success', (event) => {
  event.url = 'http://cybozu.co.jp/';
  return event;
});
```

### レコード編集画面のイベント {#record-edit-events}

| | [表示するとき](/id/bc5184e1f493d2c532c2cee2/) | [フィールドの値を変更するとき](/id/60e99be9aeb482927cc26c54/) | [保存するとき](/id/f0b69a0bf181f5c7071d082c/) | [保存した後](/id/2cf94dc37d3bbaded43e6569/) |
| :--- | :--- | :--- | :--- | :--- |
| [フィールドの値を書き換える](#record-edit-overwrite-field-values)  | ◯  | ◯ | ◯ | × |
| [フィールドの編集可／不可を設定する](#record-edit-enable-disable-field-edits)  | ◯ | ◯ | × | × |
| [フィールドにエラーを表示する](#record-edit-show-field-errors)  | ◯ | ◯ | ◯ | × |
| [画面上部にエラーを表示する](#record-edit-show-record-errors) | ◯ | ◯ | ◯ | × |
| [ルックアップを自動取得する](#record-edit-run-lookup-fields) | ◯ | ◯ | × | × |
| [ルックアップのコピー先のフィールドの値を自動でクリアする](#record-edit-clear-copied-lookup-field-values) | ◯ | ◯ | × | × |
| [値を変更したフィールドやテーブル行のフィールドデータを取得する](#record-edit-get-the-object-of-the-edited-field-or-table-row) | × | ◯ | × | × |
| [指定したURLに遷移する](#record-edit-specify-the-url-property) | × | × | × | ◯ |
| [Promise対応](#support-promise) | ◯ | × | ◯ | ◯ |
 レコード編集画面のイベントでフィールドの値を書き換える操作には、[非対応フィールド](#record-edit-overwrite-field-values-unsupported-fields)があります。 
 レコード編集画面を表示した後のイベントでフィールドの値を書き換える操作では、ルックアップフィールドの値を変更できます。 
 レコード編集画面のイベントでフィールドの編集可／不可を設定する操作には、[非対応フィールド](#record-edit-enable-disable-field-edits-unsupported-fields)があります。 
 レコード編集画面のイベントでフィールドにエラーを表示する操作には、[非対応フィールド](#record-edit-show-field-errors-unsupported-fields)があります。 
#### フィールドの値を書き換える {#record-edit-overwrite-field-values}

フィールドの値を書き換えるには、イベントハンドラー内でレコードのフィールドの値を変更し、イベントオブジェクトをreturnします。

- フィールドの編集を不可に設定しても、フィールドの値を書き換えることができます。  
  [フィールドの編集可／不可を設定する](#record-edit-enable-disable-field-edits)
- 編集権限のないフィールドの値を書き換えた場合、フィールドの値を変更できません。  
- 同じイベントタイプの複数のハンドラーが登録されている場合、最後のハンドラーがreturnした値を基準に反映されます。  
  最後に実行されるハンドラーがイベントオブジェクトをreturnしない場合、フィールドの値は反映されません。

##### 非対応フィールド {#record-edit-overwrite-field-values-unsupported-fields}

次のフィールドは、フィールドの値を書き換えてreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行
- 添付ファイル
- ルックアップ
- ルックアップアップのコピー先のフィールド

##### サンプルコード

レコード編集画面を開いたときに、次のフィールドに初期値を設定する例です。

- 文字列1行（フィールドコード：`文字列_0`）
- テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）

```js
kintone.events.on('app.record.edit.show', (event) => {
  const record = event.record;
  record['文字列_0'].value = 'この文字列で上書き';
  const tableRow = record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].value = 'テーブルの1行目を上書き';
  return event;
});
```

#### フィールドの編集可／不可を設定する {#record-edit-enable-disable-field-edits}

フィールドに編集可／不可を設定するには、イベントハンドラー内でフィールドの`disabled`プロパティに真偽値を設定して、イベントオブジェクトをreturnします。

- 編集可にするとき：「false」
- 編集不可にするとき：「true」

編集権限のないフィールドの`disabled`プロパティに「false」を設定しても、フィールドは編集可になりません。

##### 非対応フィールド {#record-edit-enable-disable-field-edits-unsupported-fields}

次のフィールドの値は、編集可／不可を設定してreturnしても、フォームには反映されません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算
- 自動計算にした文字列1行

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）の値が変更になったとき、文字列1行（フィールドコード：`文字列_0`）を編集不可にする例です。

```js
kintone.events.on('app.record.edit.change.ドロップダウン_0', (event) => {
  event.record['文字列_0'].disabled = true;
  return event;
});
```

#### フィールドにエラーを表示する {#record-edit-show-field-errors}

フィールドにエラーメッセージを表示するには、イベントハンドラー内でフィールドの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-edit-overwrite-field-values)  
  [フィールドの編集可／不可を設定する](#record-edit-enable-disable-field-edits)
- 設定したメッセージを消すには「null」を設定します。

##### 非対応フィールド {#record-edit-show-field-errors-unsupported-fields}

次のフィールドは、エラーメッセージを設定しても、エラーは発生しません。

- レコード番号
- 作成者
- 作成日時
- 更新者
- 更新日時
- ステータス
- 作業者
- 計算

##### サンプルコード

次のフィールドにエラーを表示する例です。

- 文字列1行（フィールドコード：`文字列_0`）
- テーブル（フィールドコード：`テーブル_0`）の1行目の文字列1行（フィールドコード：`文字列_1`）

```js
kintone.events.on('app.record.edit.change.ドロップダウン_0', (event) => {
  const record = event.record;
  record['文字列_0'].error = 'このエラーメッセージを表示';
  const tableRow = record['テーブル_0'].value;
  tableRow[0].value['文字列_1'].error = 'テーブルの1行目にエラーを表示';
  return event;
});
```

#### 画面上部にエラーを表示する {#record-edit-show-record-errors}

画面上部にエラーメッセージを表示するには、イベントハンドラー内でフィールドの`error`プロパティに表示するメッセージを設定して、イベントオブジェクトをreturnします。

- 次の設定は、キャンセルされます。  
  [フィールドの値を書き換える](#record-edit-overwrite-field-values)  
  [フィールドの編集可／不可を設定する](#record-edit-enable-disable-field-edits)
- PCとモバイルで利用できます。

##### サンプルコード

ドロップダウン（フィールドコード：`ドロップダウン_0`）のフィールドの値が変更されたとき、画面上部にエラーを表示する例です。

```js
kintone.events.on('app.record.edit.change.ドロップダウン_0', (event) => {
  event.error = 'エラーです！';
  return event;
});
```

#### ルックアップを自動取得する {#record-edit-run-lookup-fields}

ルックアップのコピー先の値を自動で設定するには、ルックアップフィールドの`lookup`プロパティに「UPDATE」または「true」を設定して、イベントオブジェクトをreturnします。

- ルックアップの検索結果が1件の場合のみ、自動取得できます。
- PCとモバイルで利用できます。

##### サンプルコード

レコード編集画面を開いたときに、ルックアップ（フィールドコード：`ルックアップ_0`）に値を設定してデータを取得する例です。

```js
kintone.events.on('app.record.edit.show', (event) => {
  const record = event.record;
  record['ルックアップ_0'].value = '0001'; // ルックアップフィールドの値
  record['ルックアップ_0'].lookup = true; // またはrecord['ルックアップ_0'].lookup = 'UPDATE';
  return event;
});
```

#### ルックアップのコピー先のフィールドの値を自動でクリアする {#record-edit-clear-copied-lookup-field-values}

ルックアップのコピー先の値を自動でクリアするには、ルックアップフィールドの`lookup`プロパティに「CLEAR」を設定して、イベントオブジェクトをreturnします。

- PCとモバイルで利用できます。

##### サンプルコード

レコード編集画面を開いたときに、ルックアップ（フィールドコード：`ルックアップ_0`）のコピー先のフィールドの値を空にする例です。

```js
kintone.events.on('app.record.edit.show', (event) => {
  const record = event.record;
  record['ルックアップ_0'].lookup = 'CLEAR';
  return event;
});
```

#### 値を変更したフィールドやテーブル行のフィールドデータを取得する {#record-edit-get-the-object-of-the-edited-field-or-table-row}

変更のあったフィールドやテーブル行のフィールドのデータを取得します。

- `row`プロパティは、テーブル内のイベント時のみ取得できます。
- テーブル内の行を削除した際には、`row`プロパティは「null」になります。

##### サンプルコード

レコード編集画面で、ドロップダウン（フィールドコード：`ドロップダウン_0`）の値が変更されたときの、変更のあったテーブルの行データを取得する例です。


```js
kintone.events.on('app.record.edit.change.ドロップダウン_0', (event) => {
  const row = event.changes.row;
  const field = event.changes.field;
  return event;
});
```

#### 指定したURLに遷移する {#record-edit-specify-the-url-property}

イベント処理後に指定したURLへ遷移するには、イベントハンドラー内で`url`プロパティに遷移するURLを設定して、イベントオブジェクトをreturnします。

- 「null」を設定すると、画面の遷移は発生しません。

##### サンプルコード

レコードの保存成功後に「https\://cybozu.co.jp」へ遷移する例です。

```js
kintone.events.on('app.record.edit.submit.success', (event) => {
  event.url = 'https://cybozu.co.jp/';
  console.log('url: ' + event.url);
  return event;
});
```

### イベント共通 {#common}

#### Promise対応 {#support-promise}

WebブラウザーのPromiseをreturnすることで、非同期処理の完了を待ってからフィールドの値に応じた制御ができます。  
同じkintoneのイベントに複数のイベントハンドラーが登録されているとき、エラーなどが発生してThenableオブジェクトが棄却された場合には、後続のイベントハンドラーの処理は実行されません。

記述方法は次のページを参考にしてください。  
[kintoneカスタマイズで非同期処理をしてみよう](/id/7f283857d43e6acca99eb5cb/)
