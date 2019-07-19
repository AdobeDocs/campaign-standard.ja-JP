---
title: リリースノート2018
seo-title: リリースノート2018
description: リリースノート2018
seo-description: このページには、Adobe Campaign Standardの2018リリースすべてが一覧表示されます。
page-status-flag: 常にアクティブ化されていない
uuid: 99f92a54-4b3d-48b9- b08d- e98b24e75f62
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: 参照
topic-tags: campaign- standard- release
discoiquuid: e54f8305-7e32-4193-8e5a- b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Release Notes 2018{#release-notes}

Adobe Campaign Standardの2018年リリースを探しますか。

各リリースには、新機能およびパッチが含まれています。そのコンテンツを表示するには、リリースをクリックします。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 18.9 - September 2018 {#release-18-9---september-2018}

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
   <td> In-App messaging (beta)<br /> </td> 
   <td> アプリ内メッセージを使用すると、コンテキストインタラクションを提供し、プッシュ通知をオプトアウトする可能性のあるユーザーに到達できるように、モバイルアプリのユーザーをより効率的に惹きつけることができます。プッシュ通知と連携してアプリ内メッセージを使用すると、高度にパーソナライズされた関連性の高いエクスペリエンスを作成できます。これにより、アプリユーザーのコンバージョン率と定着率が向上します。<br /> 詳しくは、 <a href="../../channels/using/about-in-app-messaging.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> Adobe CampaignとAdobe Campaignの統合により、Mobile SDK V5を使用したキャンペーンでのモバイルアプリプロパティのアクティブ化プロセスを簡素化および自動化できるようになりました。<br /> 詳しくは、 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Adobe Campaign Standardで、Amazon S3APIのバージョン4がサポートされるようになりました。

### Other changes {#other-changes}

* ブロードログでは、接続の最大数と1時間あたりの最大メッセージ数が区別されるようになりました。制限に達すると、スループットが制限される理由を知ることができます。以前は、両方のケースに同じメッセージ（「割り当てmatched"）が適用されていました。
* Campaignでモバイルアプリケーションを設定する場合、iOS証明書とAndroidサーバーキーが正常にアップロードされたかどうか、およびその有効期限がユーザーに通知されるようになりました。

   For more on this, refer to the detailed documentation on how to configure a mobile application using [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* 特定のMobileアプリのユーザーをターゲットに設定するには、キャンペーンプロパティの定義中にMobileアプリを選択します。この機能は、プッシュチャネルとアプリ内メッセージチャネルの両方に対応しています。

   For more information, refer to the [detailed documentation](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Creative Designerインターフェイスを使用してコンテンツブロックを選択すると、リストからのすべてのコンテンツブロックが読み込まれて表示されるようになりました。（CAR-27311）

   For more on this, refer to the [detailed documentation](../../designing/using/adding-a-content-block.md).

### Patches {#patches}

* 電子メールのダッシュボードと電子メールのサマリレポートの間のログ数に相違がある問題を修正しました。（CAR-28237
* ファイル転送アクティビティでファイルを読み込む際にエラーメッセージが表示される可能性があるワークフローの問題を修正しました。（CAR-27435）
* フォーム内でサービスをランダムに選択解除するという、25種類のサービスを含むランディングページの問題を修正しました。（CAR-26572）
* ファイル転送アクティビティの使用時に、SFTP URLを持つ外部アカウントを設定できないワークフローの問題を修正しました。（CAR-26475）
* サービスの概要レポートが更新できない問題を修正しました。（CAR-26301）
* エンリッチメントアクティビティの使用時に、カスタムフィールドに正しい日付が表示されない問題を修正しました。（CAR-26242）
* ファイルインポートからインポートしたときにサービス購読日が更新されない問題を修正しました。
* ワークフローでファイルのインポートを妨げていた読み込みファイルアクティビティのエラーを修正しました。
* サービスサマリレポート（CAR-25587）で誤った購読数が表示される問題を修正しました。
* Adobe AnalyticsレポートとAdobe Campaignレポートのデータに相違がある問題を修正しました。（CAR-25393）
* 制限付きアクセスユーザーがログインできない可能性がある問題を修正しました。（CAR-27381）
* Creative Designerを使用して電子メールを編集する際に、Adobe Experience Managerのコンテンツのリストが表示されない可能性がある問題を修正しました。（CAR-27181）
* Creative Designerでエラーが発生してエラーが発生する可能性がある問題を修正しました。（CAR-27304）
* Internet Explorer11を使用すると、Creative Designerでドラッグ&amp;ドロップが正しく動作しない問題を修正しました。
* カメラからアップロードし、ポートレイトモードで撮影した画像に、不要な回転位置が表示される問題を修正しました。
* Creative Designerでクエリエディターインターフェイスを使用すると、選択情報が不明確に表示される問題を修正しました。
* Creative Designerのクエリエディターインターフェイスを使用すると、要素が正しく複製されない問題を修正しました。
* 自動返信を使用して登録解除された場合でも、ブラックリストに記載された受信者にSMSメッセージを配信する問題を修正しました。（CAR-27128）
* **データベースのクリーンアップ** ワークフローが失敗する原因となっていたエラーを表示できない問題を修正しました。（CAR-26876）
* プッシュ通知定義でカスタムフィールドを削除できない可能性がある問題を修正しました。（CAR-25588）

## Release 18.7 - July 2018 {#release-18-7---july-2018}

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
   <td> High priority flag for Android push notifications<br /> </td> 
   <td> Android用の優先度の高いフラグ- Androidアプリの優先度が高いプッシュ通知を配信して、一部の制限付き処理を起動して実行することを有効にします。デフォルトの優先順位が「標準」であることに注意してください。これにより、メッセージの配信がバッテリーの節約に遅れる可能性があります。<br /> 詳しくは、 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology filter for mobile app subscribers<br /> </td> 
   <td> タイポロジフィルターでのサポートの購読-タイポロジルールのフィルター条件を指定する場合、アプリの購読はフィルターおよびターゲット設定ディメンションとして選択でき、プロファイルを使用したり、プロファイルなしでユーザーの属性をフィルタリングしたりできます。<br /> 詳しくは、 <a href="../../administration/using/about-typology-rules.md#typology-rules">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Automated content import from a URL during message preparation<br /> </td> 
   <td> 準備段階でURLから電子メールコンテンツをインポートできるようになりました。定期的な電子メール配信の場合、最新のHTMLコンテンツは、電子メールの送信時にコンテンツが常に最新の状態に保たれるように毎回取得されます。また、コンテンツがまだ準備されていない場合でも、URLからのコンテンツを含むスケジュール配信を作成することもできます。<br /> 詳しくは、 <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign release notification message<br /> </td> 
   <td> インスタンスのアップグレード後にユーザーがログインしたときにポップアップメッセージが表示されるようになりました。メッセージにはバージョン番号が表示され、リリースノートへのリンクが含まれます。You can choose to hide the message until the next release. <br /> </td> 
  </tr> 
  <tr> 
   <td> User management<br /> </td> 
   <td> 地理単位機能は、新しいキャンペーン標準インスタンスと、18.7リリースを開始した地理単位のない既存のインスタンスで使用できなくなりました。<br /> 詳しくは、 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">このページ</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-1}

* The Adobe Campaign and Adobe Target integration now allows you to leverage Target’s [Permissions](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) feature. Adobe Targetから動的な画像を電子メールに含める場合、Targetプロパティ（at_ propertyコード）を指定できるようになりました。
* プロファイルリソースへのOwcopyリンクを持つカスタムリソースが、GGPRのプライバシーアクセス/削除リクエストによって考慮されるようになりました。単純リンクとN基数のコレクションリンクの単純なリンクでは、「ターゲットレコードの削除/複製」を選択して、カスタムリソースのリンクによって参照されるレコードを削除または複製する必要があります。0または1個の単純なリンクの場合、「レコードの削除/複製」を選択すると、リンクによって参照されているターゲットレコードを削除/複製することを意味します。

### Other changes {#other-changes-1}

* レポートの共有タイムアウトが、タイムアウトエラーを回避するために1~4分に延長されました。
* 電子メールのコンテンツを編集すると、デフォルトで新しいCreative Designerが開きます。必要に応じて、変更を保存した後でもいつでもデフォルトのコンテンツエディターに戻ることができます。For more on this, refer to the [detailed documentation](../../designing/using/about-email-content-design.md).
* Creative Designerでは、新しいコンテンツコンポーネントを電子メールに追加できるようになりました。カルーセル。For more on this, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#about-content-components).
* In a transactional message hot click report, when you click the **Change profile** button, now only the test profiles linked to the event that you defined for your transactional message are listed.

### Patches {#patches-1}

* ByEmailクエリフィルターの結果を返すことができなかった問題を修正しました。（CAR-23420）
* 管理者（/rest/head/*エンドポイント、トランザクションメッセージ画面、プロファイル、オーディエンスの読み込み画面）に制限されている特定の機能または画面に標準ユーザーがアクセスできる問題を修正しました。
* DGPRプライバシーの削除リクエストで、数字が開始した場合にカスタムリソースが処理されない問題を修正しました。
* Adobe Experience Cloudで、オーディエンスの共有アクティビティを保存できなかったエラーを修正しました。
* ファイル転送アクティビティで、ファイル名に空白スペースが含まれる場合に発生する問題を修正しました。（CAR-25936）
* セッションの有効期限が切れた後に再接続ボタンを使用すると発生する可能性がある問題を修正しました。（CAR-25560）
* ファネルルールに関連付けられたタイムゾーンの最適化を使用して配信を送信すると除外される可能性がある問題を修正しました。（CAR-25425）
* API GDPR機能を使用すると、0-1タイプのリンクでデータを削除できない問題を修正しました。
* 疲労タイポロジルールのエディションをキャンセルするとエラーメッセージが表示される可能性がある問題を修正しました。
* 編集後に配信コンテンツをプレビューすると発生する可能性がある問題を修正しました。
* 「解凍」オプションの使用中にCSV zipファイルを処理すると発生する問題を修正しました。
* Creative Designerで、リンクのスタイル設定やリンクの編集の際に、不要なカラーフォントや書式を変更すると不要なカラーフォントと書式が発生する問題を修正しました。（CAR-26001）
* 動的なコンテンツを含む配信の各条件の割合をホットクリックレポートで表示できない問題を修正しました。以前は、デフォルトのバリアントのクリックのみが表示されていました。

## Release 18.6 - June 2018 {#release-18-6---june-2018}

### Improvements {#improvements-2}

* The **[!UICONTROL History]** API has been added to Adobe.IO. プロファイルのマーケティング履歴に関連する情報にアクセスできます。タッチポイント数、送信配信、ミラーページURLなどFor more on this, refer to the [dedicated use case](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* **[!UICONTROL Database cleanup]** 技術ワークフローは、データベースバックアップのパフォーマンスを向上させるために最適化されています。
* 電子メール用のクリエイティブデザイナーもフランス語とドイツ語で利用可能になりました。

### Other changes {#other-changes-2}

* **[!UICONTROL Compute stats]** 送信された配信の **[!UICONTROL Deployment]** ウィンドウにボタンが追加されました。例えば、送信の結果が長すぎるか、考慮されていない場合など、最新のKPIを取得できます。For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* **最新の技術ワークフローを配信する** ための更新で、機能管理者は **、更新ルール** のjavascriptアクティビティで無視する連続エラーの数を定義できるようになりました。デフォルトでは、フィールドの値は0に設定されており、すべてのエラーは無視されます。
* ユニットアクセス制限条件の管理時に生成されるSQLが最適化されました。
* **[!UICONTROL Update]** これで、購読に関連するデータを追加、更新または削除できます（nms:appSubscriptionRcpテーブル）。
* The **[!UICONTROL Update delivery execution]** technical workflow has been divided into two workflows in order to optimize performance: - **[!UICONTROL Update delivery execution]**: updates the delivery's tracking. デフォルトでは10分ごとに開始されます。**[!UICONTROL Update delivery indicators]**:配信のKPIは、デフォルトで1時間ごとに更新されます。For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* When a delivery is sending messages, the status in the **[!UICONTROL Deployment]** section can now have two values: **[!UICONTROL Sending]**: the messages are being sent. **[!UICONTROL Sending (retry)]**:再試行パスが進行中です。
* **[!UICONTROL Delivery preparation]** ロールを持つユーザーが配達確認を送信できるようになりました。（CAR-24313）
* The **Enable TLS over SMPP** option has been added to the **SMS routing via SMPP** external account. For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patches {#patches-2}

* Adobe Target（CAR-24848）の動的な画像を含めると電子メールが送信されない可能性がある問題を修正しました。
* **[!UICONTROL Privacy Access/Delete Request]** 技術ワークフローの問題を修正しました。リクエストのいずれかが失敗した場合には完了しませんでした。
* プライバシーコアサービスがキャンペーンからリクエストステータスの更新を受信できなかった問題を修正しました。
* **[!UICONTROL Import shared audience]** 技術ワークフローが正常に機能できなかった問題を修正しました（CAMP-25465）。
* コアプライバシーサービスでキャンペーンプライバシーリクエストが完了していない問題を修正しました。
* Adobe IDが長すぎる場合に、特定のユーザーがIMS認証によってキャンペーンStandardにログインできない可能性がある問題を修正しました。（CAR-24095）
* コンテンツモジュールを削除すると発生する可能性がある、Creative Designerの問題を修正しました。（CAR-25242）
* データベース内のプロファイルのないサブスクライバーにプッシュ通知ルールを使用する場合の問題を修正しました。（CAR-25344）
* 配信の除外ログにアクセスするとエラーメッセージが表示される可能性がある問題を修正しました。（CAR-24724）
* 拡張送信ログのインスタンスで校正が準備されない問題を修正しました。
* **[!UICONTROL Sending log]** 拡張機能を有効にしてカスタムリソースを公開すると発生する可能性がある2つの問題を修正しました。
* 定期配信で配信期間が考慮されない問題を修正しました。
* Fixed an issue that could occur when sorting data in the **[!UICONTROL Client data]** menu, for custom resources with more than 100K records. （CAR-24308）
* 動的レポートで検索機能を使用する際に考慮されなかったカスタムプロファイルディメンションの問題を修正しました。
* 動的レポートのアカウントレベルでの国際データの表示に関する問題を修正しました。
* 購読または購読の確認解除メッセージなしでサービスを作成できるようになりました。

## Release 18.5 - May 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> プライバシーコアサービス統合を使用すると、単一のJSON API呼び出しを通じて、マルチソリューションコンテキストでGGPRリクエストを自動化できます。<br /> プライバシーコアサービスからすべてのExperience CloudソリューションにプッシュされたGDPRリクエストが、キャンペーンで自動的に処理されるようになりました。<br /> 詳しくは、 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Push improvements - detailed delivery feedback<br /> </td> 
   <td> Adobe Campaignでは、MCPNSを介してプロバイダー（APNS/GCM）からプッシュメッセージに詳細なフィードバック（ログの除外ログを送信）を受信できるようになりました。<br /> 詳しくは、 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs extension<br /> </td> 
   <td> 配信ログ拡張を使用すると、プロファイルデータおよびワークフローからのセグメントコードを使用して、ログの送信を拡張できます。この情報は、動的レポートで使用でき、配信時に一部の情報のスナップショットを保持できます。<br /> 使用例は2つあります。<br /> 
    <ul> 
     <li> 拡張されたデータを使用して拡張されたBroadlogsをエクスポートする:マーケティング担当者は、セグメントコードが"A"に等しいすべてのプロファイルをエクスポートしたいと思います（ワークフローエンジンからのアクセス）。 </li> 
     <li> Segmentation on "frozen" data: As a marketer, I would like to <strong>retarget</strong> all profiles who have won 1000 loyalty points since the last sending or where segment code was equal to "A". </li> 
    </ul> For more information, refer to the <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> この機能により、プロファイルリソース拡張機能で作成されたカスタムプロファイルデータに基づいてレポートを作成および管理できます。忠誠度プログラム、好みのチャネルなどのプロファイル属性ごとにレポートを分類できます。<br /> 詳しくは、 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-3}

* アプリケーションの全体的なメモリとCPU使用量が強化されました

### Other changes {#other-changes-3}

* オーディエンスの読み込みワークフローアクティビティで、Experience Cloudオーディエンスを読み込めるようになりました。以前は、このアクティビティはQueryオーディエンスとListオーディエンスのみを読み上げることができました。Refer to the [detailed documentation](../../automating/using/read-audience.md). （CAR-23623）
* デフォルトの共有データソースの識別子が読み取り専用モードになり、変更できなくなりました。このIDを変更すると、Experience Cloudでオーディエンスを共有する際に問題が発生する可能性があります。
* Audience Managerからのオーディエンスの読み込みが、分割ファイルで機能するようになりました。以前は、importSharedAudienceのテクニカルワークフローによって、セグメントの最後のファイルのみがインポートされていました。
* AWS S3外部アカウントで、地域およびバージョン4認証メカニズムがサポートされるようになりました。Refer to the [detailed documentation](../../administration/using/external-accounts.md).
* アセット選択ウィンドウの読み込みが速くなり、問題なくウィンドウを終了することができるようになりました。
* 技術的なワークフローのプロパティと構造を、管理者権限を持つユーザーによって変更し、「すべて」の組織および地理単位に所属できるようになりました。
* セグメントの作成時にセグメント化アクティビティインターフェイスで強化された機能は次のとおりです。制限を追加した直後に「制限」タブが表示されるようになりました。新しいセグメント名が増分されるようになりました（「セグメント1"、「セグメント2"など）。
* "NextProcessingDate"フィールドがワークフローリソースに追加されます。このフィールドはREST API呼び出しを通じてのみ表示されるので、次の処理日のワークフローを視覚化できます。
* 現在、"sourceId"フィールドがトラッキングログリソース（nms:trackingLogを参照）。
* 「合計開封数」および「合計クリック数」の値を、ワークフローを介してフラットファイルでエクスポートできるようになりました。（CAR-24186）
* プロファイルの「英語-"のリストで「英語-デンマーク語」が利用できるようになりました。（CAR-23728）
* 追加データ（targetData）リンクでセグメント化アクティビティを使用する場合、ワークフロー外でデータが利用できないことを通知するメッセージが表示されるようになりました。このメッセージは、セグメントアクティビティから「カウント」または「プレビュー」ボタンをクリックすると表示されます。（CAR-23651）
* ワークフローで使用されるディスク容量を最適化するために、以下の機能が強化されました。（CAR-21979）:「ファイルの読み込み」アクティビティで処理されたファイルが、デフォルトで削除されるようになりました。オプションを使用すると、特定のニーズに合わせることができます。ワークフローが削除されると、その専用フォルダーはサーバーディレクトリから自動的に非表示になります。

### Patches {#patches-3}

* eventDateフィールドに適切に入力されていないために、一部の生レポートイベントでトラッキングイベントが関連付けられていなかった問題を修正しました。
* プッシュ通知配信のプレビューウィンドウにパーソナライズされたフィールドが表示されない問題を修正しました。
* プレビューウィンドウでプッシュ通知のメッセージ本文をワードラップできない問題を修正しました。
* メインターゲットが空のときにワークフローから再キュア配信を送信すると発生していた問題を修正しました。
* 既存のスキーマにリンクされている場合、ターゲットマッピングにアクセスできない問題を修正しました。
* ファイルの読み込みアクティビティを介してzipファイルを読み込むと発生する可能性がある問題を修正しました。（CAR-24309）
* 定期的な配信を送信するとPostgreSQLエラーが発生する問題を修正しました。（CAR-23613）
* 空のJSON属性でREST APIリクエストを送信するとエラーメッセージが表示される問題を修正しました。（CAR-23506）
* プロファイルで、「ß」文字の後に文字が大文字になるように設定されていた問題を修正しました。（CAR-23136）
* パーソナライゼーションまたは動的コンテンツブロックの適格性条件で使用された配信を、リンクされたプロファイルのスキーマの使用中に送信する問題を修正しました。（CAR-22751）
* サービスを削除できない問題を修正しました。（CAR-22050）
* テストプロファイルの国または州の値を変更できない問題を修正しました。（CAR-20426）
* Creative Designerが読み込まれない可能性がある問題を修正しました。（CAR-24573）
* 電子メールの件名のパーソナライゼーションフィールドの後に、削除された文字が追加されていた問題を修正しました。（CAR-24113）

## Release 18.4 - April 2018 {#release-18-4---april-2018}

### Patches {#patches-4}

#### Platform {#platform}

* GGPRへのアクセスまたは削除要求が正しく処理されない可能性があるエラーを修正しました。抽出されたデータに次の文字のいずれかが含まれていた場合、まれにこの動作が発生することがありました。&amp;&lt;&gt;"'.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* ログの同期に時間がかかる場合に、KPIの値が誤った値で上書きされる可能性がある問題を修正しました。

#### Workflows {#workflows}

* ワークフローのメモリ管理および最適化されたパフォーマンスが向上しました。

#### Reporting {#reporting}

* KPI共有ワークフローで、最近の6か月ではなく、過去2か月間の配信値を取得するようになりました。外部アカウントのKPIで日付が切り捨てられて表示される問題を修正しました。
* **送信**、 **配信、****および報償の際に特定のメッセージが考慮されない可能性がある問題を修正**&#x200B;しました。
* **配信サマリレポート** で選択した時間範囲が長すぎる場合に発生していたエラーを修正しました。

#### Custom resources {#custom-resources}

* カスタムリソースの準備に失敗するエラーを修正しました。

## Release 18.3 - March 2018 {#release-18-3---march-2018}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> GGPRは、2018年5月25日に実施されるデータ保護要件を調和し、最新化する欧州連合（EU）新しいプライバシー法です。GGPRは、EUに存在するデータ項目のデータを保持するAdobe Campaignのお客様に適用されます。<br /> Adobe Campaignで既に使用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割を含む）に加えて、データプロセッサーとしてこのロールを利用して、特定のGGPRリクエストのデータコントローラーとしての準備を容易にすることができます。<br /> 
    <ul> 
     <li> アクセス権:データの件名を使用すると、データコントローラーによってキャプチャされた個人データのコピーを受信できます（Adobe Campaignに保存されたデータなど）。 </li> 
     <li> 削除から削除:データの件名を使用すると、データコントローラーによって取得された個人データが削除され、Adobe Campaignに保存されているデータを含めることができます。 </li> 
    </ul> For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> Adobe Campaignの新しいクリエイティブデザイナーは、キャンペーンに完全に統合された作成エクスペリエンスを提供し、1行のコードをスクリプト化することなく、パーソナライズされた個別にパーソナライズされたパーソナライズされたパーソナライズされた電子メールを、すばやく簡単に作成できます。強力なドラッグ&amp;ドロップインターフェイスにより、クリエイティブデザイナーは、ユーザーが空白のスレートから開始したり、既存のコンテンツフラグメントやテンプレートを活用したりするかどうかを、電子メールの作成に役立ちます。<br /> 主な機能は次のとおりです。<br /> 
    <ul> 
     <li> ネイティブCreative Cloud統合によって拡張されたドラッグアンドドロップインターフェイスによって、完全にパーソナライズされたレスポンシブな電子メールを視覚的にデザインおよび作成できます </li> 
     <li> 電子メールコンテンツテンプレートを作成して保存し、電子メールの作成を支援するために保存されたテンプレートを活用 </li> 
     <li> コンテンツフラグメントの作成と保存（ヘッダー、フッター、記事など）コンテンツの作成を合理化し、ブランドの一貫性を確保する </li> 
     <li> ドラッグ&amp;ドロップインターフェイスでの作成と、ボタンのクリック時に電子メールのHTML直接編集をシームレスに切り替える </li> 
    </ul> Creative Designer for Emailは英語版でのみ利用できます。<br /> 詳しくは、詳細ドキュメントを <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">参照</a> して <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">ください</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Multilingual Push Deliveries<br /> </td> 
   <td> 電子メールチャネルとSMSチャネルに既に存在するシンプルな多言語インターフェイスが、お客様の好みの言語にかかわらず、プッシュチャネルに追加されました。<br /> この機能は、複数の地域にまたがるプッシュキャンペーンを管理し、ユーザーを対象言語でターゲット設定したい顧客向けのスケーラブルで自動的なソリューションを提供します。テンプレートスプレッドシートを使用してすべての言語のバリエーションを1回のプッシュ配信にアップロードできます。Adobe Campaignは、ユーザーの言語設定に基づいて自動的にセグメント化を行い、ワークフローとレポートを簡素化することによって冗長性を減らすことができます。<br /> 詳しくは、 <a href="../../channels/using/creating-a-multilingual-push-notification.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> すぐに使用できるフィールドに加えて、トランザクションメッセージングでは、メッセージのコンテンツを充実させるためにカスタムリソースを使用できます。<br /> 次に例を示します。<br /> 
    <ul> 
     <li> カスタムフィールドを紐付け条件として使用して、トランザクションメッセージとプロファイルに一致させる </li> 
     <li> 完全プロファイル、サービス、リンクされたデータを活用して、トランザクションメッセージをさらにパーソナライズ </li> 
    </ul> For more information, refer to the <a href="../../administration/using/configuring-transactional-messaging.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### Platform {#platform-1}

* 5000件を超えるレコードをリストからエクスポートできない問題を修正しました。
* パーソナライゼーションフィールドで名前を付けたファイルにデータをエクスポートする際の問題を修正しました。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* パーツのサイズがバイトではなく文字で計算されるため、マルチパートSMSが切り詰められる問題を修正しました。
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. プロバイダーから受信したSR（ステータスレポート）から直接再計算されます。
* 配信スケジューラーのカレンダーウィジェットの問題を修正しました。
* 送信された配信で、ターゲットを2回開くと表示される問題を修正しました。
* 遅延送信日の電子メールテンプレートを作成すると、開始日をリクエストするエラーメッセージが表示される問題を修正しました。
* 配信のコンテンツを編集する際に画像レンダリングの問題が発生する可能性がある問題を修正しました。
* キャンペーンを複製する際の校正の問題を修正しました。
* ワークフローに配信を追加した後、ナビゲーションバーを経由してキャンペーンテンプレートにアクセスするときにエラーメッセージが表示される問題を修正しました。
* A/Bテスト電子メールの推奨結果が自動的に選択され、電子メールが送信されないという問題を修正しました。This behavior could occur if the delivery was in **[!UICONTROL retryInProgress]** state.
* A/Bテスト電子メールのパラメーターを再度開くとエラーメッセージが表示される可能性がある問題を修正しました。

#### Audiences &amp; queries {#audiences-e-queries}

* Adobe Campaign ClassicからStandardに複製された受信者に関するデータにアクセスできず、クエリを設定できなかった問題を修正しました。
* **「カウント」ボタン** または「 **プレビュー** 」ボタンを使用した後、クエリエディターでフィルタータイプフィールドを使用すると発生していた問題を修正しました。

#### Workflows {#workflows-1}

* **請求** ワークフローは、配信準備遅延を改善するために最適化されています。
* 定期的な配信アクティビティを使用すると、アウトバウンドのトランジションに人口データが表示されない問題を修正しました。
* **更新データ** アクティビティの後に、拒否レコードがトランジションに表示されない問題を修正しました。
* **DeliverabilityUpdate** の技術ワークフローが失敗する可能性がある問題を修正しました。

#### Integrations {#integrations}

* 国際文字がAdobe Analyticsに正しく送信されない問題を修正しました。
* Experience Cloudアセットライブラリからメッセージをメッセージに挿入しようとすると、アセットが読み込まれるようになりました。
* 場合によってアセット選択ウィンドウが閉じることがない問題を修正しました。
* データソースの詳細から、関連ワークフローに直接アクセスしてワークフローの状態を確認できるようになりました。
* トリガーイベントを定義または編集するときに、直接トリガースキーマを更新できるようになりました。この変更により、トリガーの公開を取り消して別のものを作成する必要がなくなりました。

#### Transactional messages {#transactional-messages}

* 配信リソースが拡張されたときのトランザクションメッセージテンプレートのエラーを修正しました。
* トランザクションメッセージを削除できるようになりました。

## Release 18.2 - February 2018 {#release-18-2---february-2018}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> <strong>購読サービス</strong> のワークフローアクティビティで、複数のサービスのプロファイルリストをサブスクライブまたはサブスクライブ解除できるようになりました。ワークフローで、プロファイルを含むファイルと、各プロファイル、操作タイプおよびサービスを読み込みます。<strong>購読サービス</strong> アクティビティでは、この情報を使用し、すべてのプロファイルの購読および購読解除を一度に動的に処理できます。<br /> 詳しくは、 <a href="../../automating/using/subscription-services.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> The new <span class="uicontrol">Enrichment</span> workflow activity allows you to leverage the inbound transitions and complete the output transition with additional data. プロファイルをターゲット設定する場合、拡張アクティビティでは、データベースに保存されていない追加のデータ（例えば、インポートされたファイルからのアクセス）によってプロファイル情報を拡張できます。<br /> 詳しくは、 <a href="../../automating/using/enrichment.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### Platform {#platform-2}

* Adobe Campaignのインターフェイスの上部バーが新しいExperience Cloudメニューで更新されました。
* Fixed an issue which prevented the link to **[!UICONTROL Offers]** from being displayed in the solution dropdown list.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* 配信準備段階が強化され、パフォーマンスが向上しました。
* 一部のiche状況でトラッキングログが破損する可能性がある問題を修正しました。
* 配信準備と確認の間に連絡先日が変更されたときに発生していた連絡先の更新の問題を修正しました。現在は、準備の後に連絡先日を変更する場合、送信を確認する前に、配信を再度準備する必要があります。See the [detailed documentation](../../sending/using/preparing-the-send.md).

#### Push notifications {#push-notifications}

* iOSプッシュ通知で一部のパーソナライゼーションフィールドが動作しないエラーを修正しました。
* プッシュ通知ダッシュボードでクリック率とオープン率が0%と表示されるエラーを修正しました。

#### Reports {#reports}

* 一部のブラウザーでレポートリストが空として表示されるエラーを修正しました。
* Fixed an error that occurred in the **[!UICONTROL Report sharing]** technical workflow just before its expiration limit was reached.

#### Workflows {#workflows-2}

* ドラッグ&amp;ドロップ後にアクティビティにアクセスできない問題を修正しました。
* Fixed an issue that could cause the order of output transitions of a **[!UICONTROL Segmentation]** activity to change in some situations.
* 列挙タイプフィールドが含まれていて、ワークフローから以前保存されていたオーディエンスを読み取る際に発生するエラーを修正しました
* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain checked even after unchecking it when defining the scheduling properties of a delivery created in a workflow.
* Automatic removal of duplicate rows (DISTINCT clause) can now be disabled in **[!UICONTROL Query]** activities, via a new option located in the **[!UICONTROL Additional data]** tab. パフォーマンス上の理由から多数の（100を超える）追加要素を定義する場合、このオプションを無効にすることをお勧めします。

#### Integrations {#integrations-1}

* **[!UICONTROL Data sources]** 設定画面が改善されました。

### Known issues {#known-issues}

表示に問題があるので、Internet Explorerバージョン11を使用しないことをお勧めします。

状況によっては、キャンペーンインターフェイスからコンテキストヘルプリンクを使用する場合に発生することがあります。18.3で修正されます。

## Release 18.1 - January 2018 {#release-18-1---january-2018}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> 疲労管理のレポート作成は、送信前に指定した日付範囲内の電子メール、プッシュ、SMSおよびダイレクトメールチャネルの配信に影響する、柔軟性の高い専用のレポートです。競合するすべてのキャンペーンを単一のビューで迅速に表示できるようになり、マーケティング担当者は、疲労ルールをより効果的に設定し、コミュニケーションを優先順位付けすることによってマーケティングキャンペーンを計画できます。<br /> 詳しくは、 <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Report sharing<br /> </td> 
   <td> レポート共有を使用すると、レポートをAdobe Campaignのユーザーと共有して、自動的に定期的に電子メールで添付できます。定期的なレポートを受信するユーザーは、各電子メールの専用リンクを介してこれらの情報を登録解除できます。<br /> 詳しくは、 <a href="../../reporting/using/reporting-interface.md#share-tab">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> プッシュメッセージプレビュー-プッシュ通知コンテンツエディタ内からiOSおよびAndroidデバイスでプッシュ通知をプレビューして、テストまたは配信の実行前に受信者が表示する内容を正確に確認できます。<br /> 詳しくは、 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細なドキュメント</a>を参照してください。<br /> コンテンツ利用可能-アプリを長期間開かない場合、そのデータは古くなります。これにより、ユーザーが最後にアプリを開くときにデータを更新または置換する必要があり、アプリの使用が遅延する可能性があります。コンテンツのサポートを追加すると、Adobe Campaignユーザーはアプリを起動して、プッシュ通知の配信時にバックグラウンドでデータを更新し、一貫性を高め、ユーザーのアプリ内エクスペリエンスを制御できます。<br /> 可変コンテンツ-可変コンテンツのサポートを追加したAdobe Campaignユーザーは、モバイルアプリの拡張機能を活用して、Adobe Campaignから送信されたプッシュ通知のコンテンツまたは提示方法をさらに変更できます。For example, users can leverage Mutable Content to: <br /> 
    <ul> 
     <li> 暗号化された形式で配信されたデータの復号化 </li> 
     <li> 画像またはその他のメディアファイルをダウンロードし、通知に添付ファイルとして追加 </li> 
     <li> 通知の本文またはタイトルのテキストの変更 </li> 
     <li> 通知へのスレッド識別子の追加 </li> 
    </ul> For more information on Content Available and Mutable Content, refer to the <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detailed documentation</a>.<br /><strong>警告:</strong> これらのプッシュ通知の更新により、ユーザーはモバイルアプリケーションをアップグレードする必要があります。Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Time-zone optimized deliveries<br /> </td> 
   <td> すべての受信者のタイムゾーンにある特定の日時に配信されるように定期的な電子メール、SMSおよびプッシュ通知をスケジュールし、複数の配信を設定せずに、適切なタイミングでメッセージを配信するようにします。<br /> 詳しくは、 <a href="../../automating/using/scheduler.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal activity triggering<br /> </td> 
   <td> Adobe Campaign Standard APIからワークフローのシグナルアクティビティを直接トリガーできるようになりました。<br /> 詳しくは、 <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">詳細なドキュメント</a> を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### Platform {#platform-3}

* プロファイル検索が最適化され、パフォーマンスが向上しました。
* デフォルトのセキュリティグループの内部識別子が、標準ユーザーの読み取り専用モードになりました。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-3}

* 配信のコンテンツに顔文字を挿入すると発生する表示の問題を修正しました。
* 配信がまだエディションにある場合に、ユーザーがログの送信にアクセスできる問題を修正しました。
* **[!UICONTROL Scheduler]** アクティビティで、受信者のタイムゾーンに応じて配信を送信できるようになりました。
* SMS: The option **[!UICONTROL Store incoming MO]** in the database has been added to external accounts. When checked, all incoming SMS will be stored into the **inSMS** table.
* SMS:現在、サービスはトランザクションテンプレートではなくイベントに添付されています。
* SMS:デフォルトのSMTP接続タイムアウトが30秒に短縮されました。

#### Push notifications {#push-notifications-1}

* プッシュ通知の配信を停止できないエラーを修正しました。
* プッシュ通知を使用してアプリケーションを起動するためのプッシュ通知のアドバンスオプションにオプションが追加されました。
* プッシュ通知プレビュービデオの一時停止ボタンを追加しました。
* iPhone、Android、タブレットなどの様々なデバイスでプッシュ通知プレビューを使用できるようになりました。

   すべてのチャネル

#### Reports {#reports-1}

* 100%を超えるレートが表示されるエラーを修正しました。
* ユーザーがCSVでレポートをダウンロードできない問題を修正しました。
* Added a new **[!UICONTROL Report]** item in the homepage.

#### Workflows {#workflows-3}

* クエリで追加のデータを使用し、スペースを含むエイリアスを追加するとエラーメッセージが表示される問題を修正しました。英数字以外の文字が"_"に置き換えられました。
* KPIの計算がデフォルトで停止することがあるという問題を修正。

#### Profiles and audiences {#profiles-and-audiences}

* オーディエンスのクエリで複数のフィルターを追加すると発生するエラーを修正しました。
* プロファイルの写真を変更すると発生していた表示の問題を修正しました。
* クエリの母集団をカウントした後、正確な結果番号を表示するツールチップが追加されました。
* ユーザーがオーディエンスを選択したり、オーディエンスピッカーウィンドウを閉じたりできない問題を修正しました。
* 式エディターで使用可能な関数のリストが更新されました。**formatCurrency関数** と **ConvertCurrency** 関数は削除されました。

