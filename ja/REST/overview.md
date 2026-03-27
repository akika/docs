---
title: "kintone REST API"
description: "データ連携のためのAPIです。レコードの取得／登録／更新／削除や、ファイルのアップロード／ダウンロードのAPIがあります。また、アプリの情報取得やフォームの情報取得のAPIもあります。"
product: kintone
weight: 300
layout: single-sidebar-accordion
type: single
aliases:
  - "/ja/id/de8fa2714f80a6bdacad6cb4/"
---

kintone REST APIの使い方は、次のチュートリアルを参照してください。  
[kintone REST APIを使ってみよう](/id/ef64b29134b8e8e4a1945c84/)

### レコード {#record}

#### レコードの取得／登録／更新／削除 {#record-record}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| 1件のレコードを取得する | GET | [/k/v1/record.json](/id/ca1c4e932b47856d3eb1a819/) |
| 1件のレコードを登録する | POST | [/k/v1/record.json](/id/e7f3125797f78aaec154b918/) |
| 1件のレコードを更新する | PUT | [/k/v1/record.json](/id/607d2f57a86f03ca70588ab8/) |
| 複数のレコードを取得する | GET | [/k/v1/records.json](/id/ba1703e9391653c667ce958b/) |
| 複数のレコードを登録する | POST | [/k/v1/records.json](/id/5cf0698779c8854753d5b61f/) |
| 複数のレコードを更新する | PUT | [/k/v1/records.json](/id/0cc38cb334db46c7413c667c/) |
|複数のレコードを削除する | DELETE | [/k/v1/records.json](/id/3e09998aa236ef52743338f9/) |
| （レコードの一括取得）カーソルを作成する | POST | [/k/v1/records/cursor.json](/id/4e59634133e0f320b35f8711/) |
| （レコードの一括取得）カーソルからレコードを取得する | GET | [/k/v1/records/cursor.json](/id/22f3376b9638cc7d94b8ad57/) |
| （レコードの一括取得）カーソルを削除する | DELETE | [/k/v1/records/cursor.json](/id/f2b87ac0eafb5c6fad2fdbfb/) |

#### レコードのコメントの操作 {#record-comment}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| レコードのコメントを取得する | GET | [/k/v1/record/comments.json](/id/b74703885198a01fe8a948ba/) |
| レコードにコメントを投稿する | POST | [/k/v1/record/comment.json](/id/45dbf35056918f6a13549f70/) |
| レコードのコメントを削除する | DELETE | [/k/v1/record/comment.json](/id/bd7c8ed72e071bc0ed6731cd/) |

#### プロセス管理の操作 {#record-process}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| レコードの作業者を更新する | PUT | [/k/v1/record/assignees.json](/id/709d819774fd8c4e0960c1a7/) |
| 1件のレコードのステータスを更新する | PUT | [/k/v1/record/status.json](/id/ff1f30dda4461d5bb807af27/) |
| 複数のレコードのステータスを更新する | PUT | [/k/v1/records/status.json](/id/044d255131483eaf4fe66756/) |

#### その他 {#record-other}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| 複数アプリのレコード操作を一括処理する | POST | [/k/v1/bulkRequest.json](/id/bc41b4cb11864e868abd2eb2/) |
| APIを実行したユーザーのレコードのアクセス権の設定を取得する | GET | [/k/v1/records/acl/evaluate.json](/id/e5b4dc5768ba266a21dd2964/) |

### ファイル {#file}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| ファイルをダウンロードする | GET | [/k/v1/file.json](/id/c5da2ff7d17ed3b5764a4a3f/) |
| ファイルをアップロードする | POST | [/k/v1/file.json](/id/bb1225dd8d192245c3645a95/) |

### アプリ {#app}

アプリに関するAPIには、2つのURLがあります。  
詳細は、各ドキュメントを確認してください。

- アプリの動作を確認するテスト環境に反映するURL：「/k/v1/**preview**/`API_PATH`.json」
- 本番環境に反映するURL：「/k/v1/`API_PATH`.json」

#### アプリ情報 {#info}

|  | HTTPメソッド | URL | 備考 |
| :-- | :-- | :-- | :-- |
| 1件のアプリの情報を取得する | GET | [/k/v1/app.json](/id/f9f95e788d8e6cdbc42da01f/) ||
| 複数のアプリの情報を取得する | GET | [/k/v1/apps.json](/id/bc9738cfc60c75502dedfc20/) ||
| 動作テスト環境にアプリを作成する | POST | [/k/v1/preview/app.json](/id/be316bcfaa096d7943d4e669/) ||
| アプリの使用状況を取得する | GET | [/k/v1/apps/statistics.json](/id/87b9a4d7093e6c78b1dff270/) |ワイドコースのみ|
| アプリ管理者用メモを取得する | GET | [/k/v1/app/adminNotes.json<br />/k/v1/preview/app/adminNotes.json](/id/6b336db6f0404cf2cb2a0056/) ||
| アプリ管理者用メモを変更する | PUT | [/k/v1/preview/app/adminNotes.json](/id/36e66a8eaed28aab195bcc45/) ||

