---
title: "kintone JavaScript API"
description: "kintoneの画面上の動作や見た目を変えるAPIです。JavaScriptファイルをアプリにアップロードして適用することで、ユーザーのkintone画面上で動作します。kintoneにはさまざまなJavaScriptイベントがあり、動作を変更できます。"
product: kintone
layout: single-sidebar-accordion
weight: 400
type: single
aliases:
  - "/ja/id/9744d83c79ac1b73e5cab2c7/"
---

kintone JavaScript APIの基本的な使い方は、チュートリアル「はじめようkintone API」で学ぶことができます。  
[はじめようkintone API](/id/46b0f210829099e8fb07b198/)

### イベント {#event}

イベントの利用方法は、次のページを参照してください。  
[イベント処理の記述方法](/id/37f50c8d618067d42eee8050/)

#### レコード一覧画面 {#event-record-list}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| 一覧画面を表示した後 | [app.record.index.show](/id/a7cfce771ab828cfb4d654cf/) | [mobile.app.record.index.show](/id/a7cfce771ab828cfb4d654cf/) |
| インライン編集を開始したとき | [app.record.index.edit.show](/id/8d1bc2d35a1aaa39cf7d2d85/) | なし |
| インライン編集のフィールド値を変更したとき | [app.record.index.edit.change.`フィールドコード`](/id/d7b246ea0d5a2789a92f6b35/) | なし |
| インライン編集で保存するとき | [app.record.index.edit.submit](/id/bab2a87016ccaa3c4cc99c88/) | なし |
| インライン編集に成功したとき | [app.record.index.edit.submit.success](/id/043bc028a700e0c7e78cae46/) | なし|
| インライン編集が終了したとき | [app.record.index.edit.finish](/id/74707004da36397834ee0a25/) | なし |
| レコードを削除する前 | [app.record.index.delete.submit](/id/886240ad14145f8817ceb086/) | なし |

#### レコード詳細画面 {#event-record-detail}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| レコード詳細画面を表示した後 | [app.record.detail.show](/id/12aad5aeaa4c1b4f3ff384b8/) | [mobile.app.record.detail.show](/id/12aad5aeaa4c1b4f3ff384b8/) |
| レコードを削除する前 | [app.record.detail.delete.submit](/id/8bc93e47b3daa8eeb65b810b/) | [mobile.app.record.detail.delete.submit](/id/8bc93e47b3daa8eeb65b810b/) |
| プロセス管理のアクションを実行したとき | [app.record.detail.process.proceed](/id/ef0771670e41ce94b25cce7a/) | [mobile.app.record.detail.process.proceed](/id/ef0771670e41ce94b25cce7a/) |

#### レコード追加画面 {#event-record-add}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| レコード追加画面を表示した後 | [app.record.create.show](/id/6a31504b599c450eb14a4a00/) | [mobile.app.record.create.show](/id/6a31504b599c450eb14a4a00/) |
| フィールドの値を変更したとき | [app.record.create.change.`フィールドコード`](/id/3a1f2cd8fce89e4c74d66dac/) | [mobile.app.record.create.change.`フィールドコード`](/id/3a1f2cd8fce89e4c74d66dac/) |
| 保存するとき | [app.record.create.submit](/id/3764737cfb553b8da2064315/) | [mobile.app.record.create.submit](/id/3764737cfb553b8da2064315/) |
| 保存に成功した後 | [app.record.create.submit.success](/id/73fe105cd172f6b35f80d416/) | [mobile.app.record.create.submit.success](/id/73fe105cd172f6b35f80d416/) |

#### レコード編集画面 {#event-record-event}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| レコード編集画面を表示した後 | [app.record.edit.show](/id/bc5184e1f493d2c532c2cee2/) | [mobile.app.record.edit.show](/id/bc5184e1f493d2c532c2cee2/) |
| フィールドの値を変更したとき | [app.record.edit.change.`フィールドコード`](/id/60e99be9aeb482927cc26c54/) | [mobile.app.record.edit.change.`フィールドコード`](/id/60e99be9aeb482927cc26c54/) |
| 保存するとき | [app.record.edit.submit](/id/f0b69a0bf181f5c7071d082c/) | [mobile.app.record.edit.submit](/id/f0b69a0bf181f5c7071d082c/) |
| 保存に成功した後 | [app.record.edit.submit.success](/id/2cf94dc37d3bbaded43e6569/) | [mobile.app.record.edit.submit.success](/id/2cf94dc37d3bbaded43e6569/) |

#### レコード印刷画面 {#event-record-print}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| レコード印刷画面を表示した後 | [app.record.print.show](/id/3bc9fd50e0df52db2617ae3c/) | なし |

