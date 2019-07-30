---
title: リリースノート
seo-title: リリースノート
description: リリースノート
seo-description: このページには、Adobe Campaign Standardの最新リリースがすべて記載されています。
page-status-flag: 常にアクティブ化されていない
uuid: 1cf2e40c- beca-43db-8261- a1820ee86ad3
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: 参照
topic-tags: campaign- standard- release
discoiquuid: 5c7bfb74-4002-4ffe-87e8- bdb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 70f20623cfb4b902adf49cc2934cfdec0894f86c

---


# Release Notes{#release-notes}

Adobe Campaign Standardの特定のリリースを探しています。

各リリースには、新機能およびパッチが含まれています。そのコンテンツを表示するには、リリースをクリックします。[リリース予定](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) については、リリースの次回のリリースをご覧ください。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a previous release, consult these pages: [2018 Release Notes](../../rn/using/release-notes-2018.md), [2017 Release Notes](../../rn/using/release-notes-2017.md), [2015-2016 Release Notes](../../rn/using/release-notes-2015-2016.md). Also consult the list of [Deprecated and Removed Features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Release 19.3 - July 2019 {#release-19-3---july-2019}

### What's new? {#what-s-new-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> External API Activity (Public Beta)<br /> </td> 
   <td> <p>より深いパーソナライゼーションを実現するために、外部APIアクティビティを使用すると、外部システムからのデータをREST API呼び出し経由でワークフローに取り込むことができます。RESTエンドポイントは、顧客管理システム、Adobe I/OランタイムまたはAdobe Experience Cloud RESTエンドポイント（例: Data Platform、Target、Analytics、Campaign）です。</p><p>この機能は現在パブリックベータ版です。</p><p>For more information, refer to the <a href="../../automating/using/external-api.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Report on workflow segment<br /> </td> 
   <td> <p>この機能により、マーケティング担当者は、セグメントコードごとに配信パフォーマンスを分類できます。ワークフローを作成し、セグメント化アクティビティを使用して配信母集団にセグメントを割り当てると、これらのセグメントが同じ配信に移行できるようになります。これにより、単一の配信内で複数のセグメントに基づいてオープン/クリックの統計を表示できます。</p><p>For more information, refer to the <a href="../../reporting/using/creating-a-report-workflow-segment.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">how-to video</a>.</p></td>
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-2}

* 不正なリクエストに対するサービス妨害（DoS）攻撃を防ぐために、セキュリティ上の問題を修正しました。（CAR-33454）

### Email Designer enhancements {#email-designer-enhancements-3}

* コンポーネントが追加されるたびにHTMLテンプレートに追加のHTMLスタイルタグが追加され、テンプレートのサイズが劇的に増加する可能性がある問題を修正しました。（CAR-34694）
* 右端のツールバーメニューオプションが使用できない可能性がある問題を修正しました。（CAR-34577）
* ミラーページURLコンテンツブロックが電子メールコンテンツに挿入されていた問題を修正しました。（CAR-34779）
* 電子メールでJSPPコードを使用すると、コンテンツの編集が難しくなる問題を修正しました。（CAR-34574）
* ハイパーリンクを追加すると、上部で画像が切り詰められる問題を修正しました。（CAR-34382）
* 電子メールデザイナーをFirefoxに使用する際の表示の問題を修正しました。（CAR-34364）
* 電子メールで動的コンテンツを定義する際に、アドバンスモードで発生していたいくつかの問題を修正しました。（CAR-34351、CAR-34333、CAR-34331）
* 動的コンテンツルールエディター（CAR-34304、CAN-34303）で発生していたいくつかの問題を修正。
* 電子メールデザイナーの設定ウィンドウ（CAR-33749）にリンクフィールドが表示されない問題を修正しました。
* YouTubeのアイコンが送信済み電子メールでサイズ変更されていた問題を修正しました。（CAR-33726）
* ミラーページコンテンツを編集可能にするセキュリティ上の問題を修正しました。（CAR-33691）
* 動的コンテンツの記号を使用するとHTML出力が破損する問題を修正しました。（CAR-33688）
* 電子メールデザイナーでテキストを編集する際に「元に戻す」オプションを使用すると発生していた問題を修正しました。（CAR-32565）
* スタイルを削除せずにスタイルを解除すると、追加のタグが作成される問題を修正しました。（CAR-32359）
* 電子メールで使用される各コンポーネントがデスクトップデバイスでのみ表示されるか、モバイルデバイスのみで表示されるかを定義できるようになりました。
* Socialコンテンツコンポーネントの幅と高さを設定できるようになりました。
* 動的コンテンツを削除した後、動的コンテンツの古いソースコードが削除されない問題を修正しました。
* 電子メールの変更後に電子メールの件名が更新されない可能性がある問題を修正しました。
* nの問題を修正しました。n列構造がワークスペースにドロップされると、選択されないようになります。
* 電子メールダッシュボードでメッセージのサムネールがぼやけて表示される問題を修正しました。
* Outlookで受信した電子メールでバックグラウンドが正しく表示されない問題を修正しました。
* 電子メールDesignerホームページでの一部の並べ替えの問題を修正しました。
* 動的コンテンツを使用する場合に、バリアントを複製すると発生していた問題を修正しました。
* 不要なフィールドが電子メールデザイナーの設定ペインから削除されました。

### Other improvements {#other-improvements-3}

* Adobe Experience Platformロケーションサービスとの統合により、Adobe Campaignは、エクスペリエンスプラットフォームSDKを使用して、場所ベースのマーケティングメッセージをモバイルアプリのサブスクライバーに送信できるようになりました。For more information, refer to the [detailed documentation](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* レポート機能が改善され、エクスペリエンスが向上しました。この機能を使用するには、動的レポート使用規約に同意する必要があります。For more on this, refer to the [detailed documentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* ワークフローでは、次の10個のワークフローをプレビューするための新しいオプションが追加されました。For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* スケジューラーアクティビティでは、新しいオプションによって、毎月配信する特定の週の特定の日を選択できます。For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* 集計期間を使用せずに定期配信を作成する場合、配信の送信前に配信ダッシュボードで確認を要求できるようになりました。For more on this, refer to the [detailed documentation](../../sending/using/confirming-the-send.md).
* ワークフローの外部シグナルアクティビティで宣言されているイベント変数を使用して、配信のラベルをカスタマイズできるようになりました。For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* DGPRの削除クエリが改善され、パフォーマンスが向上しました。（CAR-33504）
* 外部アカウント設定インターフェイスから"ftp"オプションが削除されました。（CAR-34472）
* これで、電子メールメッセージごとにSMTPテストモードオプションを有効化および無効化できます。For more on this, refer to the [detailed documentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). （CAR-34602）

### Other changes {#other-changes-2}

* 配信プロパティインターフェイスに警告が追加されました。これにより、集計期間に基づいて配信が準備され、ワークフローを1日に複数回呼び出すことができます。これにより、期間がないことを確認することができます。（CAR-34393）
* カスタムリソース設定画面に警告が追加されました。カスタムリソースIDには最大30文字を使用することをお勧めします。これは、カスタムリソースフィールド、キー、インデックスおよびリンクにも適用されます。
* ランディングページで使用されるトランザクションメッセージを確認メッセージとして削除しようとするとメッセージが表示されるようになりました。
* アクティビティが6時間以上実行されていると、ワークフローログに警告が表示されるようになりました。これは、プッシュ通知、配信、シグナル、開始、終了、フォーク、AND、ジョイント、スケジュールおよび待機アクティビティには適用されません。
* 同時に実行されるワークフローの最大数に達すると、ワークフローログに警告が表示されるようになりました。
* 7日以上の状態で一時停止または失敗したワークフローは、ディスク容量を節約するために停止しました。クリーニングタスクがワークフローログに表示されます。
* 「ファイルの転送」アクティビティを使用すると、ファイルサイズが使用可能なディスク容量を超えるとエラーが記録されるようになりました。
* アプリ内メッセージのセカンダリボタンで、リンク先URLへリダイレクトアクションを選択できなくなりました。

### Patches {#patches-3}

* DGPRへのアクセス要求が失敗する可能性がある問題を修正しました。
* 一意のプロファイルに対して複数のトリガーを受信した場合に、トリガーされる可能性がある問題を修正しました。
* ログイン後にエラーメッセージが表示される可能性がある問題を修正しました。
* カスタムリソースを作成または拡張すると空白ページが表示される問題を修正しました。
* ターゲットディメンションとしてAppSubscriptionRCPを持つオーディエンスがモバイル配信でターゲティングできない問題を修正しました。
* エラーを修正し、電子メールアドレスが強制隔離されない問題を修正しました。（CAR-24587）
* タイポロジルールを追加してから、タイポロジを保存する前に発生していた問題を修正しました。（CAR-32789）
* 動的コンテンツを無効にするとランディングページのコンテンツが表示されない問題を修正しました。（CAR-32924）
* マスター配信の属性でパーソナライゼーションを使用すると発生する定期配信の問題を修正しました。（CAR-32983）
* 受信SMSメッセージデータを含むトランジションの結果を読み取ることができなかったワークフローの問題を修正しました。（CAR-33134）
* フォークと除外アクティビティを組み合わせてオーディエンスを作成すると発生していたワークフローの問題を修正しました。（CAR-33401）
* ミラーページのコンテンツが表示されず、定期配信用にメッセージが送信されない問題を修正しました。（CAR-33413）
* プロファイルとオーディエンス間の統合アクティビティを使用するとエラーが発生する問題を修正しました。この問題は、入力トランジションの識別キーの非互換性が原因で発生していました。（CAR-33713）
* テストアクティビティで、"recCount"式がダブルクリック時に正しい構文を使用できなかった問題を修正しました。（CAR-33756）
* 請求のテクニカルワークフローログを開くとエラーメッセージが表示される可能性がある問題を修正しました。（CAR-34313）
* 購読を含むチェックボックスフィールドの設定時に発生する可能性があるランディングページの問題を修正しました。（CAR-34369）
* リストを設定し、「アイコン」フィールドを追加すると発生していた問題を修正しました。（CAR-34585）
* "|」および"%"記号を、ファイルワークフローアクティビティの読み込みの日付または時間区切り文字として使用します。（CAR-34706）
* ランディングページのチェックボックスを使用して表示条件を使用すると発生していた問題を修正しました。（CAR-34802）
* フィルタリングディメンションがトラッキングログとプロファイルのターゲットディメンションに設定されている場合、「追加データ」タブにフィールドが表示されなかった、強化アクティビティの問題を修正しました。
* "WorkflowTemplate"リソースを書き出す際にエラーメッセージが表示される問題を修正しました。
* 新しいプロファイルを作成すると、ダイアログボックスから選択した場合に「国/地域コード」フィールドが保存されない問題を修正しました。
* Direct Mailインポートテンプレート（UpdateCarinessDeliveryLogsDirectMail）の使用時に発生していたいくつかの問題を修正。
* Assets on Demand統合の問題を修正しました。
* タイムラインビューでズームインすると発生していた問題を修正しました。（CAR-33628）
* スケジュールされた日時の電子メールメッセージに対して、校正刷りが即座に送信されない問題を修正しました。（CAR-33723）
* ユーザーがログアウトしたときにエラーログを生成したトランザクションメッセージに関連する問題を修正しました。（CAR-31698）
* 電子メールメッセージのスケジュール設定時に特定の環境で発生する可能性があるエラーを修正しました。
* 配信の更新の実行ワークフローが失敗する問題を修正しました。
* 件名に複数行が含まれている場合に電子メールコンテンツが破損するセキュリティの問題を修正しました。


## Release 19.2.7 - July 2019 {#release-19-2-7---july-2019}

### Improvements {#improvements-2}

* DGPRの削除クエリが改善され、パフォーマンスが向上しました。
* 19.2アップグレード後にWebがクラッシュする可能性がある問題を修正しました。（CAR-34862）
* 管理者以外のユーザーがレポートを保存またはスケジュールできない可能性がある問題を修正しました。（CAR-31133）
* "|」をクリックします。（CAR-34706）

## Release 19.2.4 - June 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* HTMLで空のスタイルタグを使用するとフラグメントを編集できない問題を修正しました。これは、19.2.3のCOP-33778のフォローアップ修正です。

## Release 19.2.3 - June 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

19.2リリースのフラグメントを最適化するための一連の改善と修正が導入されました。新しく作成したフラグメントはシームレスに機能します。以前にビルドされたフラグメントは、グレーアウトされており、新しい形式に移行する必要があります。そのためには、各フラグメントをクリックし、新しい形式への移行を検証します。すべてのフラグメントを移行する前に、いくつかのフラグメントをテストすることをお勧めします。

* ロック解除後にフラグメントを編集できない問題を修正しました。これは、19.2に更新する際に既存のフラグメントに影響していました。（CAR-33778）
* 動的コンテンツを使用する際の問題を修正しました。HTMLに余分なスペースが追加されました。

### Other improvements {#other-improvements-2}

* SMSコネクタを切断した後にSMSの送信が再開されない可能性がある問題を修正しました。
* TLSが有効になっている場合にSMPP接続が閉じる可能性がある問題を修正しました。
* TLSが有効になっている場合にSMPP接続が閉じる可能性がある問題を修正しました。
* Adobe Experience Platform Mobile SDKで作成されたモバイルアプリケーションのプロパティを管理するために、"Launch_ URL_ Campaign"オプションがキャンペーンに追加されました。
* 新しく作成されたモバイルプロパティの証明書をアップロードしてモバイルアプリケーションのプロパティページを終了した後、サンドボックス環境オプションにつながるエラーを修正しました。
* サービスリソースの情報を使用してトランザクションメッセージコンテンツを拡張できなかった問題を修正しました。（CAR-33707）
* サービスからプロファイルを登録解除しようとすると発生していたブラックリストのランディングページの問題を修正しました。

## Release 19.2 - May 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Control Panel<br /> </td> 
   <td> <p>管理者ユーザーとして作業効率を向上させるために、容量を容易に監視し、インスタンスの設定を管理できます（SFTPサーバー管理から開始）。</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Local notifications<br /> </td> 
   <td> <p>ローカル通知メッセージを使用すると、インターネットやモバイルアプリケーションにアクセスしなくても、モバイルアプリケーション内で新しいデータが利用可能になったときにユーザーに通知できます。ローカル通知は、特定の時間に、およびイベントに応じてモバイルアプリケーションによってトリガーされます。</p><p>For more information, refer to the <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">detailed documentation</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Workflow enhancement - Add a payload to external signal activity<br /> </td> 
   <td> <p>定義された条件が別のワークフローから正常に満たされた場合、または外部システムと統合するREST API呼び出しが正常に完了した場合に、ペイロードを使用してワークフローを開始します。This also includes a new <strong>test</strong> activity where you can run tests on this functionality.</p><p>For more information, refer to the <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Landing Pages enhancement - Google reCAPTCHA<br /> </td> 
   <td> <p>Google reCaptchAを利用して、顧客からの行動を起こさずにランディングページでスパムを防ぐことができます。</p><p>For more information, refer to the <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">detailed documentation</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements}

* レポートワークスペースの潜在的なクリックジャックセキュリティ問題を修正。

### Email Designer enhancements {#email-designer-enhancements}

* フラグメントを複製して電子メールデザイナーで使用しようとすると発生していた問題を修正しました。（CAR-33193）
* 電子メールデザイナーインターフェイスでインライン要素を使用すると不要なスペースが作成される問題を修正しました。（CAR-32163）
* 電子メールデザイナーに電子メールコンテンツを保存した後に、ユーザーによって追加された追加のHTMLタグ属性が削除される問題を修正しました。（CAR-32162）
* 電子メールデザイナーのHTMLモードで削除した後でもMicrosoft Officeのタグが表示される問題を修正しました。（CAR-32141）
* 以前のバージョンの電子メールDesignerを使用して電子メールを作成した場合、この電子メールコンテンツを開くと、ユーザーに最新バージョンへの更新を求めるポップアップウィンドウが表示されるようになります。（CAR-31529）
* 一部のメッセージングクライアントに配信されると電子メールDesignerで作成された電子メールから画像がゆがめる問題を修正しました。（CAR-31407）
* リストやボタンなどの一部の要素が、HTMLモードで作成されたときにプレーンテキストモードで正しく表示されない問題を修正しました。（CAR-32582、CAR-32542）
* コンテンツテンプレートまたはフラグメントプロパティに50を超える組織単位を表示できない問題を修正しました。（CAR-32932）
* Outlookで電子メールデザイナーで作成された電子メールを受信すると、ビューポートの背景色が発生する問題を修正しました。（CAR-31402）
* 電子メールDesignerで作成した電子メールコンテンツをOutlookで開いたときに応答しない可能性がある問題を修正しました。（CAR-31400）
* 電子メールの件名で動的コンテンツが正しく動作しない問題を修正しました。（CAR-32837）
* 電子メールの件名が正しくエスケープされなかった問題を修正しました。
* フラグメントを電子メールデザイナーの左パレットに読み込めない問題を修正しました。
* フラグメントリストを更新する際に、電子メールコンテンツの編集中に作成されたフラグメントが電子メールデザイナーの左パレットに表示されない問題を修正しました。
* 動的コンテンツを電子メールで使用中に発生していたいくつかの問題を修正。
* RGB値を使用してカラーを定義しようとすると、カラーピッカーが発生する問題を修正しました。
* モバイルの電子メールを受信する際にミラーページが応答できない問題を修正しました。

### Transactional Messaging enhancements {#transactional-messaging-enhancements}

操作とパフォーマンスを最適化するために、トランザクションメッセージングチャネルにいくつかの改善点が追加されました。

* トランザクションメッセージ期間が拡張され、特に再試行が実行される際に、すべてのメッセージが期限切れになるように拡張されました。
* トランザクションメッセージのパフォーマンスが、異なる送信スレッドでの負荷分散によって強化されました。
* トランザクションメッセージングプロセスは、同じメッセージの複数の分析で開始できるように最適化されています。
* トランザクションプッシュ通知のスループットと遅延が一貫しない可能性がある問題を修正しました。
* トランザクションメッセージ実行配信のターゲットオーディエンスが正しくない問題を修正しました。
* イベント設定と関連付けられたトランザクションメッセージを含むパッケージを読み込むと発生していた問題を修正しました。For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* 製品リストを含むトランザクションメッセージ用に作成されたテストプロファイルから収集データを削除する問題を修正しました。

### Other changes {#other-changes}

* SMS外部アカウントに新しいオプションが追加されました。同時接続の数をより適切に制御するために、SMSを送信するMTAプロセスの最大数を制限できます。For more information, refer to the [SMS connector protocol and settings](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) technote.
* API拡張機能を使用してリソースを公開する場合、APIが既に公開されている場合は、APIが再度公開されるたびに自動的に更新されるようになりました。これまでは、このアクションは手動で、APIの更新に失敗すると、このAPIのプロファイルまたはサービスリソースが壊れる可能性がありました。For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 郵便番号ディメンションが動的レポートから削除されました。代わりに、City、Country、Stateディメンションを使用することをお勧めします。
* アプリ内メッセージの「初回起動」ライフサイクルイベントトリガーが削除されました。
* セキュリティグループでパッケージをエクスポートする場合、各グループに割り当てられているロールが含まれるようになりました。（CAR-32960）
* 読み込みファイルアクティビティでは、新しいオプションを使用すると、アップロードするファイルの列が列の定義に一致することを確認できます。For more information, refer to the [detailed documentation](../../automating/using/load-file.md). （CAR-32229）
* ワークフローをペイロードで開始できるようになり、ワークフロー内のアクティビティ間で外部パラメーターを使用および共有できるようになりました。For more information, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md). （CAR-29412&amp; CAPET-29413）
* キャンペーン標準APIで、ペイロードを使用してプロファイルの地理的および組織単位を更新できるようになりました。For more information, refer to the [detailed documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* データベースからのオブジェクトにアクセスできない場合にエラーメッセージが表示されるようになりました。
* ファイルアクティビティの抽出で、エクスポートするファイルの名前を定義するときにJavaScript機能が更新されました。"Output"フィールドでは、formatDate関数のみを使用できるようになりました。For more information, refer to the [detailed documentation](../../automating/using/extract-file.md).
* カスタムリソースの自動シーケンスIDの生成が改善されました。新しいカスタムリソースのプライマリキーは、デフォルトで64ビットになりました。
* カスタムリソース発行テストモードが改善されました。最後のカスタムリソースのパブリケーションに失敗し、修正されなかった場合に、ユーザーに警告メッセージが表示されるようになりました。カスタムリソースの発行エラーが発生した後、最後の作業バージョンにロールバックできます。For more information, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* 「転送ファイルアクティビティ」に新しいオプションが追加されました。ファイルのダウンロードアクションを使用するときにSFTPモードでファイルを並べ替えることができます。For more information, refer to the [detailed documentation](../../automating/using/transfer-file.md). （CAR-33109）

### Patches {#patches}

* SMS設定がリロードされると、メモリリークがMTAに発生する可能性がある問題を修正しました。
* 修復モードでデータベースの更新を公開できない可能性がある問題を修正しました。
* Adobe AnalyticsレポートとAdobe Campaign動的レポートに相違がある問題を修正しました。（CAR-25393）
* レポート共有ワークフローが失敗する原因となっていたエラーを修正。
* ユーザーがメディアURLだけでアプリ内メッセージを送信できなかったエラーを修正しました。
* インスタンスに証明書がアップロードされていない場合でも、モバイルアプリが表示される問題を修正しました。
* Fixed an error that prevented personalization fields from working when using the **Target all users of a Mobile app** template.
* 新しいキャンペーン標準インスタンスがプロビジョニングされました。（CAR-32635&amp; CAC-32344）
* ワークフローの日付数式をカスタマイズできないエラーを修正しました。（CAR-30336）
* カスタム日付数式を定義する際に、ドロップダウンリストで「追加データ」フィールドと「セグメントコード」フィールドが使用できない問題を修正しました。（CAR-32383）
* 「ファイルの転送」および「ファイルを抽出」アクティビティが暗号化されていても、ファイルが見つからないという問題を修正しました。（CAR-32377）
* APIで、lineCountフィルターが正確な合計数をレンダリングできない問題を修正しました。（CAR-31424）
* ランディングページで、変更した値が変更されたときに入力フィールドが表示されない問題を修正しました。（CAR-31401）
* シグナルアクティビティが予期せずアクティブ化される可能性がある問題を修正しました。
* オーディエンスが空の場合に電子メールのプレビューが表示されない可能性がある問題を修正しました。
* 「ファイルを抽出」アクティビティで、「受信移行が空の場合にファイルを生成しない」オプションがアクティブ化された場合にファイルを生成できる問題を修正しました。
* 配信品質ワークフローが正常に終了しなかった場合に、配信品質のワークフローが無効になる問題を修正しました。
* ユーザーがレポートを保存またはスケジュールできない可能性がある問題を修正しました。（CAR-31133）

## Release 19.1.3 - March 2019 {#release-19-1-3---march-2019}

### Email Designer enhancements {#email-designer-enhancements-1}

* テンプレートを保存後にテンプレートを変更できない問題を修正しました。
* 以前に作成したテンプレートを電子メールで使用する際の様々な問題を修正しました。
* インポートされたテンプレートでコンポーネントを非表示にできない問題を修正しました。

### Other improvements {#other-improvements}

* タイポロジルールを表示する際のエラーを修正しました。（CAR-32059&amp; CAC-31849）
* タイポロジルールを編集できない問題を修正しました。（CAR-31750）
* InMailプロセスで予期せず停止する問題を修正しました。（CAR-31238）

## Release 19.1 - February 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Push channel Reporting improvements<br /> </td> 
   <td> <p>プッシュチャネルレポートにはいくつかの改良点があり、ユーザーエンゲージメントをより直感的に測定できます。このリリースでは、以下の3つの異なる指標にプッシュチャネル指標のリストを展開しています。インプレッション、クリック、開く（アプリを開く）を使用すると、ユーザーのプッシュ通知とのインタラクションをより効率的に測定および分析できます。これに加えて、これらの指標の定義と実装も標準化しています。また、プッシュ通知レポートは、一般的に使用されるビジュアライゼーションと指標でも改善されました。</p><p> For more information, refer to the <a href="../../reporting/using/push-notification-report.md">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Launch integration for Mobile App<br /> </td> 
   <td> <p>このリリースには、Adobe Campaign Platform LaunchおよびMobile SDKのAdobe Campaign Standard用のGAバージョンのAndroidおよびiOS Extensionsとの統合が含まれています。これらの拡張機能は、プッシュメッセージ、アプリ内メッセージおよびモバイルアプリプロファイルの更新をサポートしています。</p><p> For more information, refer to the <a href="../../administration/using/about-typology-rules.md#typology-rules">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile In-App Messaging<br /> </td> 
   <td> <p>このリリースには、キャンペーン内のアプリ内チャネルのGAバージョンが含まれています。機能的な観点から、ベータ版リリースに最も注目すべき点は、アプリ内チャネルの動的レポートと、Mobile SDKとMCYASの間の安全なハンドシェイクです（アプリ内ルールをSDKに提供するMarketing Cloud内アプリメッセージサービス）。安全なハンドシェイクを使用すると、ユーザーのPIIデータが悪意のあるハンドになり、ユーザーがログアウトするたびにメッセージキャッシュをクリアすることで、共有デバイスでのユーザーのプライバシーを維持できます。</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Workflow enhancements<br /> </td> 
   <td> <p>次のワークフロー機能が追加されました。</p> 
    <ul> 
     <li> ワークフロー内でアクティビティをコピー&amp;ペーストしたり、同じキャンペーンインスタンスから別のワークフローをコピーしたりできるようになりました。これにより、ワークフローまたは特定のアクティビティ全体を簡単に複製し、最初に定義された設定を維持することができます。For more information, refer to the <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">detailed documentation</a>. （CAR-20014） </li> 
     <li> <strong>ファイル</strong> アクティビティの読み込み時に、拒否されたレコードを含むファイルの名前にタイムスタンプを追加できるようになりました。For more information, refer to the <a href="../../automating/using/load-file.md#configuration">detailed documentation</a>. </li> 
     <li> <strong>クエリー</strong> および <strong>セグメント</strong> アクティビティで、アクティビティにデータがない場合にアウトバウンドトランジションを有効にできるようになりました。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-1}

* 生成されたランディングページのHTMLコードが更新され、検索エンジンのインデックスを作成できないようになりました。

### Email Designer enhancements {#email-designer-enhancements-2}

* Behanceアーティストが設計した、クラスに優れた4つのレスポンシブレスポンシブ電子メールテンプレートを利用できるようになりました。

   For more information, refer to the [detailed documentation](../../start/using/about-templates.md#content-templates).

* 新しいオンボーディング体験により、電子メールの作成を迅速に開始し、ドキュメントやチュートリアルに簡単にアクセスできます。

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#email-designer-home-page).

* ニーズに応じて列数と幅を柔軟に設定できるようになりました。

   For more information, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* モバイルビューで編集する場合、特定のコンポーネントをモバイル表示でのみ非表示にして、スペースを効果的に使用できます。

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* 既に利用可能な電子メールテンプレートにカスタムソーシャルチャネルを追加できるようになりました。
* 18を超える構造を使用すると構造メニューを下にスクロールできない問題を修正しました。（CAR-31173）
* Adobe Campaignで送信されたプリヘッダーを含む電子メールを転送すると、コンテンツの上部にプリヘッダーが表示される問題を修正しました。（CAR-30736）
* Fixed an issue that prevented the subject line from being updated when clicking the **Refresh AEM content** option after modifying the subject in Adobe Experience Manager. （CAR-29984）
* Adobe Targetの動的な画像を使用できない問題をいくつか修正しました。
* コンテンツが以前URLからインポートされている場合に、準備時にコンテンツを更新する際にプレビューが更新されない問題を修正しました。
* The YouTube icon has been added to the **Social** content component.
* The **List** view has been added for content components and fragments displayed in the Email Designer palette.

### Other improvements {#other-improvements-1}

* SDK V4およびAEP SDKアプリの両方について、Adobe Campaignが完全にFCMに準拠しました。
* Adobe Campaignでは、AppleによるWatchOSだけでなくAndroidによるプッシュ通知もサポートされています。
* インターフェイス内でのナビゲーション時に表示される警告メッセージとエラーメッセージが明確になり、理解しやすくなりました。
* オプトインおよびオプトアウトに関連するプロファイルリスト列に追加できるようになりました（「今後の連絡は不要です…」フィールド）。
* プロファイル作成画面のタイムゾーンドロップダウンリストが、「アドレス」セクションからインターフェイスの上部セクションに移動しました。
* カスタムリソース画面の設定時に区切り文字を追加できるようになり、フィールドをカテゴリに整理できるようになりました。

   For more information, refer to the [detailed documentation](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Other changes {#other-changes-1}

* Adobe CampaignおよびAdobe Experience Cloudは、2019年春のMicrosoft Internet Explorer11およびCampaign Standard19.2リリースのサポートを終了します。Microsoft Edgeまたは別のサポート対象ブラウザーに切り替えてください。[廃止された機能および削除された機能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) ページを参照してください。
* The **Country code** field from the Profile resource has been renamed to **Country/Region code**.

### Patches {#patches-1}

* テストプロファイルを電子メールトランザクションメッセージに追加する際にメッセージが送信されない問題を修正しました。（CAR-29854）
* すべてのチャネルからのメッセージ送信が同時にトリガーされた場合に、他のチャネルから送信されるメッセージが、その他のチャネルから低速になる問題を修正しました。
* 外部アカウント接続が確立されていない場合に、MTAがSMSメッセージの送信を開始する問題を修正しました。
* スケジューラーアクティビティの実行頻度と開始時間が発生していた問題を修正しました。（CAR-30745）
* 拡張プロファイルリソースを使用するとPKEYの生成に発生する可能性がある問題を修正しました。（CAR-30285）
* カレンダー日ベースの疲労ルールで発生する可能性がある問題を修正しました。（CAR-30136）
* "Base"で終わる名前を持つカスタムリソースにアクセスしようとすると発生する可能性がある問題を修正しました。（CAR-30109）
* パッチ呼び出しを使用してサービスにプロファイルをサブスクライブできなかった問題を修正しました。（CAR-29728）
* 読み込みファイルアクティビティでXMLファイルを読み込む際にワークフローが破損する可能性がある問題を修正しました。（CAR-29208およびCAR-28205）
* カスタムリソースをリンクすると、逆基数リンクが生成されない可能性がある問題を修正しました。（CAR-30476）
* セグメントコードのみを使用する場合に配信ログを拡張できない問題を修正しました。
* ワークフローでファイル転送アクティビティを使用すると行が複製される可能性がある問題を修正しました。
* 指定した時刻に予定レポートが送信されない問題を修正しました。
* ワークフローでのアプリ内配信の「配信する」および「送信済み」 KPIの相違が発生する問題を修正しました。
* カスタムHTMLで作成されたアプリ内メッセージでトラッキングできない問題を修正しました。
* ワークフローでアプリ内配信コンテンツを保存できない問題を修正しました。
* 管理者にモバイルアプリケーションが表示されない問題を修正しました。
* 配信品質の更新の技術ワークフローが失敗する問題を修正しました。（CAR-26387）
* アプリ内配信の作成中にターゲット設定されたプロファイルと配信ダッシュボードに表示されていたプロファイルの相違を修正しました。（CAR-28722）
* CampaignとAssetsコアサービスの統合で、電子メールで共有アセットを選択できない可能性がある問題を修正しました。

## Release 19.0 - January 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email Designer General Availability<br /> </td> 
   <td> <p>新しい直観的な電子メールデザイナー（旧称Creative Designer）はGAに移動しました。これで、次のようなレガシーコンテンツエディターのすべての機能がサポートされるようになりました。</p> 
    <ul> 
     <li> The use of <a href="../../integrating/using/adding-target-dynamic-content.md">dynamic images from Adobe Target</a> </li> 
     <li> The ability to <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">retrieve content from a URL automatically at preparation time</a> </li> 
     <li> Fully compliant <a href="../../start/using/about-templates.md#content-templates">out-of-the box content templates</a>. </li> 
    </ul> 
    <p>For more information, refer to the <a href="../../designing/using/about-email-content-design.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">how-to video</a>. 以下に、機能強化および修正点を示します。</p><p>その結果、レガシー電子メールコンテンツエディターは非推奨となりました。For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Product Listings in Transactional Emails<br /> </td> 
   <td> <p>トランザクションの電子メールメッセージで、1つまたは複数の製品コレクションを参照できるようになりました。例えば、ユーザの買い物かごにあるすべての製品を画像、価格、各製品へのリンクと共に一覧表示する買い物かごの放棄電子メールを自動的に送信できます。</p><p>For more information, refer to the <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">how-to video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile View in the Email Designer<br /> </td> 
   <td> <p>電子メールコンテンツを編集する際に、専用のモバイルビューに切り替えることができるようになりました。これにより、マージン、フォントサイズの小さいフォント、背景色などのすべてのスタイルオプションを個別に編集することで、電子メールのレスポンシブデザインを微調整できます。</p><p> For more information, refer to the <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> In-App Messaging Beta Improvements<br /> </td> 
   <td> <p>アプリ内メッセージベータ版機能が強化され、次の機能が強化されました。</p> 
    <ul> 
     <li> アプリ内ベータチャネルはGGPR準拠です </li> 
     <li> Analytics APIとの統合により、Triggersドロップダウンにデータを挿入 </li> 
     <li> 配信テンプレートの直感的な外観と説明 </li> 
     <li> ユーザビリティの観点からのインターフェイスの強化 </li> 
    </ul> <p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* データアクティビティの読み込みの新しいオプションで、拒否されたレコードを含むファイルに処理後ステージを適用できるようになりました（例:郵便番号圧縮）。（CAR-24521）
* 更新データアクティビティの新しいオプションにより、アップロードするデータの最大バッチサイズを設定できるようになりました。（CAR-28400）
* プロファイルのアドレス状態の選択を改善。国を選択すると、「州」ドロップダウンリストが、関連する状態値で自動的に更新されるようになりました。（CAR-28874）
* ファイルアクティビティの抽出の新しいオプションで、受信移行が空の場合にファイルを生成できないようになりました。これにより、SFTPサーバーで空のファイルを作成およびアップロードすることを防ぎます。
* 配信サマリレポートが改善されました。
* プロファイルのアドレスを定義する際に利用可能な国のリストが強化されました。（CAR-26707）
* 組み込みワークフローをインポートしようとするとエラーメッセージが表示されるようになりました。

### Email Designer {#email-designer}

* Adobe Campaignでこの機能が無効になっている場合でも、電子メールテンプレートまたは電子メールデザイナーで作成されたコンテンツフラグメント機能が有効になっていても、電子メールテンプレートまたは電子メールのコンテンツフラグメントが有効になっていた問題を修正しました。（CAR-28174）
* 電子メールデザイナーでコンテンツを編集する際に動的コンテンツ条件を保存できない問題を修正しました。（CAR-27905）
* 電子メールのプレーンバージョンのメッセージを編集し、電子メールDesignerでHTML同期を分割した後に、電子メールコンテンツからHTMLバージョンを削除する問題を修正しました。（CAR-28507）
* Internet Explorer11の使用時に電子メールデザイナーインターフェイスが開く問題を修正しました。（CAR-28273）
* 電子メールデザイナーのボタンに適用されたスタイル設定のMicrosoft Outlookレンダリングがゆがめる問題を修正しました。
* 電子メールDesignerで、フラグメントがデフォルトでロックされていると想定されない電子メールで使用されていた、コンテンツフラグメントからURLを編集可能にしていた問題を修正しました。
* Microsoft Officeで電子メールデザイナーの区切りコンポーネントが表示されない問題を修正しました。
* レガシー電子メールコンテンツエディターを使用してAEMから同期されたコンテンツを表示すると、特定のインターネットブラウザーでページがフリーズする問題を修正しました。（CAR-29068）
* レガシー電子メールコンテンツエディターの使用時に電子メール内の任意の画像をクリックすると発生するエラーを修正しました。（CAR-30424）
* 電子メールデザイナーで電子メールを編集する際に、新しく作成されたフラグメントが表示されない問題を修正しました。（CAR-29928）
* 電子メールデザイナーで作成され、Outlook Webメールクライアントを使用して受信した電子メールにボタンテキストが正しく表示されない問題を修正しました。
* これで、電子メールデザイナーを使用してプロファイルトランザクションメッセージを作成できます。（CAR-28900）
* 電子メールDesignerで、URLからコンテンツを自動的に取得するときにコンテンツを編集可能にし、ロックする必要があるという電子メールデザイナーのエラーを修正しました。

### Patches {#patches-2}

* 動的レポートで誤った配信ログが表示される問題を修正しました。（CAR-23446）
* バウンスサマリレポートの数字に影響する可能性がある問題を修正しました。（CAR-28703）
* Fixed an issue with the Campaign and Assets Core Service integration which could prevent assets from being displayed when selecting **[!UICONTROL Image shared from Adobe Experience Cloud]** in an email (CAMP-28732).
* 外部アカウントでのトランス集計が許可されている場合でも、"pa"文字を含むSMSメッセージが送信されない問題を修正しました。（CAR-29041）
* ワークフローでセグメント化アクティビティを使用すると重複するレコードが表示される問題を修正しました。（CAR-28743）
* ワークフローアクティビティの列にある値マッピングの1つを削除できなかった問題を修正しました。（CAR-28708）
* ファイル転送アクティビティで、「ファイルが存在するかどうかをテストする」というワイルドカードを使用してワイルドカードを使用する場合に発生していた問題を修正しました。（CAR-28977）
* 外部アカウント設定の更新時に発生する可能性があるファイル転送アクティビティの問題を修正しました。（CAR-28894）
* 「電子メールが空でない」条件を使用すると、クエリエディターのカスタムフィルターの問題が修正されました。（CAR-28741）
* 100,000件を超えるレコードを含むカスタムリソーステーブルを書き出すと発生する問題を修正しました。（CAR-28150）
* トリガーにリンクされているトランザクションメッセージを削除できない問題を修正しました。（CAR-28385）
* 一部のSMSログに安全に表示されていなかったパスワードを削除しました。
* Adobe Campaignによって送信される空のパスワードが原因でSMPPシミュレーターへの接続が失敗する問題を修正しました。
* SMS接続が不安定な場合にキャンペーンを送信できない問題を修正しました。
* 動的レポートで削除された配信が表示される問題を修正しました。
* ワークフローでのエンリッチメントアクティビティを使用すると、配信ログから追加のデータを取得できない問題を修正しました。
* "Nカーディナリティコレクションリンク」リンクタイプを使用し、「ターゲットレコードを削除すると、リンクによる参照の削除を意味する」というDGPRのリクエストが発生する問題を修正しました。
* レポートの共有の問題を修正しました。
* プッシュ通知を送信するとスループットの問題が発生する可能性がある問題を修正しました。
* ダイレクトメール出力ファイルにフィールドがない問題を修正しました。
* ユーザーが組み込みワークフローを変更できる問題を修正しました。
* 設定された抽出アクティビティのワークフローを含むキャンペーンテンプレートに基づいてキャンペーンを作成する際の問題を修正しました。（CAR-29198）
* 複数の要素に対して同じ式を使用できなかったファイル抽出アクティビティの問題を修正しました。（CAR-29182）
* クエリエディターで、rtEventのBroadlogとトラッキングログの結合条件を持つ問題を修正しました。（CAR-28780）
* 「特定のアクション」ランディングページオプションを変更できない問題を修正しました。（CAR-29422）
* ワークフローでイベントのペイロードをエクスポートできなかった問題を修正しました。（CAR-29029）
* ブラックリストに記載されたSMS番号がSMSメッセージに除外されない問題を修正しました。（CAR-28898）
* 着信メッセージの処理中にエラーが発生した場合にSMPPプロバイダーに通知されない可能性がある問題を修正しました。（CAR-29804）
* 関連する配信を持つ外部アカウントが削除される問題を修正しました。（CAR-29738）
* SMSメッセージの送信スループットが向上し、安定しました。
* SMSメッセージで"~"文字が使用できない問題を修正しました。（CAR-29172）
* 送信時間の最適化オプションを使用した配信の問題を修正しました。（CAR-29231）

