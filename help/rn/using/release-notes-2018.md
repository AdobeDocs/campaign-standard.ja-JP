---
title: リリースノート 2018
description: このページでは、Adobe Campaign Standard の 2018年の全リリースを紹介します。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5386'
ht-degree: 7%

---

# リリースノート 2018{#release-notes}

## リリース 18.9 - 2018 年 9 月 {#release-18-9---september-2018}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> 機能<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> アプリ内メッセージ（ベータ版）<br /> </td> 
   <td> アプリ内メッセージを使用すると、コンテキストインタラクションを提供し、プッシュ通知をオプトアウトした可能性のあるユーザーにリーチできるようにすることで、モバイルアプリユーザーをより効果的に惹きつけることができます。 プッシュ通知と組み合わせてアプリ内メッセージを使用し、高度にパーソナライズされた、関連性の高いエクスペリエンスを作成します。 これにより、アプリユーザーのコンバージョンと定着が向上します。<br /> 詳しくは、 <a href="../../channels/using/about-in-app-messaging.md">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> モバイルアプリ用のAdobeLaunch 統合（ベータ版）<br /> </td> 
   <td> Adobe CampaignとのAdobeLaunch の統合により、Mobile SDK V5 を使用した Campaign での Mobile App Property の有効化がシンプルになり、プロセスが自動化されました。<br /> 詳しくは、 <a href="https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改善点**

* Adobe Campaign Standardは、Amazon S3 API のバージョン 4 をサポートするようになりました。

**その他の変更**

* broadLog で、接続の最大数と 1 時間あたりのメッセージの最大数が区別されるようになりました。限界値に達した場合、スループットが制限される理由を判別できます。これまでは、どちらの場合にも同じメッセージ（「割り当てに達しました」）が表示されていました。
* Campaign でモバイルアプリケーションを設定する際、iOSの証明書と Android サーバーキーが正常にアップロードされたかどうかと、その有効期限をユーザーが知ることができるようになりました。

  詳しくは、を使用してモバイルアプリケーションを設定する方法に関する詳細なドキュメントを参照してください。 [SDK V4](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) および [SDK V5](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html).

* キャンペーンプロパティの定義時にモバイルアプリを選択して、特定のモバイルアプリでユーザーをターゲット設定します。 この機能は、プッシュメッセージチャネルとアプリ内メッセージチャネルの両方に使用されます。

  詳しくは、[詳細なドキュメント](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)を参照してください。