#### グラフ画面 {#event-record-graph}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| グラフ画面を表示した後 | [app.report.show](/id/e5329a3897c9395484e66d97/) | [mobile.app.report.show](/id/e5329a3897c9395484e66d97/) |

#### ポータル画面 {#event-portal}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| ポータル画面を表示した後 | [portal.show](/id/8dac51519b826f2b22c709af/) | [mobile.portal.show](/id/8dac51519b826f2b22c709af/) |

#### スペース画面 {#event-space}

| イベントが発生するタイミング | PC | モバイル |
| :--- | :-- | :-- |
| スペースのポータル画面を表示した後 | [space.portal.show](/id/98715f80d1158b8e45fb717a/) | [mobile.space.portal.show](/id/98715f80d1158b8e45fb717a/) |

### イベントハンドラーの登録・削除 {#on-off-event-handler}

| API | PC | モバイル |
| :--- | :-- | :-- |
| イベントハンドラーを登録する | [kintone.events.on()](/id/37f50c8d618067d42eee8050/#register-event-handlers) | [kintone.events.on()](/id/37f50c8d618067d42eee8050/#register-event-handlers) |
| イベントハンドラーを削除する | [kintone.events.off()](/id/37f50c8d618067d42eee8050/#remove-event-handlers) | [kintone.events.off()](/id/37f50c8d618067d42eee8050/#remove-event-handlers) |

### API実行 {#api}

#### kintone REST APIの実行 {#api-rest-api}

| API | PC | モバイル |
| :--- | :-- | :-- |
| kintone REST APIリクエストを送信する | [kintone.api()](/id/84b51223dd9e63a226e3e985/) | [kintone.api()](/id/84b51223dd9e63a226e3e985/) |
| APIのURLを取得する | [kintone.api.url()](/id/cfcc7df6983c232a20afb4ca/) | [kintone.api.url()](/id/cfcc7df6983c232a20afb4ca/) |
| クエリ文字列付きのAPIのURLを取得する | [kintone.api.urlForGet()](/id/dc042283e99b36fa589884c5/) | [kintone.api.urlForGet()](/id/dc042283e99b36fa589884c5/) |
| CSRFトークンを取得する | [kintone.getRequestToken()](/id/9792fbbe12d96c4377e620a0/) | [kintone.getRequestToken()](/id/9792fbbe12d96c4377e620a0/) |
| kintone REST API同時接続数を取得する | [kintone.api.getConcurrencyLimit()](/id/be6644464bc87582589f8e74/) | [kintone.api.getConcurrencyLimit()](/id/be6644464bc87582589f8e74/) |

#### 外部APIの実行 {#api-proxy}

| API | PC | モバイル |
| :--- | :-- | :-- |
| 外部のAPIを実行する | [kintone.proxy()](/id/c9377c4b54b8cf6acca21283/) | [kintone.proxy()](/id/c9377c4b54b8cf6acca21283/) |
| 外部にファイルをアップロードする | [kintone.proxy.upload()](/id/007d544232d090a546119edb/) | [kintone.proxy.upload()](/id/007d544232d090a546119edb/) |

### 情報の取得／設定 {#get-set}

#### レコード {#get-set-record-detail}

| API | PC | モバイル |
| :--- | :-- | :-- |
| レコードIDを取得する | [kintone.app.record.getId()](/id/b55c4c83e168c616d740debe/) | [kintone.mobile.app.record.getId()](/id/b55c4c83e168c616d740debe/) |
| レコードの値を取得する | [kintone.app.record.get()](/id/71ec8ee172be644b63b967eb/) | [kintone.mobile.app.record.get()](/id/71ec8ee172be644b63b967eb/) |
| レコードに値をセットする | [kintone.app.record.set()](/id/bd485c4c00776c6a54fbf89c/) | [kintone.mobile.app.record.set()](/id/bd485c4c00776c6a54fbf89c/) |
| <!-- JSAPISPEC-61 --> ログインユーザーのレコードに対するアクセス権を取得する | [kintone.app.record.getPermissions()](/id/b5a7e48f34a3c1fe515fbdab) | [kintone.app.record.getPermissions()](/id/b5a7e48f34a3c1fe515fbdab) |
| <!-- JSAPISPEC-91 --> ログインユーザーのレコードのフィールドに対するアクセス権を取得する | [kintone.app.record.getFieldPermissions()](/id/b618d8b673053743eb0ab369) |  [kintone.app.record.getFieldPermissions()](/id/b618d8b673053743eb0ab369) |
| <!-- JSAPISPEC-97 --> レコードのステータスの履歴を取得する | [kintone.app.record.getStatusHistory()](/id/c123bafd783398c6fdb95716) | [kintone.app.record.getStatusHistory()](/id/c123bafd783398c6fdb95716) |
| <!-- JSAPISPEC-156 --> 実行可能なアプリのアクションの一覧を取得する | [kintone.app.record.getActions()](/id/38b6bf320ef72a5e80e09890/) | [kintone.app.record.getActions()](/id/38b6bf320ef72a5e80e09890/) |

#### アプリ {#get-set-app}

| API | PC | モバイル |
| :--- | :-- | :-- |
| <!-- JSAPISPEC-70 --> アプリ情報を取得する | [kintone.app.get()](/id/2308e9869399a394a6c7fa48) | [kintone.app.get()](/id/2308e9869399a394a6c7fa48) |
| アプリのIDを取得する | [kintone.app.getId()](/id/58ed3981d6610c27ed8f3ecb/) | [kintone.mobile.app.getId()](/id/58ed3981d6610c27ed8f3ecb/) |
| <!-- JSAPISPEC-88 --> アプリのフィールド情報を一括取得する | [kintone.app.getFormFields()](/id/2351ceb2ff6866d764caf1a0) | [kintone.app.getFormFields()](/id/2351ceb2ff6866d764caf1a0) |
| <!-- JSAPISPEC-89 --> アプリのフォームのレイアウトを取得する | [kintone.app.getFormLayout()](/id/acb476ed47260d227ff461dd) | [kintone.app.getFormLayout()](/id/acb476ed47260d227ff461dd) |
| <!-- JSAPISPEC-77 --> アプリの動作テスト環境かどうか取得する | [kintone.app.isTestEnvironment()](/id/6e7f621c98e5d9d8475ef02c) | [kintone.app.isTestEnvironment()](/id/6e7f621c98e5d9d8475ef02c) |
| <!-- JSAPISPEC-75 --> アプリがメンテナンスモードかどうかを取得する | [kintone.app.isMaintenanceMode()](/id/9ae81af080ccdc515dac32db) | [kintone.app.isMaintenanceMode()](/id/9ae81af080ccdc515dac32db) |
| <!-- JSAPISPEC-104 --> アプリの説明の開閉を切り替える | [kintone.app.showDescription(state)](/id/06a562e02a4cb729fd0ca17e) | なし |
| アプリのアイコンのURLを取得する | [kintone.app.getIcons()](/id/271da2fa8dbd896fd80ce0a7/) | [kintone.app.getIcons()](/id/271da2fa8dbd896fd80ce0a7/) |
| <!-- JSAPISPEC-12 --> レコード一覧のフィールド要素を取得する | [kintone.app.getFieldElements(fieldCode)](/id/54cea1424b291b8405c0310f) | [kintone.mobile.app.getFieldElements(fieldCode)](/id/54cea1424b291b8405c0310f) |
| <!-- JSAPISPEC-17 --> レコード一覧のメニューの右側の要素を取得する | [kintone.app.getHeaderMenuSpaceElement()](/id/6e79138a046b80c1fbe53052) | なし |
| <!-- JSAPISPEC-13 --> レコード一覧のメニューの下側の要素を取得する | [kintone.app.getHeaderSpaceElement()](/id/89fae5e18c61fef4d8f0f342) | なし |
| <!-- JSAPISPEC-120 --> レコード一覧の設定を取得する | [kintone.app.getView()](/id/a27aaf94e2fa640b180e2de4) | [kintone.app.getView()](/id/a27aaf94e2fa640b180e2de4) |
| <!-- JSAPISPEC-121 --> レコード一覧の一覧を取得する | [kintone.app.getViews()](/id/8f3b290d228a61380f6ae863) | [kintone.app.getViews()](/id/8f3b290d228a61380f6ae863) |
| レコード一覧のクエリ文字列を取得する | [kintone.app.getQueryCondition()](/id/6dd85913d217259e3d783714/) | [kintone.mobile.app.getQueryCondition()](/id/6dd85913d217259e3d783714/) |
| レコード一覧のクエリ文字列を取得する（オプション付き） | [kintone.app.getQuery()](/id/7e9ee591064613a82666a6d9/) | [kintone.mobile.app.getQuery()](/id/7e9ee591064613a82666a6d9/) |
| グラフの一覧を取得する | [kintone.app.getReports()](/id/26f635cc2a7361e01b69383d) | [kintone.app.getReports()](/id/26f635cc2a7361e01b69383d) |
| <!-- JSAPISPEC-24 --> ヘッダーの下側の要素を取得する | なし | [kintone.mobile.app.getHeaderSpaceElement()](/id/ed978122b50328d0141f8463) |
| ルックアップフィールドの参照先のアプリIDを取得する | [kintone.app.getLookupTargetAppId()](/id/d4a50f3d1be7e99c0b1868e5/) |[kintone.mobile.app.getLookupTargetAppId()](/id/d4a50f3d1be7e99c0b1868e5/) |
| 関連レコード一覧の参照先のアプリIDを取得する | [kintone.app.getRelatedRecordsTargetAppId()](/id/b0fdfc0522cdd6a0e49c0381/) | [kintone.mobile.app.getRelatedRecordsTargetAppId()](/id/b0fdfc0522cdd6a0e49c0381/) |
| <!-- JSAPISPEC-127 --> プロセス管理の設定を取得する | [kintone.app.getStatus()](/id/f444ee3bc0dd7a0c65598300/) | [kintone.app.getStatus()](/id/f444ee3bc0dd7a0c65598300/) |
| <!-- JSAPISPEC-100 --> 実行可能なプロセス管理のアクションの一覧を取得する | [kintone.app.record.getStatusActions()](/id/aa93a0ba6551dadfd743fd8b/) | [kintone.app.record.getStatusActions()](/id/aa93a0ba6551dadfd743fd8b/) |
| <!-- JSAPISPEC-128 --> プロセス管理の現在の作業者を取得する | [kintone.app.record.getAssignees()](/id/bf6eebcc8531964476a4ccd9/) | [kintone.app.record.getAssignees()](/id/bf6eebcc8531964476a4ccd9/) |
| <!-- JSAPISPEC-90 --> カテゴリーの設定情報を取得する | [kintone.app.getCategories()](/id/7033b9ca85d30d741646514c) | [kintone.app.getCategories()](/id/7033b9ca85d30d741646514c) |
| <!-- JSAPISPEC-65 --> ログインユーザーのアプリに対するアクセス権を取得する | [kintone.app.getPermissions()](/id/35745482e71cfa0ea53197b1) | [kintone.app.getPermissions()](/id/35745482e71cfa0ea53197b1) |

#### スペース {#get-set-space}

| API | PC | モバイル |
| :--- | :-- | :-- |
| <!-- JSAPISPEC-68 --> スペース情報を取得する | [kintone.space.get()](/id/b2b0c7a91ace5c80f9c217a2) | [kintone.space.get()](/id/b2b0c7a91ace5c80f9c217a2) |
| <!-- JSAPISPEC-80 --> ログインユーザーのスペースに対するアクセス権を取得する | [kintone.space.getPermissions()](/id/b97a36803f75e027553a2e4e) | [kintone.space.getPermissions()](/id/b97a36803f75e027553a2e4e) |

#### システム {#get-set-system}

| API | PC | モバイル |
| :--- | :-- | :-- |
| <!-- JSAPISPEC-95 --> 機能の有効化状況を取得する | [kintone.system.getAvailableFeatures()](/id/5336b7ab7a940ce33ec1d80e) | [kintone.system.getAvailableFeatures()](/id/5336b7ab7a940ce33ec1d80e) |
| <!-- JSAPISPEC-79 --> ログインユーザーのシステムに対する権限を取得する | [kintone.system.getPermissions()](/id/26d02fe833467a0b37277c6c) | [kintone.system.getPermissions()](/id/26d02fe833467a0b37277c6c) |

#### ライセンス {#get-set-license}

| API | PC | モバイル |
| :--- | :-- | :-- |
| <!-- JSAPISPEC-84 --> 試用中かどうかを取得する | [kintone.license.isTrial()](/id/2ed5b79c7f11fdc9e853a61f) | [kintone.license.isTrial()](/id/2ed5b79c7f11fdc9e853a61f) |
| <!-- JSAPISPEC-96 --> kintoneの契約中のコースを取得する | [kintone.license.getSubscriptionPlan()](/id/0b249e9c2444cc2f62075afb) | [kintone.license.getSubscriptionPlan()](/id/0b249e9c2444cc2f62075afb) |

#### 全体 {#get-set-all}

| API | PC | モバイル |
| :--- | :-- | :-- |
| ログインユーザーの情報を取得する | [kintone.getLoginUser()](/id/77c07915d060850bf7497995/) | [kintone.getLoginUser()](/id/77c07915d060850bf7497995/) |
| ログインユーザーのカスタマイズ項目を取得する | [kintone.user.getCustomFields()](/id/f8d0671d656d2c0ae4dd05d0/) | [kintone.user.getCustomFields()](/id/f8d0671d656d2c0ae4dd05d0/) |
| ログインユーザーが所属するグループ（ロール）を取得する | [kintone.user.getGroups()](/id/5fee930cc4e93f49c7b26e61/) | [kintone.user.getGroups()](/id/5fee930cc4e93f49c7b26e61/)|
| ログインユーザーが所属する組織を取得する | [kintone.user.getOrganizations()](/id/353c88fc9220005bb0ac6925/) | [kintone.user.getOrganizations()](/id/353c88fc9220005bb0ac6925/)  |
| 表示中の画面を取得する | [kintone.getPageType()](/id/24550b0c653df3686831660e/) | [kintone.getPageType()](/id/24550b0c653df3686831660e/) |
| ユーザーのアイコンを取得する | [kintone.user.getIcons()](/id/239e17984146b8f72af2f8be/) | [kintone.user.getIcons()](/id/239e17984146b8f72af2f8be/) |
| デザインのバージョンを取得する | [kintone.getUiVersion()](/id/bb6785bc5550b8adea13db9c/) | [kintone.getUiVersion()](/id/bb6785bc5550b8adea13db9c/) |
| <!-- JSAPISPEC-73 --> cybozu.comの他のサービスを利用可能かを取得する      | [kintone.getAvailableServices()](/id/1f712ed39f52b4d9faacf7c6) | [kintone.getAvailableServices()](/id/1f712ed39f52b4d9faacf7c6) |
| <!-- JSAPISPEC-74 --> ドメイン情報を取得する | [kintone.getDomain()](/id/eac269672d461b7707c1dec0) | [kintone.getDomain()](/id/eac269672d461b7707c1dec0) |
| <!-- JSAPISPEC-87 --> 利用可能なAPIの種類を取得する | [kintone.getAvailableApiTypes()](/id/c84294d596a06e40d449a3a5) | [kintone.getAvailableApiTypes()](/id/c84294d596a06e40d449a3a5) |
| <!-- JSAPISPEC-85 --> セキュアアクセスかどうかを取得する | [kintone.isAccessWithClientCertificateAuthentication()](/id/4d64f77e75362e8224880741) | [kintone.isAccessWithClientCertificateAuthentication()](/id/4d64f77e75362e8224880741) |
| <!-- JSAPISPEC-86 --> モバイルアプリからのアクセスかどうかを取得する | [kintone.isMobileApp()](/id/6f1060634b37f1bee566f234) | [kintone.isMobileApp()](/id/6f1060634b37f1bee566f234) |
| <!-- JSAPISPEC-81 --> モバイル版の画面かどうかを取得する | [kintone.isMobilePage()](/id/9efffa632fdad3142a7b8b48) | [kintone.isMobilePage()](/id/9efffa632fdad3142a7b8b48) |
| <!-- JSAPISPEC-83 --> ログインユーザーの個人設定を取得する | [kintone.getUserPreference()](/id/4dff42d1c530d2eafa7f4b1e) | [kintone.getUserPreference()](/id/4dff42d1c530d2eafa7f4b1e) |
| <!-- JSAPISPEC-78 --> ログインユーザーがcybozu.com共通管理者かどうかを取得する | [kintone.isUsersAndSystemAdministrator()](/id/94691556bd94c3a2cdaab863) | [kintone.isUsersAndSystemAdministrator()](/id/94691556bd94c3a2cdaab863) |
| <!-- JSAPISPEC-76 --> フロントエンド基盤の刷新後の画面かどうかを取得する | [kintone.isRevampedUI()](/id/bbfaa03dedc276890f5db503) | [kintone.isRevampedUI()](/id/bbfaa03dedc276890f5db503) |
| <!-- JSAPISPEC-130 / JSAPISPEC-184 --> 確認ダイアログ/確認ボトムシートを表示する | [kintone.showConfirmDialog()](/id/8b01f191ba328ffd13a7cdf3) | [kintone.mobile.showConfirmBottomSheet()](/id/4fd437171bce7d4c0f9ed8d1) |
| <!-- JSAPISPEC-126 / JSAPISPEC-183 --> ダイアログ／ボトムシートを作成する | [kintone.createDialog()](/id/6ace24e2779da218b2193bc3) | [kintone.mobile.createBottomSheet()](/id/01be21701e2179b1fa094da1/) |
| <!-- JSAPISPEC-123 --> 画面上部にメッセージを表示する | [kintone.showNotification()](/id/82b92606653bc58e0260cde2) | [kintone.mobile.showNotification()](/id/82b92606653bc58e0260cde2) |
| <!-- JSAPISPEC-124 --> ローディングを表示する | [kintone.showLoading()](/id/9545a24cd5f7e4bd428f1a70) | [kintone.mobile.showLoading()](/id/9545a24cd5f7e4bd428f1a70) |
| <!-- JSAPISPEC-119 --> kintone内の画面のURLを組み立てる | [kintone.buildPageUrl()](/id/9f2164aa03296c1ad3e42408) | [kintone.buildPageUrl()](/id/9f2164aa03296c1ad3e42408) |
| <!-- JSAPISPEC-122 --> ショートカットキーの有効／無効を切り替える | [kintone.setKeyboardShortcuts()](/id/8cb62c20ccce8501dd4e4499) | なし |
| <!-- JSAPISPEC-166 --> ショートカットキーの有効／無効の状態を取得する | [kintone.getKeyboardShortcuts()](/id/63da494f91aec0007a9df204) | なし |

### フィールド表示／非表示 {#field-shown}

| API | PC | モバイル |
| :--- | :-- | :-- |
| フィールドの表示／非表示を切り替える | [kintone.app.record.setFieldShown()](/id/4fd422ae65295b6280f190e6/) | [kintone.mobile.app.record.setFieldShown()](/id/4fd422ae65295b6280f190e6/) |
| グループフィールドを開閉する | [kintone.app.record.setGroupFieldOpen()](/id/c4c047e64bee53e15ab63feb/) | [kintone.mobile.app.record.setGroupFieldOpen()](/id/c4c047e64bee53e15ab63feb/) |
| <!-- JSAPISPEC-132,134 --> フィールドの表示／非表示の状態を取得する | [kintone.app.record.isFieldVisible()](/id/5d738a9338e3ce0faece404a/) | [kintone.mobile.app.record.isFieldVisible()](/id/5d738a9338e3ce0faece404a/) |
| <!-- JSAPISPEC-135,136 --> グループフィールドの開閉状態を取得する | [kintone.app.record.isGroupFieldOpen()](/id/53a7a8bf938126aa0873fa28/) | [kintone.mobile.app.record.isGroupFieldOpen()](/id/53a7a8bf938126aa0873fa28/) |

### フィールドのスタイル設定 {#set-field-style}

| API | PC | モバイル |
| :--- | :-- | :-- |
| フィールドのスタイルの設定 | [kintone.app.record.setFieldStyle()](/id/099ac586036fd1d7e4375fff/) | [kintone.mobile.app.record.setFieldStyle()](/id/099ac586036fd1d7e4375fff/) |
| フィールドのスタイルの取得 | [kintone.app.record.getFieldStyle()](/id/21c511090da2f0f83e36ca57/) | [kintone.mobile.app.record.getFieldStyle()](/id/21c511090da2f0f83e36ca57/) |

### 要素の表示／非表示 {#element-shown}

| API | PC | モバイル |
| :--- | :-- | :-- |
|  アプリの説明の開閉を切り替える | [kintone.app.showDescription()](/id/06a562e02a4cb729fd0ca17e/) | なし |
| レコードの追加ボタンの表示／非表示を切り替える | [kintone.app.showAddRecordButton()](/id/24d3b386945269f0af1b986c/) | [kintone.mobile.app.showAddRecordButton()](/id/24d3b386945269f0af1b986c/) |
| アプリの設定ボタンの表示／非表示を切り替える | [kintone.app.showAppSettingsButton()](/id/fec916e4fead8244d36c48b7/) | なし |
| レコードの再利用ボタンの表示／非表示を切り替える | [kintone.app.record.showDuplicateRecordButton()](/id/4a426a490652260ebe21ae75/) | なし |
| レコードの編集ボタンの表示／非表示を切り替える | [kintone.app.record.showEditRecordButton()](/id/9b0d51f78663c9f8029d1276/) | [kintone.mobile.app.record.showEditRecordButton()](/id/9b0d51f78663c9f8029d1276/) |
| 絞り込みボタンの表示／非表示を切り替える | [kintone.app.showFilterButton()](/ja/id/ee3d1e6b8c15ceaa7f597446/) | [kintone.mobile.app.showFilterButton()](/ja/id/ee3d1e6b8c15ceaa7f597446/) |
| グラフを選択するパーツの表示／非表示を切り替える | [kintone.app.showViewAndReportSelector()](/ja/id/3ebd5ca326d1183b76d40360/) | [kintone.mobile.app.showReportSelector()](/id/36161dc17ec3d9bb97fcad26/) |
| グラフを選択するパーツの選択肢の表示／非表示を切り替える | [kintone.app.showReportSelectorItems()](/ja/id/f1e8b55587b3bc460e3de56b/) | [kintone.mobile.app.showReportSelectorItems()](/id/f1e8b55587b3bc460e3de56b/) |
|  一覧を選択するパーツの表示／非表示を切り替える | [kintone.app.showViewAndReportSelector()](/ja/id/3ebd5ca326d1183b76d40360/) | [kintone.mobile.app.showViewSelector()](/id/512b36733c9a4c67009d3715/) |
| 一覧を選択するパーツの選択肢の表示／非表示を切り替える | [kintone.app.showViewSelectorItems()](/id/f16ad5b7cf03bc704016e018/) | [kintone.mobile.app.showViewSelectorItems()](/id/f16ad5b7cf03bc704016e018/) |
| アプリのオプションボタンの表示／非表示を切り替える | [kintone.app.showOptionsButton()](/id/715ef3dfa91472b63889e82e/) | [kintone.mobile.app.showOptionsButton()](/id/715ef3dfa91472b63889e82e/) |
|  前／次のレコードに移動するボタンの表示／非表示を切り替える | [kintone.app.record.showPager()](/id/6d54917591c7106de11f03e2/) | [kintone.mobile.app.record.showPager()](/id/6d54917591c7106de11f03e2/) |
| 集計ボタンの表示／非表示を切り替える | [kintone.app.showReportButton()](/id/e99be6af45e79cbea314f34f/) | なし |
| サイドバーの開閉を切り替える | [kintone.app.record.showSideBar()](/id/add5dcd73e708afd4d9a93c5/) | なし |
| アプリのアクションボタンの表示／非表示を切り替える | [kintone.app.record.showActionButton()](/id/ab4b2304e1a8a02ad6690b98/) | [kintone.mobile.app.record.showActionButton()](/id/ab4b2304e1a8a02ad6690b98/) |
| プロセス管理のアクションボタンの表示／非表示を切り替える | [kintone.app.record.showStatusActionButton()](/id/82851eb347b84ac2bfdf032a/) | [kintone.mobile.app.record.showStatusActionButton()](/id/82851eb347b84ac2bfdf032a/) |
| 「現在の作業者を変更」ボタンの表示／非表示を切り替える | [kintone.app.record.showChangeAssigneeButton()](/id/aa639a1ab21fa6850ceae656/) | なし |

### 要素の表示状態取得 {#get-element-display-state}

| API | PC | モバイル |
| :--- | :-- | :-- |
| アプリの説明の表示状態を取得する | [kintone.app.getDescriptionDisplayState()](/id/3e12c983a0308a1a23280fd1/) | なし |
| サイドバーの表示状態を取得する | [kintone.app.record.getSideBarDisplayState()](/id/1e940d0c0e301533e047d316/) | なし |
| レコード追加ボタンの表示状態を取得する | [kintone.app.getAddRecordButtonDisplayState()](/id/13114d2b2af5bb3ebed62589/) | [kintone.mobile.app.getAddRecordButtonDisplayState()](/id/13114d2b2af5bb3ebed62589/) |
| レコード編集ボタンの表示状態を取得する | [kintone.app.record.getEditRecordButtonDisplayState()](/id/ceef2a6005e35d3b69a48f7e/) | [kintone.mobile.app.record.getEditRecordButtonDisplayState()](/id/ceef2a6005e35d3b69a48f7e/) |
| レコード再利用ボタンの表示状態を取得する | [kintone.app.record.getDuplicateRecordButtonDisplayState()](/id/2ff4344b271bdc2ecf45b3e3/) | なし |
| アプリ設定ボタンの表示状態を取得する | [kintone.app.getAppSettingsButtonDisplayState()](/id/b5202e412676ef9e4a329717/) | なし |
| アプリのオプションボタンの表示状態を取得する | [kintone.app.getOptionsButtonDisplayState()](/id/288993f5f959376e7c8fecc7/) | [kintone.mobile.app.getOptionsButtonDisplayState()](/id/288993f5f959376e7c8fecc7/) |
| 前／次のレコードに移動するボタンの表示状態を取得する | [kintone.app.record.getPagerDisplayState()](/id/317ad7ba2ac30fcc138f9e27/) | [kintone.mobile.app.record.getPagerDisplayState()](/id/317ad7ba2ac30fcc138f9e27/) |
| 絞り込みボタンの表示状態を取得する | [kintone.app.getFilterButtonDisplayState()](/id/391b29b6afca0716f54f705a/) | [kintone.mobile.app.getFilterButtonDisplayState()](/id/391b29b6afca0716f54f705a/) |
| 集計ボタンの表示状態を取得する | [kintone.app.getReportButtonDisplayState()](/id/35cbd789f1ed4fce17396b4d/) | なし |
| グラフを選択するパーツの表示状態を取得する | [kintone.app.getViewAndReportSelectorDisplayState()](/id/9a6a7bddfeaa8a44deb11334/) | [kintone.mobile.app.getReportSelectorDisplayState()](/id/234c347d8193fef821a0ae04/) |
| グラフを選択するパーツの選択肢の表示状態を取得する | [kintone.app.getReportSelectorItemsDisplayState()](/ja/id/32835bbdd8effc6df45f3157/) | [kintone.mobile.app.getReportSelectorItemsDisplayState()](/id/32835bbdd8effc6df45f3157/) |
| 一覧を選択するパーツの表示状態を取得する | [kintone.app.getViewAndReportSelectorDisplayState()](/id/9a6a7bddfeaa8a44deb11334/) | [kintone.mobile.app.getViewSelectorDisplayState()](/id/00775548ce79c821f0642726/) |
| 一覧を選択するパーツの選択肢の表示状態を取得する | [kintone.app.getViewSelectorItemsDisplayState()](/id/45ba8467285977766ac3d3fb/) | [kintone.mobile.app.getViewSelectorItemsDisplayState()](/id/45ba8467285977766ac3d3fb/) |
| アプリのアクションボタンの表示状態を取得する | [kintone.app.record.getActionButtonDisplayState()](/id/66c9199a1caac37b0a5199c0/) | [kintone.mobile.app.record.getActionButtonDisplayState()](/id/66c9199a1caac37b0a5199c0/) |
| プロセス管理のアクションボタンの表示状態を取得する | [kintone.app.record.getStatusActionButtonDisplayState()](/id/30ed19e5e011c9b891588f2e/) | [kintone.mobile.app.record.getStatusActionButtonDisplayState()](/id/30ed19e5e011c9b891588f2e/) |
| 「現在の作業者を変更」ボタンの表示状態を取得する | [kintone.app.record.getChangeAssigneeButtonDisplayState()](/id/808ee7a1ab856354feb80afe/) | なし |

### 要素の取得 {#get-element}

#### レコード詳細画面 {#get-element-record-detail}

| API | PC | モバイル |
| :--- | :-- | :-- |
| フィールド要素を取得する | [kintone.app.record.getFieldElement()](/id/8a380badcc82a4b82b89fdd1/) | [kintone.mobile.app.record.getFieldElement()](/id/8a380badcc82a4b82b89fdd1/) |
| メニューの上側の要素を取得する | [kintone.app.record.getHeaderMenuSpaceElement()](/id/d67859bda24c80d877965ce3/) | なし |
| ヘッダーの下側の要素を取得する | なし | [kintone.mobile.app.getHeaderSpaceElement()](/id/ed978122b50328d0141f8463/) |
| スペースフィールドの要素を取得する | [kintone.app.record.getSpaceElement()](/id/dc0e131a81a14037490c0365/) | [kintone.mobile.app.record.getSpaceElement()](/id/dc0e131a81a14037490c0365/)  |

#### レコード一覧画面 {#get-element-record-list}

| API |  PC | モバイル |
| :--- | :-- | :-- |
| フィールド要素を取得する | [kintone.app.getFieldElements()](/id/54cea1424b291b8405c0310f/) | [kintone.mobile.app.getFieldElements()](/id/54cea1424b291b8405c0310f/) |
| メニューの右側の要素を取得する | [kintone.app.getHeaderMenuSpaceElement()](/id/6e79138a046b80c1fbe53052/) | なし |
| メニューの下側の要素を取得する | [kintone.app.getHeaderSpaceElement()](/id/89fae5e18c61fef4d8f0f342/) | なし |
| ヘッダーの下側の要素を取得する | なし | [kintone.mobile.app.getHeaderSpaceElement()](/id/ed978122b50328d0141f8463/) |

#### ポータル画面 {#get-element-portal}

| API | PC | モバイル |
| :--- | :-- | :-- |
| ポータルの上側の要素を取得する | [kintone.portal.getContentSpaceElement()](/id/384a63484a0aecbb3bf3d673/) | [kintone.mobile.portal.getContentSpaceElement()](/id/384a63484a0aecbb3bf3d673/) |

#### スペース画面 {#get-element-space}

| API | PC | モバイル |
| :--- | :-- | :-- |
| スペースのポータル画面の上側の要素を取得する | [kintone.space.portal.getContentSpaceElement()](/id/c2a61055f399075aa57d8890/) | [kintone.mobile.space.portal.getContentSpaceElement()](/id/c2a61055f399075aa57d8890/) |

### プラグイン {#get-element-plugin}

| API | PC | モバイル |
| :--- | :-- | :-- |
| 設定情報を取得する | [kintone.plugin.app.getConfig()](/id/159e4bac618eaed0d0653073/) | [kintone.plugin.app.getConfig()](/id/159e4bac618eaed0d0653073/) |
| 設定情報を保存する | [kintone.plugin.app.setConfig()](/id/db07deb5730bc862595b708b/) | なし |
| 外部APIの実行に必要な情報を取得する | [kintone.plugin.app.getProxyConfig()](/id/0e4161ce3cd7962a51863c65/) | なし |
| 外部APIの実行に必要な情報を保存する | [kintone.plugin.app.setProxyConfig()](/id/28058eda48d7908ac4edb765/) | なし |
| 外部APIを実行する | [kintone.plugin.app.proxy()](/id/bcbba33a205d0eaad724c342/) | [kintone.plugin.app.proxy()](/id/bcbba33a205d0eaad724c342/) |
| 外部にファイルをアップロードする | [kintone.plugin.app.proxy.upload()](/id/1fa304ef2a8b06d88cd479f3/) | [kintone.plugin.app.proxy.upload()](/id/1fa304ef2a8b06d88cd479f3/) |