#### フォーム {#app-form}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| フィールドを取得する | GET | [/k/v1/app/form/fields.json<br />/k/v1/preview/app/form/fields.json](/id/27655375153b121d98533774/) |
| フィールドを追加する | POST | [/k/v1/preview/app/form/fields.json](/id/cdeb42b35921e6d4f137208f/) |
| フィールドの設定を変更する | PUT | [/k/v1/preview/app/form/fields.json](/id/624e263fbf459af64cfb3d35/) |
| フィールドを削除する | DELETE | [/k/v1/preview/app/form/fields.json](/id/7217d82119f8399506fb6f25/) |
| フォームのレイアウトを取得する | GET | [/k/v1/app/form/layout.json<br />/k/v1/preview/app/form/layout.json](/id/c519d299340cf1606c0611cb/) |
| フォームのレイアウトを変更する | PUT | [/k/v1/preview/app/form/layout.json](/id/ab3a01794c08a2e60573e6ba/) |
| フォームの設計情報を取得する | GET | [/k/v1/form.json<br />/k/v1/preview/form.json](/id/2c5dd59423a6a3ba11dd063e/) |

#### 一覧 {#app-view}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| 一覧の設定を取得する | GET | [/k/v1/app/views.json<br />/k/v1/preview/app/views.json](/id/c4c5befe425032f6c36b9c4b/) |
| 一覧の設定を変更する | PUT | [/k/v1/preview/app/views.json](/id/578dd5e90f674cd4e6075c17/) |

#### グラフ {#app-report}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| グラフの設定を取得する | GET | [/k/v1/app/reports.json<br />/k/v1/preview/app/reports.json](/id/33ebaf1dd8e1ec09c22aa938/) |
| グラフの設定を変更する | PUT | [/k/v1/preview/app/reports.json](/id/651618fce78670408b1931fb/) |

#### アプリの設定 {#app-settings}

##### 一般設定

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| アプリの一般設定を取得する | GET | [/k/v1/app/settings.json<br />/k/v1/preview/app/settings.json](/id/8728eba2a728ae1dd0af3fec/) |
| アプリの一般設定を変更する | PUT | [/k/v1/preview/app/settings.json](/id/65b118066af4efd01f103de5/) |
| プロセス管理の設定を取得する | GET | [/k/v1/app/status.json<br />/k/v1/preview/app/status.json](/id/b74914ae9d60fb454d48fb07/) |
| プロセス管理の設定を変更する | PUT | [/k/v1/preview/app/status.json](/id/3bcd41df582e8d4a8f5de017/) |
| アプリの設定の運用環境への反映状況を確認する | GET | [/k/v1/preview/app/deploy.json](/id/d87cdb0253f91784ecb74a09/) |
| アプリの設定を運用環境へ反映する | POST | [/k/v1/preview/app/deploy.json](/id/11f6926af40fdc7907b1e3a3/) |

##### カスタマイズ／サービス連携

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| アプリに追加されているプラグインの一覧を取得する | GET | [/k/v1/app/plugins.json<br />/k/v1/preview/app/plugins.json](/id/f6f52cc42fbddf4ec1a2d783/) |
| アプリにプラグインを追加する | POST | [/k/v1/preview/app/plugins.json](/id/43c9f463d7eab7285396f1a1/) |
| JavaScript / CSS カスタマイズ設定を取得する | GET | [/k/v1/app/customize.json<br />/k/v1/preview/app/customize.json](/id/9b499a476dafed45a6f62dd3/) |
| JavaScript / CSS カスタマイズ設定を変更する | PUT | [/k/v1/preview/app/customize.json](/id/f954b1b1daf7728c3db7f9a2/) |

##### 通知

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| アプリの条件通知の設定を取得する | GET | [/k/v1/app/notifications/general.json<br />/k/v1/preview/app/notifications/general.json](/id/1b335d06a15cb14a63de6c31/) |
| アプリの条件通知の設定を変更する | PUT | [/k/v1/preview/app/notifications/general.json](/id/07dce8a40d8f19b443ece685/) |
| レコードの条件通知の設定を取得する | GET | [/k/v1/app/notifications/perRecord.json<br />/k/v1/preview/app/notifications/perRecord.json](/id/c97b592ff7123b33f612e511/) |
| レコードの条件通知の設定を変更する | PUT | [/k/v1/preview/app/notifications/perRecord.json](/id/3897bdf9cc4e7e827ec144bd/) |
| リマインダーの条件通知の設定を取得する | GET | [/k/v1/app/notifications/reminder.json<br />/k/v1/preview/app/notifications/reminder.json](/id/1d8e27cf54cafeea137c9c9a/) |
| リマインダーの条件通知の設定を変更する | PUT | [/k/v1/preview/app/notifications/reminder.json](/id/40cd28137a44cc3967aafeb7/) |