* Creative Designer インターフェイスを使用してコンテンツブロックを選択する場合、リストのすべてのコンテンツブロックが読み込まれ、表示されるようになりました。 （CAMP-27311）

  詳しくは、 [詳細なドキュメント](../../designing/using/personalization.md#adding-a-content-block).

**パッチ**

* トランザクション E メールの E メールダッシュボードと E メールの概要レポートで、ログ数に矛盾が生じる問題を修正しました。 (CAMP-28237)
* ファイル転送アクティビティを通じてファイルを読み込む際にエラーメッセージが表示される可能性があるワークフローの問題を修正しました。 （CAMP-27435）
* 25 を超えるサービスを含むランディングページで、フォーム内のサービスがランダムに選択解除される問題を修正しました。 （CAMP-26572）
* ワークフローで、ファイル転送アクティビティを使用する際に、SFTP URL を使用して外部アカウントを設定できない問題を修正しました。 （CAMP-26475）
* サービスの概要レポートが更新されない問題を修正しました。 （CAMP-26301）
* エンリッチメントアクティビティを使用する際のワークフローで、カスタムフィールドに正しい日付が表示されない問題を修正しました。 （CAMP-26242）
* ファイルのインポートによってインポートした場合に、サービスの購読登録日が更新されない問題を修正しました。
* ファイルの読み込みアクティビティで、ワークフローがファイルを読み込めないエラーを修正しました (CAMP-27068)。
* サービスの概要レポートで、間違った購読数が表示されていた問題を修正しました (CAMP-25587)。
* Adobe AnalyticsとAdobe Campaignのレポートでデータに相違が生じる問題を修正しました。 （CAMP-25393）
* 制限付きアクセスユーザーがログインできない可能性がある問題を修正しました。 （CAMP-27381）
* クリエイティブデザイナーで E メールを編集する際に、Adobe Experience Managerコンテンツのリストが表示されない場合がある問題を修正しました。 （CAMP-27181）
* クリエイティブデザイナーが開かず、エラーが発生する可能性がある問題を修正しました。 （CAMP-27304）
* Internet Explorer 11 を使用している場合に、Creative Designer でドラッグ&amp;ドロップが正しく機能しない問題を修正しました。
* カメラからアップロードされた画像や、縦長モードで撮影された画像が、不要な回転位置に表示される問題を修正しました。
* クリエイティブデザイナーでクエリエディターインターフェイスを使用すると、選択情報が不明瞭に表示される問題を修正しました。
* Creative Designer でクエリエディターインターフェイスを使用する際に、要素を正しく複製できない問題を修正しました。
* 自動返信を通じて配信を停止していた場合でブロックリストに加えるも、上の受信者に SMS メッセージが配信され続けていた問題を修正しました。 （CAMP-27128）
* エラーが表示されず、 **データベースのクリーンアップ** ワークフローが失敗しました。 （CAMP-26876）
* プッシュ通知定義のカスタムフィールドを削除できない可能性がある問題を修正しました。 （CAMP-25588）

## リリース 18.7 - 2018 年 7 月 {#release-18-7---july-2018}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> 機能<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Android プッシュ通知用の高優先度フラグ<br /> </td> 
   <td> Android 用の高優先度フラグ — スリープ中のデバイスが起動し、一部の限られた処理を実行する原因となる Android アプリに対して、高優先度のプッシュ通知を配信できるようにします。 デフォルトの優先度は「標準」で、メッセージの配信がバッテリを節約するのを遅らせる場合があります。 <br /> 詳しくは、 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> モバイルアプリ購読者向けのタイポロジフィルター<br /> </td> 
   <td> タイポロジフィルターでの購読をサポート — タイポロジルールのフィルタリング条件を指定する場合、プロファイルの有無に関わらず、フィルタリングディメンションとターゲティングディメンションとしてアプリケーション購読を選択できます。 <br /> 詳しくは、 <a href="../../sending/using/about-typology-rules.md">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> メッセージの準備中に URL からのコンテンツのインポートを自動化<br /> </td> 
   <td> 準備段階で URL から E メールコンテンツをインポートできるようになりました。 繰り返し E メール配信の場合、最新のHTMLコンテンツは、E メールが送信された時点でコンテンツが常に最新であることを確認するメッセージが準備されるたびに取得されます。 また、この機能を使用すると、コンテンツがまだ準備できていない場合でも、URL からのコンテンツを使用してスケジュールされた配信を作成できます。<br /> 詳しくは、 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> キャンペーンリリース通知メッセージ<br /> </td> 
   <td> インスタンスを新しいバージョンにアップグレードした後にユーザーがログインしたときに、ポップアップメッセージが表示されるようになりました。 メッセージには、バージョン番号が示され、リリースノートへのリンクが含まれています。 次のリリースまでメッセージを非表示にするよう選択できます。 <br /> </td> 
  </tr> 
  <tr> 
   <td> ユーザー管理<br /> </td> 
   <td> 新しいCampaign Standardインスタンスと、地理的単位が作成されていない既存のインスタンスで、地理的単位機能が 18.7 リリース以降で使用できなくなりました。<br /> 詳しくは、 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=ja">ページ</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改善点**

* Adobe CampaignとAdobe Targetの統合で、Target の [権限](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=ja) 機能。 E メールにAdobe Targetからの動的画像を含める場合、Target プロパティ（at_property コード）を指定できるようになりました。
* プロファイルリソースに対する独自のコピーリンクを持つカスタムリソースは、GDPR プライバシーのアクセス要求および削除要求で考慮されるようになりました。 基数が 1 つのシンプルリンクと基数コレクションリンクが N 個の場合、カスタムリソースで「ターゲットレコードを削除/複製すると、リンクで参照されたレコードが削除/複製されます」を選択する必要があります。 基数が 0 または 1 の場合は、「レコードを削除/複製すると、リンクで参照されるターゲットレコードが削除または複製されます」を選択します。

**その他の変更**

* タイムアウトエラーを回避するため、レポート共有のタイムアウトが 1 分から 4 分に増加しました。
* E メールのコンテンツを編集すると、新しいクリエイティブデザイナーがデフォルトで開きます。 必要に応じて、変更を保存した後でいつでもデフォルトコンテンツエディターに戻ることができます。 詳しくは、 [詳細なドキュメント](../../designing/using/designing-content-in-adobe-campaign.md).
* クリエイティブデザイナーで、新しいコンテンツコンポーネントを E メール（カルーセル）に追加できるようになりました。 詳しくは、 [詳細なドキュメント](../../designing/using/designing-from-scratch.md#about-content-components).
* トランザクションメッセージのホットクリックレポートで、 **プロファイルを変更** 」ボタンをクリックすると、トランザクションメッセージ用に定義したイベントにリンクされたテストプロファイルのみが表示されます。

**パッチ**

* byEmail クエリフィルターで結果を返せなかった問題を修正しました。 （CAMP-23420）
* 管理者に制限された特定の機能や画面に標準ユーザーがアクセスできる問題を修正しました (/rest/head/&#42; エンドポイント、トランザクションメッセージング画面、プロファイルおよびオーディエンスの読み込み画面 )。
* 名前が数字で始まる場合に GDPR プライバシー削除要求を処理できない問題を修正しました。
* 「オーディエンスを保存」アクティビティで、Adobe Experience Cloudのアプリケーション購読者を共有できないエラーを修正しました。
* ファイル名に空白のスペースが含まれている場合に発生する可能性がある「ファイル転送」アクティビティの問題を修正しました。 （CAMP-25936）
* セッションの期限が切れた後に再接続ボタンを使用した場合に発生する可能性がある問題を修正しました。 （CAMP-25560）
* 疲労ルールに関連付けられたタイムゾーンの最適化を使用して配信を送信すると除外が発生する可能性がある問題を修正しました。 （CAMP-25425）
* API GDPR 機能の使用時に、0-1 タイプのリンクを含むデータの削除が妨げられる可能性がある問題を修正しました。
* 疲労タイポロジルールのエディションをキャンセルするとエラーメッセージが表示される問題を修正しました。
* 配信コンテンツを編集後にプレビューする際に発生する可能性がある問題を修正しました。
* 「解凍」オプションの使用中に CSV zip ファイルを処理する際に発生する可能性がある問題を修正しました。
* クリエイティブデザイナーで、スタイルが組み込まれている一部のテキストをリンクに変更したり、そのリンクを編集したりすると、不要な色のフォントや書式が発生する問題を修正しました。 （CAMP-26001）
* 動的コンテンツを含む配信で、ホットクリックレポートで各条件の割合が表示されない問題を修正しました。 以前は、デフォルトバリアントのクリック数のみが表示されていました。

## リリース 18.6 - 2018 年 6 月 {#release-18-6---june-2018}

**改善点**

* The **[!UICONTROL History]** API がAdobe.IO に追加されました。 プロファイルのマーケティング履歴に関する情報（タッチポイント数、送信された配信数、ミラーページの URL など）にアクセスできます。 詳しくは、 [専用の使用例](../../api/using/interacting-with-marketing-history.md) .
* The **[!UICONTROL Database cleanup]** データベースバックアップのパフォーマンスを向上させるために、テクニカルワークフローが最適化されました。
* E メール用のクリエイティブデザイナーが、フランス語とドイツ語でも利用できるようになりました。

**その他の変更**

* A **[!UICONTROL Compute stats]** ボタンが **[!UICONTROL Deployment]** 送信された配信のウィンドウ。 この関数を使用すると、例えば、送信の結果が更新に時間がかかりすぎたり、考慮されていなかったりした場合に、最新の KPI を取得できます。 詳しくは、[この節](../../sending/using/confirming-the-send.md)を参照してください。
* Adobe Analytics の **配信品質の更新** 標準のテクニカルワークフローで、機能管理者は、 **ルールを更新** javascript アクティビティ。 デフォルトでは、フィールドの値は 0 に設定されています。これは、すべてのエラーが無視されることを意味します。
* ユニットアクセス制限条件の管理時に生成される SQL を最適化しました。
* The **[!UICONTROL Update]** 「 」アクティビティで、購読に関連するデータ（nms:appSubscriptionRcp テーブル）の追加、更新、削除をおこなえるようになりました。
* The **[!UICONTROL Update delivery execution]** パフォーマンスを最適化するために、テクニカルワークフローは 2 つのワークフローに分かれています。 - **[!UICONTROL Update delivery execution]**：配信のトラッキングを更新します。 デフォルトでは、10 分ごとに実行されます。 **[!UICONTROL Update delivery indicators]**：配信の KPI を更新します。デフォルトでは、1 時間ごとに開始されます。 テクニカルワークフローについて詳しくは、この [セクション](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 配信がメッセージを送信する際に、 **[!UICONTROL Deployment]** セクションに 2 つの値を含めることができるようになりました。 **[!UICONTROL Sending]**：メッセージは送信中です。 **[!UICONTROL Sending (retry)]**：再試行パスが進行中です。
* を持つユーザー **[!UICONTROL Delivery preparation]** ロールが配達確認を送信できるようになりました。 （CAMP-24313）
* The **TLS over SMPP を有効にする** オプションが **SMPP を介した SMS ルーティング** 外部アカウント。 詳しくは、この[節](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)を参照してください。

**パッチ**

* Adobe Targetから動的画像を含めると E メールが送信されない可能性がある問題を修正しました (CAMP-24848)。
* の問題を修正しました。 **[!UICONTROL Privacy Access/Delete Request]** いずれかのリクエストが失敗した場合に完了しなかったテクニカルワークフロー。
* Privacy Core サービスが Campaign からリクエストステータスの更新を受け取れない問題を修正しました。
* 次の問題を修正しました： **[!UICONTROL Import shared audience]** 正常に動作しなかったテクニカルワークフロー (CAMP-25465)。
* Campaign のプライバシーリクエストがコアPrivacy Serviceで完了とマークされない問題を修正しました。
* Adobe IDが長すぎる場合に、特定のユーザーが IMS 認証を通じてCampaign Standardにログインできない可能性がある問題を修正しました。 （CAMP-24095）
* コンテンツモジュールの削除時に発生する可能性があるクリエイティブデザイナーの問題を修正しました。 （CAMP-25242）
* データベースにプロファイルがない購読者に対して、プッシュ通知の疲労ルールを使用する際の問題を修正しました。 （CAMP-25344）
* 配信の除外ログにアクセスする際にエラーメッセージが表示される可能性がある問題を修正しました。 （CAMP-24724）
* 拡張送信ログを含むインスタンスで配達確認が準備されない問題を修正しました。
* を使用してカスタムリソースを公開する際に発生する可能性がある 2 つの問題を修正しました。 **[!UICONTROL Sending log]** 拡張機能が有効化されました。
* 繰り返し配信で配信期間が考慮されない場合がある問題を修正しました。
* でデータを並べ替える際に発生する可能性がある問題を修正しました。 **[!UICONTROL Client data]** メニュー（100,000 件を超えるレコードを持つカスタムリソース用） （CAMP-24308）
* 動的レポートで検索機能を使用する際に、カスタムプロファイルのディメンションが考慮されなかった問題を修正しました。
* 動的レポートのアカウントレベルでの国際データの表示の問題を修正しました。
* 購読または購読解除の確認メッセージを表示せずに、サービスを作成できるようになりました。

## リリース 18.5 - 2018 年 5 月 {#release-18-5---may-2018}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> 機能<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR：コアサービスの統合<br /> </td> 
   <td> Privacy Core Service 統合を使用すると、1 回の JSON API 呼び出しで、複数のソリューションのコンテキストで GDPR リクエストを自動化できます。 <br /> Privacy Core Service からすべてのExperience Cloudソリューションにプッシュされた GDPR 要求は、Campaign で自動的に処理されるようになりました。 <br /> 詳しくは、 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> プッシュの改善 — 詳細な配信のフィードバック<br /> </td> 
   <td> Adobe Campaignは、MCPNS を介してプロバイダー (APNS/GCM) からプッシュメッセージに関する詳細なフィードバック（ログと除外ログの送信）を受け取る機能を提供するようになりました。<br /> 詳しくは、 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ログ拡張機能<br /> </td> 
   <td> 配信ログ拡張機能を使用すると、送信ログを、ワークフローから取得したプロファイルデータとセグメントコードで拡張できます。 この情報は、動的レポートで使用でき、配信の送信時に、一部の情報のスナップショットを保持できます。<br /> その他にも 2 つの使用例があります。<br /> 
    <ul> 
     <li> 「frozen」データを含む拡張 broadlog の書き出し：（ワークフローエンジンからの）セグメントコードが「A」に等しいすべてのプロファイルをマーケティング担当者として書き出します。 </li> 
     <li> 「凍結」データに対するセグメント化：マーケティング担当者として、 <strong>再ターゲット化</strong> 前回の送信以降に 1000 ロイヤルティポイントを獲得した、またはセグメントコードが「A」に等しかったすべてのプロファイル。 </li> 
    </ul> 詳しくは、<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細ドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> カスタムプロファイルデータを使用した動的レポート<br /> </td> 
   <td> この機能を使用すると、プロファイルリソース拡張中に作成されたカスタムプロファイルデータに基づいてレポートを作成および管理できます。 ロイヤルティプログラム、優先チャネルなどのプロファイル属性別にレポートを分類できます。<br /> 詳しくは、 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改善点**

* アプリケーションの全体的なメモリと CPU 使用率が向上しました

**その他の変更**

* 「オーディエンスの閲覧」ワークフローアクティビティは、Experience Cloudのオーディエンスを読み取れるようになりました。 以前は、このアクティビティは、クエリオーディエンスとリストオーディエンスのみを読み取ることができました。 詳しくは、 [詳細なドキュメント](../../automating/using/read-audience.md). （CAMP-23623）
* 既定の共有データソースの識別子は読み取り専用モードになり、変更できなくなりました。 この識別子を変更すると、オーディエンスをExperience Cloudと共有する際に問題が発生する可能性があります。
* Audience Manager からのオーディエンスのインポートが分割ファイルで正しく機能するようになりました。これまでは、importSharedAudience テクニカルワークフローによってセグメントの最後のファイルのみがインポートされていました。
* AWS S3 外部アカウントで、地域とバージョン 4 の認証メカニズムがサポートされるようになりました。 [詳細ドキュメント](../../administration/using/external-accounts.md)を参照してください。
* アセット選択ウィンドウの読み込みが高速化され、アセットを選択した後、問題なくウィンドウを終了できるようになりました。
* テクニカルワークフローのプロパティと構造を、管理権限を持ち、「すべて」の組織単位と地理的単位に属するユーザーが変更できるようになりました。
* 新しいセグメントを作成する際の Segmentation アクティビティインターフェイスが強化されました。制限を追加した直後に「制限」タブが表示されるようになりました。 新しいセグメントの名前が増分されました（「Segment 1」、「Segment 2」など）。
* 「nextProcessingDate」フィールドがワークフローリソースに追加されます。 このフィールドは REST API 呼び出し経由でのみ表示され、次の処理日にワークフローを視覚化できます。
* 「sourceId」フィールドがトラッキングログリソース (nms:trackingLog) に公開されるようになりました。
* 「合計開封数」と「合計クリック数」の値を、ワークフローを介してフラットファイルにエクスポートできるようになりました。 （CAMP-24186）
* プロファイルの「優先言語」リストで「English - Danmark」を利用できるようになりました。 （CAMP-23728）
* 「追加データ (targetData) 」リンクを含む Segmentation アクティビティを使用する場合、ワークフロー外でデータが使用できないことを示すメッセージが表示されるようになりました。 このメッセージは、Segmentation アクティビティで「カウント」ボタンまたは「プレビュー」ボタンをクリックすると表示されます。 （CAMP-23651）
* ワークフローで使用されるディスク領域を最適化する機能が強化されました。(CAMP-21979):「ファイルの読み込み」アクティビティで処理されるファイルは、デフォルトで削除されるようになりました。 オプションを使用すると、特定のニーズに合わせてこれらを保持できます。 ワークフローを削除すると、専用フォルダーはサーバーディレクトリから自動的に抑制されます。

**パッチ**

* 一部の生レポートイベントで、eventDate フィールドに適切な値が入力されていなかったので、トラッキングイベントが関連付けられていなかった問題を修正しました。
* プッシュ通知配信のプレビューウィンドウにパーソナライズされたフィールドが表示されなかった問題を修正しました。
* プレビューウィンドウで、プッシュ通知のメッセージ本文をテキストでワードラップできない問題を修正しました。
* ワークフローから繰り返し配信を送信する際に、メインターゲットが空の場合に発生する問題を修正しました。
* 存在しないスキーマにリンクされている場合にターゲットマッピングにアクセスできない問題を修正しました。
* 「ファイルの読み込み」アクティビティで zip ファイルを読み込む際に発生する可能性がある問題を修正しました。 （CAMP-24309）
* 繰り返し配信の送信時に PostgreSQL エラーが発生する問題を修正しました。 （CAMP-23613）
* 空の JSON 属性を持つ REST API リクエストを送信するとエラーメッセージが表示される問題を修正しました。 （CAMP-23506）
* が「ß」文字の後の文字を大文字に設定するプロファイルの問題を修正しました。 （CAMP-23136）
* プロファイルのリンクされたスキーマの属性を使用する際に、パーソナライゼーションまたは動的コンテンツブロックの実施要件条件で使用された配信を送信する際に発生していた問題を修正しました。 （CAMP-22751）
* サービスを削除できない問題を修正しました。 （CAMP-22050）
* テストプロファイルで国または州の値を変更できなかった問題を修正しました。 （CAMP-20426）
* クリエイティブデザイナーの読み込みを妨げる可能性がある問題を修正しました。 （CAMP-24573）
* E メールの件名のパーソナライゼーションフィールドの後に追加された文字が削除される問題を修正しました。 （CAMP-24113）

## リリース 18.4 - 2018 年 4 月 {#release-18-4---april-2018}

**パッチ**

_Platform_

* が GDPR のアクセス要求または削除要求を正しく処理できない可能性があるエラーを修正しました。 この動作は、抽出したデータに次の文字のいずれかが含まれている場合が稀に見られました。 &amp; &lt; > &quot; &#39;.

_E メール、SMS メッセージおよびダイレクトメール_

* broadlog の同期に 1 時間以上かかった場合に、KPI が誤った値で上書きされる問題を修正しました。

_ワークフロー_

* メモリ管理の改善と、ワークフローでのパフォーマンスの最適化。

_レポート_

* KPI 共有ワークフローで、過去 6 か月間ではなく、過去 2 か月間の配信値が取得されるようになりました。 KPI 共有外部アカウントで日付が切り捨てられる問題を修正しました。
* 特定のメッセージが **送信済み**, **配信済み** および **バウンス**&#x200B;指標。
* 選択された時間範囲 ( **配信の概要レポート** が長すぎました。

_カスタムリソース_

* カスタムリソースの準備に失敗するエラーを修正しました。

## リリース 18.3 - 2018 年 3 月 {#release-18-3---march-2018}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> 機能<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> EU 一般データ保護規則（GDPR）<br /> </td> 
   <td> GDPR は 2018 年 5 月 25 日より欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化させることを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。<br /> Adobe Campaignでは既にプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）を提供していますが、この機会にデータ処理者として、特定の GDPR 要求に対するデータ管理者としての準備を容易にする追加機能を導入しました。<br /> 
    <ul> 
     <li> アクセス権限：データ主体は、データ管理者により取得された自分の個人データのコピーを受け取ることができます。これには Adobe Campaign に保存されているデータも含まれている場合があります。 </li> 
     <li> 削除権限：データ主体は、データ管理者により取得された自分の個人データを消去させることができます。これには Adobe Campaign に保存されているデータも含まれている場合があります。 </li> 
    </ul> 詳しくは、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">詳細ドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> E メール用 Creative Designer（ベータ版）<br /> </td> 
   <td> Adobe Campaignの新しい Creative Designer は、Campaign で完全に統合された作成エクスペリエンスを提供し、コードを 1 行も記述することなく、魅力的で個々にパーソナライズされた E メールを容易かつ素早く視覚的に作成できます。 クリエイティブデザイナーは、強力なドラッグ&amp;ドロップインターフェイスを通じて、ユーザーが空白のスレートから開始したり、既存のコンテンツフラグメントやテンプレートを利用したりして、E メール作成を拡大縮小できます。 <br /> 主な機能は次のとおりです。<br /> 
    <ul> 
     <li> ネイティブの統合によって拡張された、ドラッグ&amp;ドロップインターフェイスを通じて、完全にパーソナライズされたレスポンシブな E メールを視覚的にデザインし、作成します。 </li> 
     <li> E メールコンテンツテンプレートを作成して保存し、保存したテンプレートを活用して E メール作成のスケールを調整 </li> 
     <li> コンテンツフラグメント（ヘッダー、フッター、記事など）を作成し、保存すると、 コンテンツの作成を合理化し、ブランドの一貫性を確保する </li> 
     <li> ドラッグ&amp;ドロップインターフェイスでの作成と、ボタンのクリックでの電子メールのHTMLの直接編集をシームレスに切り替えます。 </li> 
    </ul> E メール用クリエイティブデザイナーは英語でのみ使用できます。<br /> 詳しくは、 <a href="../../designing/using/designing-content-in-adobe-campaign.md">詳細なドキュメント</a> これを見て <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">ビデオ</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 多言語プッシュ配信<br /> </td> 
   <td> E メールチャネルと SMS チャネルに既に存在するのと同じシンプルな多言語インターフェイスがプッシュチャネルに追加され、優先言語に関係なく顧客を惹きつけるのに役立ちます。<br /> この機能は、複数の地域にわたるプッシュキャンペーンを管理し、優先言語でユーザーをターゲットにしたいお客様向けに、拡張性と自動化に優れたソリューションを提供します。 すべての言語バリアントを、テンプレート化されたスプレッドシートを使用して 1 回のプッシュ配信に 1 回のクリックでアップロードできます。 その後、Adobe Campaignはユーザーの言語設定に基づいて自動セグメント化を実行し、ワークフローとレポートを簡素化して冗長性を減らすのに役立ちます。<br /> 詳しくは、 <a href="../../channels/using/creating-a-multilingual-push-notification.md">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> トランザクションメッセージでのカスタムリソースの使用<br /> </td> 
   <td> トランザクションメッセージでは、標準のフィールドに加えて、カスタムリソースを使用してメッセージのコンテンツをエンリッチメントできるようになりました。<br /> 例：<br /> 
    <ul> 
     <li> カスタムフィールドを紐付け条件として活用し、トランザクションメッセージをプロファイルに一致させます </li> 
     <li> 完全なプロファイル、サービス、リンクされたデータを活用して、トランザクションメッセージをさらにパーソナライズする </li> 
    </ul> 詳しくは、<a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">詳細ドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**パッチ**

_Platform_

* 5,000 件を超えるレコードをリストからエクスポートできない問題を修正しました。
* パーソナライゼーションフィールドを使用してという名前のファイルにデータを書き出す際の問題を修正しました。

_E メール、SMS メッセージおよびダイレクトメール_

* 部分のサイズがバイトではなく文字で計算されるので、マルチパート SMS が切り捨てられる問題を修正しました。
* オプションが追加され、 **[!UICONTROL Delivered]** または **[!UICONTROL Bounces + Errors]** 配信送信後にリアルタイムで更新される KPI。 これらは、プロバイダーから受け取った SR（ステータスレポート）から直接再計算されます。
* 配信スケジューラーのカレンダーウィジェットの問題を修正しました。
* 送信した配信でターゲットを 2 回目に開く際の表示の問題を修正しました。
* 送信日が遅れた E メールテンプレートを作成する際に、開始日をリクエストするエラーメッセージが表示される問題を修正しました。
* 配信のコンテンツを編集する際に画像レンダリングの問題が発生する問題を修正しました。
* キャンペーンを複製する際の配達確認の問題を修正しました。
* ワークフローに配信を追加した後、ナビゲーションバーからキャンペーンテンプレートにアクセスするとエラーメッセージが表示される問題を修正しました。
* A/B テスト用 E メールの勝者を自動的に選択できず、E メールが送信されない場合がある問題を修正しました。 この動作は、配信が **[!UICONTROL retryInProgress]** 状態。
* A/B テスト用 E メールのパラメーターを再度開くとエラーメッセージが表示される場合がある問題を修正しました。

_オーディエンスとクエリ_

* Adobe Campaign Classicから Standard にレプリケートされた受信者のデータにアクセスできない問題を修正しました。
* クエリエディターでフィルタータイプフィールドを使用した際に、 **カウント** または **プレビュー** ボタン。

_ワークフロー_

* The **請求** 配信準備の遅延を改善するために、ワークフローが最適化されました。
* 繰り返し配信アクティビティを使用する場合に、母集団データがアウトバウンドトランジションに表示されない問題を修正しました。
* レコードの却下が **データを更新** アクティビティ。
* 原因として **deliverabilityUpdate** テクニカルワークフローが失敗しました。

_統合_

* 各国語文字がAdobe Analyticsに正しく送信されない問題を修正しました。
* メッセージにアセットアセットライブラリから画像を挿入しようとした場合、Experience Cloudの読み込みが高速化されました。
* 場合によって、アセット選択ウィンドウが閉じられない可能性がある問題を修正しました。
* データソースの詳細から、関連するワークフローに直接アクセスして、ワークフローの状態を確認できるようになりました。
* イベントイベントを定義または編集する際に、トリガートリガーを直接更新できるようになりました。 この変更により、トリガーを非公開にして別のアセットを作成する必要がなくなりました。

_トランザクションメッセージ_

* 配信リソースが拡張された際のトランザクションメッセージテンプレートのエラーを修正しました。
* トランザクションメッセージを削除できるようになりました。

## リリース 18.2 - 2018 年 2 月 {#release-18-2---february-2018}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> 機能<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 購読 — 複数のサービスに対するプロファイルのリストの購読または購読解除<br /> </td> 
   <td> The <strong>購読サービス</strong> ワークフローアクティビティで、複数のサービスに対するプロファイルのリストを購読または購読解除できるようになりました。 ワークフローで、プロファイルを含むファイルをインポートし、各プロファイルに対して、操作のタイプとサービスをインポートします。 The <strong>購読サービス</strong> アクティビティは、この情報を使用して、すべてのプロファイルの購読と購読解除を一度に動的に処理できます。<br /> 詳しくは、 <a href="../../automating/using/subscription-services.md">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> エンリッチメントアクティビティ — 以前のトランジションに基づくデータのエンリッチメント<br /> </td> 
   <td> 新しい <span class="uicontrol">エンリッチメント</span> 「workflow」アクティビティでは、インバウンドトランジションを利用し、追加のデータで出力トランジションを完了することができます。 プロファイルをターゲット設定する場合、「エンリッチメント」アクティビティを使用すると、データベースに保存されていない（例えば、インポートしたファイルからの）追加データでプロファイル情報をエンリッチメントできます。<br /> 詳しくは、 <a href="../../automating/using/enrichment.md">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**パッチ**

_Platform_

* Adobe Campaignインターフェイスの上部バーが更新され、新しいExperience Cloudメニューが追加されました。
* リンク先の **[!UICONTROL Offers]** を「ソリューション」ドロップダウンリストに表示しないようにします。

_E メール、SMS メッセージおよびダイレクトメール_

* 配信の準備段階が強化され、パフォーマンスが向上しました。
* 一部のニッチ状況でトラッキングログが破損する可能性があるいくつかの問題を修正しました。
* 配信の準備と確認の間にコンタクト日が変更された際に発生していたコンタクト日の更新の問題を修正しました。 これで、準備後にコンタクト日を変更した場合、送信を確定する前に、配信を再度準備する必要があります。 詳しくは、 [詳細なドキュメント](../../sending/using/preparing-the-send.md).

_プッシュ通知_

* 一部のパーソナライゼーションフィールドがiOSのプッシュ通知で機能しないエラーを修正しました。
* プッシュ通知ダッシュボードで、クリック率および開封率が 0%と表示されるエラーを修正しました。

_レポート_

* 一部のブラウザーでレポートリストが空と表示されるエラーを修正しました。
* 次の項目で発生していたエラーを修正しました： **[!UICONTROL Report sharing]** 有効期限に達する直前のテクニカルワークフロー。

_ワークフロー_

* アクティビティをドラッグ&amp;ドロップした後にアクセスできない問題を修正しました。
* の出力トランジションの順序が変わる可能性がある問題を修正しました。 **[!UICONTROL Segmentation]** アクティビティを使用して、特定の状況で変更することができます。
* 列挙タイプのフィールドを含むオーディエンスを読み取る際、以前にワークフローから保存されていたエラーを修正しました。
* 次の問題を修正しました： **[!UICONTROL Request confirmation before sending messages]** ワークフローで作成した配信のスケジュールプロパティを定義する際にオフにした後も、オプションがオンのままになる。
* 重複行（DISTINCT 句）の自動削除を無効にできるようになりました。 **[!UICONTROL Query]** アクティビティ、 **[!UICONTROL Additional data]** タブをクリックします。 パフォーマンス上の理由から、追加の要素を多数（100 を超える）定義する場合は、このオプションを無効にすることをお勧めします。

_統合_

* にいくつかの改善が加えられました。 **[!UICONTROL Data sources]** 設定画面。

_既知の問題_

表示の問題が発生する可能性があるので、Internet Explorer バージョン 11 を使用しないことをお勧めします。

Campaign インターフェイスからのコンテキストヘルプリンクを使用する際に、問題が発生する場合があります。 18.3 で修正されます。

## リリース 18.1 - 2018 年 1 月 {#release-18-1---january-2018}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> 機能<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 疲労管理のレポート<br /> </td> 
   <td> 疲労管理のレポートは、送信前に指定した日付範囲内の E メール、プッシュ、SMS およびダイレクトメールチャネルにわたる配信に対する疲労ルールの影響を表示する、専用の設定可能なレポートです。 競合するすべてのキャンペーンを 1 つのビューですばやく確認できるというインサイトを追加し、マーケターは、疲労ルールをより効果的に設定し、通信を優先することに従ってマーケティングキャンペーンを計画できます。<br /> 詳しくは、 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> レポートの共有<br /> </td> 
   <td> レポートの共有を使用すると、自動定期的なレポートを含む電子メールの添付ファイルとして、Adobe Campaignユーザーとレポートを共有できます。 繰り返しレポートを受け取るユーザーは、各電子メールの専用リンクを使用して、これらの通信から購読解除できます。<br /> 詳しくは、 <a href="../../reporting/using/reporting-interface.md#share-tab">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 新しい機能をプッシュ<br /> </td> 
   <td> プッシュメッセージのプレビュー — iOSおよび Android デバイス上で、プッシュ通知コンテンツエディター内からプッシュ通知をプレビューすると、配信をテストまたは実行する前に、受信者に送られる内容を正確に確認できます。<br /> 詳しくは、 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">詳細なドキュメント</a>.<br /> 使用可能なコンテンツ — 長時間開かれていないアプリのデータは期限切れになる場合があります。 その結果、ユーザーが最終的にアプリを開いた時点でデータを更新または置き換える必要が生じ、アプリの使用に遅延が生じる可能性があります。 利用可能なコンテンツのサポートが追加されたので、Adobe Campaignのユーザーは、プッシュ通知を配信する際にアプリを起動してバックグラウンドでデータを更新でき、ユーザーのアプリ内エクスペリエンスの一貫性と制御を向上できます。<br /> 可変コンテンツ — 可変コンテンツのサポートが追加されたことで、Adobe Campaignのユーザーは、モバイルアプリの拡張機能を活用して、Adobe Campaignから送信されるプッシュ通知のコンテンツや表示をさらに変更できます。 例えば、可変コンテンツを利用して、次のことができます。 <br /> 
    <ul> 
     <li> 暗号化された形式で配信されたデータを復号化する </li> 
     <li> 画像または他のメディアファイルをダウンロードし、添付ファイルとして通知に追加する </li> 
     <li> 通知の本文またはタイトルテキストを変更する </li> 
     <li> 通知にスレッド識別子を追加する </li> 
    </ul> 使用可能なコンテンツと可変コンテンツについて詳しくは、 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">詳細なドキュメント</a>.<br /> <strong>警告：</strong> プッシュ通知に関するこれらの更新では、お客様はモバイルアプリケーションをアップグレードする必要があります。 参照： <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">このテクニカルノート</a> を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> タイムゾーンに最適化された配信<br /> </td> 
   <td> 繰り返し送信の E メール、SMS、プッシュ通知を各受信者のタイムゾーンの特定の日時に配信するようにスケジュールし、複数の配信を設定することなく、適切な時刻にメッセージが配信されるようにします。 <br /> 詳しくは、 <a href="../../automating/using/scheduler.md">詳細なドキュメント</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API シグナルアクティビティのトリガー<br /> </td> 
   <td> ワークフローのシグナルアクティビティをAdobe Campaign Standard API から直接トリガーできるようになりました。<br /> 詳しくは、 <a href="/help/api/using/triggering-a-signal-activity.md">詳細なドキュメント</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**パッチ**

_Platform_

* パフォーマンスを向上させるために、プロファイル検索が最適化されました。
* デフォルトのセキュリティグループの内部識別子は、標準ユーザーに対して読み取り専用モードになりました。

_E メール、SMS メッセージおよびダイレクトメール_

* 配信コンテンツに絵文字を挿入する際に発生していた表示の問題を修正しました。
* 配信がまだ編集中の場合に、ユーザーが送信ログにアクセスできる問題を修正しました。
* The **[!UICONTROL Scheduler]** 「 」アクティビティでは、受信者のタイムゾーンに応じて配信を送信できるようになりました。
* SMS：オプション **[!UICONTROL Store incoming MO]** は、外部アカウントに追加されました。 オンにすると、すべての受信 SMS が **inSMS** 表。
* SMS：サービスがトランザクションテンプレートではなくイベントに添付されるようになりました。
* SMS：デフォルトの SMTP 接続タイムアウトが 30 秒に短縮されました。

_プッシュ通知_

* プッシュ通知の配信を停止できないエラーを修正しました。
* プッシュ通知を含むアプリケーションを起動するためのプッシュ通知の詳細オプションが追加されました。
* プッシュ通知のプレビュービデオ用に一時停止ボタンが追加されました。
* プッシュ通知プレビューを、iPhone、Android、タブレットなどの様々なデバイスで使用できるようになりました。

_レポート_

* 100%を超える率で表示されるエラーを修正しました。
* ユーザーが CSV でレポートをダウンロードできない問題を修正しました。
* 新しい **[!UICONTROL Report]** 」項目がホームページに表示されます。

_ワークフロー_

* クエリで追加データを使用したり、スペースを含むエイリアスを追加したりするとエラーメッセージが表示される問題を修正しました。 英数字以外の文字が「_」に置き換えられました。
* KPI を計算するテクニカルワークフローが、場合によってデフォルトで停止することがある問題を修正しました。

_プロファイルとオーディエンス_

* オーディエンスのクエリに複数のフィルターを追加する際に発生していたエラーを修正しました。
* プロファイルの画像を変更する際に発生していた表示の問題を修正しました。
* クエリの母集団をカウントした後の正確な結果数を示すツールチップを追加しました。
* ユーザーがオーディエンスを選択したり、オーディエンスピッカーウィンドウを閉じたりできなかった問題を修正しました。
* 式エディターで使用できる関数のリストが更新されました。 The **FormatCurrency** および **ConvertCurrency** 関数が削除されました。