##### アクセス権

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| アプリのアクセス権の設定を取得する | GET | [/k/v1/app/acl.json<br />/k/v1/preview/app/acl.json](/id/44f492901695be0e04995639/) |
| アプリのアクセス権の設定を変更する | PUT | [/k/v1/app/acl.json<br />/k/v1/preview/app/acl.json](/id/44b696f92ed866eeaedbfda6/) |
| レコードのアクセス権の設定を取得する | GET | [/k/v1/record/acl.json<br />/k/v1/preview/record/acl.json](/id/a477d376052721249caa89ac/) |
| レコードのアクセス権の設定を変更する | PUT | [/k/v1/record/acl.json<br />/k/v1/preview/record/acl.json](/id/8146d61095ad5e89160e4483/) |
| フィールドのアクセス権の設定を取得する | GET | [/k/v1/field/acl.json<br />/k/v1/preview/field/acl.json](/id/b5b686dfcf2f8c131c28ed6a/) |
| フィールドのアクセス権の設定を変更する | PUT | [/k/v1/field/acl.json<br />/k/v1/preview/field/acl.json](/id/942e8542b200b829f8b3bac7/) |

##### その他の設定

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| アプリのアクション設定を取得する | GET | [/k/v1/app/actions.json<br />/k/v1/preview/app/actions.json](/id/f7d1613d42dd28f38e7d9ae9/) |
| アプリのアクション設定を変更する | PUT | [/k/v1/preview/app/actions.json](/id/1d8ac4b88d5a12468c0665f7/) |

##### 運用管理

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| アプリの所属するスペースを変更する | POST | [/k/v1/app/move.json](/id/ed4007715721805df315ed47/) |

### スペース {#space}

#### スペース {#space-space}

|  | HTTPメソッド | URL | 備考 |
| :-- | :-- | :-- | :-- |
| スペースの情報を取得する | GET | [/k/v1/space.json](/id/6e2a365943e303fbb30f01de/) ||
| スペースの設定を変更する | PUT | [/k/v1/space.json](/id/d85a81945868db8c288a3b11/) ||
| テンプレートからスペースを作成する | POST | [/k/v1/template/space.json](/id/d8ea4eaea0b2fc619ba7c782/) ||
| スペースを削除する | DELETE | [/k/v1/space.json](/id/f64a35f9aad6459095e4dc17/) ||
| スペースの本文を更新する | PUT | [/k/v1/space/body.json](/id/cf580126da2b465115ded1e6/) ||
| スペースのメンバーとスペース管理者の情報を取得する | GET | [/k/v1/space/members.json](/id/febe6f4eb7efa2f2c77f583d/) ||
| スペースのメンバーを更新する | PUT | [/k/v1/space/members.json](/id/9227d39612c7a78c9161ad53/) ||
| スペースの使用状況を取得する | GET | [/k/v1/space/statistics.json](/id/8d2d6e955eea07f32b8af62d/) |ワイドコースのみ|

#### スレッド {#space-thread}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| スペースのスレッドを作成する | POST | [/k/v1/space/thread.json](/id/24a2ad8d0fb574f3617e1b92/) |
| スペースのスレッドを更新する | PUT | [/k/v1/space/thread.json](/id/030c46e9b685a5eee19637f0/) |
| スペースのスレッドにコメントを投稿する | POST | [/k/v1/space/thread/comment.json](/id/bcacb3ceff7039b39222ebb4/) |

#### ゲストユーザーとゲストスペース {#space-guest}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| ゲストユーザーを追加する | POST | [/k/v1/guests.json](/id/29318cb3da48dfeb065b884d/) |
| ゲストユーザーを削除する | DELETE | [/k/v1/guests.json](/id/943e420d94eb3d018df68d28/) |
| ゲストスペースのゲストメンバーを更新する | PUT | [/k/guest/`GUEST_SPACE_ID`/v1/space/guests.json](/id/712234897391d75133c3d464/) |

### プラグイン {#plugin}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| インストール済みのプラグインの一覧を取得する | GET | [/k/v1/plugins.json](/id/ace5777d9375efed42500278/) |
| インストールが必要なプラグインの一覧を取得する | GET | [/k/v1/plugins/required.json](/id/56524ae67a377d756e329bd2/) |
| プラグインを追加しているアプリの一覧を取得する | GET | [/k/v1/plugin/apps.json](/id/d756f228bad9ca044866aed0/) |
| プラグインを読み込む | POST | [/k/v1/plugin.json](/id/6806ccee84420bfaf17ae74f/) |
| プラグインを更新する | PUT | [/k/v1/plugin.json](/id/4c0e93986f6a7c08033d874f/) |
| プラグインをアンインストールする | DELETE | [/k/v1/plugin.json](/id/8c2031cc1081afd160007699/) |

### API情報 {#apis}

|  | HTTPメソッド | URL |
| :-- | :-- | :-- |
| kintone REST APIの一覧を取得する | GET | [/k/v1/apis.json](/id/b9eb79547d5b2eb184d56b7f/) |
| kintone REST APIのスキーマ情報を取得する | GET | [/k/v1/apis/\*.json](/id/0e51c5da54396a7a916f10b5/) |
