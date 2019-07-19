---
title: リリースノート2015-2016
seo-title: リリースノート2015-2016
description: リリースノート2015-2016
seo-description: このページには、Adobe Campaign Standardの2015および2016リリースがすべて表示されます。
page-status-flag: 常にアクティブ化されていない
uuid: d5a0f6cc-0bad-46cf-8dff-1717fb624f8f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: 参照
topic-tags: campaign- standard- release
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2015-2016{#release-notes}

Adobe Campaign Standardの特定の2015-2016リリースを探します。

各リリースには、新機能およびパッチが含まれています。そのコンテンツを表示するには、リリースをクリックします。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 16.11 - November 2016 {#release-16-11---november-2016}

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
   <td> Deliverability exclusion rules<br /> </td> 
   <td> 暗号化されたグローバル抑制リストが、悪意のあるアクティビティ（特にスパムの使用）のためブラックリストに記載されないように配信品質インスタンスで管理されるようになりました。<br /> 電子メール配信ごとに、2つのデフォルトのタイポロジルールによって、受信者の電子メールアドレスが、このリストに含まれている許可されていないアドレスまたはドメイン名と比較されます。一致がある場合、その受信者はターゲットの母集団から除外されます。<br /> 詳しくは、 <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> General optimization<br /> </td> 
   <td> このアップデートには、クライアントによって発生した問題を修正する多くの変更およびパッチが含まれています。The global platform performances have also been optimized. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### General {#general}

* いくつかのセキュリティ上の問題を修正しました。
* REST APIの空のフィールドや重複したフィールドに関するいくつかの問題を修正しました。
* アプリケーションのホームページからSMSメッセージおよびプッシュ通知を直接作成できるようになりました。

#### Emails and SMS messages {#emails-and-sms-messages}

* ユーザーがコンテンツエディターでzipファイルをアップロードできない問題を修正しました。
* 配達確認を送信後に配達確認を開くことができない問題を修正しました。
* Fixed an issue that led to an error message displaying when accessing the **[!UICONTROL Hot Clicks]** report on an A/B test email.
* **[!UICONTROL Show source]** モードを使用して変更が適用されない問題を修正しました。
* 予測件名行xmlモデルファイルが読み込まれない可能性がある問題を修正しました。
* A new screen dedicated to importing data for the subject line trained model is now available in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* 管理者以外のユーザーが電子メール設定画面で許可されたマスクを編集できない問題を修正しました。

#### Push notifications {#push-notifications}

* **[!UICONTROL Send push on profiles]** テンプレートを使用してプッシュ通知を送信した後、受信者にログおよびイベントログが表示されない問題を修正しました。
* 新しいモバイルアプリケーションが作成されない可能性がある問題を修正しました。

#### Workflows {#workflows}

* **[!UICONTROL Subscription]** アクティビティの使用時に発生していたパフォーマンスの問題を修正しました。
* 内部名にスペースが含まれている場合にワークフローが機能しない問題を修正しました。

#### Integrations {#integrations}

* Fixed an issue that could lead to an error being displayed when using the **Image shared from Adobe Marketing Cloud** option in an email.

#### Custom resources {#custom-resources}

* 拡張APIフィールドの2つのパブリケーション間でAPIのログプレビューが強化されました。
* カスタムリソースを公開前に削除できない問題を修正しました。
* プロファイルが拡張され、識別子キーが動的フィールドに設定されない問題を修正しました。
* カスタムリソースにリンクを追加すると発生する可能性がある問題を修正しました。

## Release 16.10 - October 2016 {#release-16-10---october-2016}

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
   <td> Email predictive subject line<br /> </td> 
   <td> 電子メールの編集時に、新しいオプションを使用すると、異なる件名行を試して、送信前のオープンレートの見積もりを行うことができます。これは、過去の配信データに基づいて、またはお客様の業界固有の定義済みモデルを使用して、独自のモデルをトレーニングすることで実現できます。この機能は、電子メールメッセージおよび英語のコンテンツのみを含むデータベースで使用できます。<br /> 有効化および使用の詳細については、 <a href="../../designing/using/personalizing-the-subject-line-of-an-email.md#predictive-subject-line">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS transactional messaging<br /> </td> 
   <td> SMSチャネルがAdobe Campaignのトランザクションメッセージング機能に追加されました。トランザクションメッセージで2つのチャネルがサポートされるようになりました。電子メールおよびSMS。<br /> 詳しくは、 <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Follow-up message for transactional messaging<br /> </td> 
   <td> イベントをターゲティングするワークフローを作成できるようになりました。これは、トランザクションメッセージを以前に受信した顧客にフォローアップメッセージを送信できることを意味します。イベントタイプ、イベントログ、トラッキングログでターゲットをフィルタリングできます。フォローアップメッセージでは、イベント（ペイロード）のコンテンツを利用できます。<br /> 詳しくは、 <a href="../../channels/using/follow-up-messages.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Extended Profile &amp; Services API<br /> </td> 
   <td> プロファイルおよびサービスAPIに拡張フィールドを公開できるようになりました。パブリケーションメカニズムにより、APIを使用してプロファイルまたはサービスカスタムリソースの拡張フィールドをマッピングできます。For this to work, the <strong>Datamodel</strong> role has been added. この新しい役割により、ユーザーはデータモデルにアクセスできる管理者のセットを設定できます。<br /> 詳しくは、 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### General {#general-1}

* いくつかのセキュリティ上の問題を修正しました。

#### Emails and SMS messages {#emails-and-sms-messages-1}

* The SMS external account configuration screen ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) has been improved. Several parameters have been added in the **[!UICONTROL SMSC specifics]** section to support error codes in the "Text" field.

#### Push notifications {#push-notifications-1}

* **[!UICONTROL Send via push notification]** （Mobile App）テンプレートに基づいてプッシュ通知のオーディエンスを編集する際に、事前定義済みのフィルターが表示されない問題を修正しました。
* The mobile application configuration screen ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) now displays a message to indicate that the iOS or Android platform has been successfully created.

#### Landing pages {#landing-pages}

* ランディングページのフォームが送信されたときに確認電子メールが送信されない問題を修正しました。

#### Audiences and queries {#audiences-and-queries}

* クエリエディターでプロファイルを選択すると発生していたいくつかの問題を修正。

#### Transactional messages {#transactional-messages}

* トランザクションテンプレートを非公開にできないエラーを修正しました。
* イベントリストにイベントが表示される問題を修正しました。

#### Integrations {#integrations-1}

* 共有オーディエンスが、そのオーディエンスの更新後に配信されない問題を修正しました。
* Fixed an issue that prevented a shared asset ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** option) from being used in a landing page.
* Adobe Audience Managerからインポートした共有オーディエンスの編集時に発生していた問題を修正しました。

## Release 16.9 - September 2016 {#release-16-9---september-2016}

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
   <td> Remarketing Triggers<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> Adobe Marketing Cloudでは、様々なトリガー（買い物かごやそのフォームを破棄した顧客の行動、買い物かごから製品を削除した製品、セッションが期限切れのクライアントなど）を定義します。トリガーを作成するときに、トリガーの条件と、イベント（プロ広告）で送信されるデータをAdobe Campaignに定義します。<br /> Adobe Campaignでは、以前に作成したトリガーを選択し、イベントデータを使用してイベントデータを豊かにし、そのトリガーにリンクされているトランザクションメッセージテンプレートを定義します。例えば、クライアントが買い物かごを放棄すると、イベントはAdobe Campaignに送信され、その後15分以内にクライアントに送信されるリマーケティング電子メール経由でこのイベントを利用できます。<br /> 詳しくは、 <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages: Pause / Unpublish<br /> </td> 
   <td> コンテンツの更新中にトランザクションテンプレートの発行を休止できるようになりました。対応するメッセージは送信されなくなりますが、データベースに保存されます。再開すると、キューに登録されているメッセージは処理され、期限切れになっている場合は送信されます。<br /> 詳しくは、 <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">詳細なドキュメント</a>を参照してください。<br /> イベントおよびトランザクションテンプレートも公開取り消しできるようになりました。対応するメッセージは、現在送信されず、データベースに保存されません。<br /> 詳しくは、 <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> 複数のブランドを持つクライアントは、同じインスタンスで管理できるようになりました。ブランドとは、Adobe Campaign内のブランドに関連するすべてのパラメーターを一元的に設定できる、Adobe Campaignインスタンスの管理者が管理する機能です。これには、トラッキングURL、ウェブ分析、サーバURL、ドメイン名などの技術的なパラメーターに対するロゴなどのものが含まれます。<br /> 詳しくは、 <a href="../../administration/using/branding.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Responsive email design preview<br /> </td> 
   <td> この機能により、様々な種類のデバイスでの電子メールの応答性をテストできます。In the email preview, a grid has been added to test your email on various screen sizes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications<br /> </td> 
   <td> マーケティング担当者がiOSおよびAndroidモバイルデバイスでパーソナライズされたセグメントプッシュ通知を送信できるように、新しいチャネルが追加されました。メッセージは、単一の配信またはワークフローアクティビティを使用して送信できます。トランザクションメッセージとの互換性は、今後のバージョンで利用できます。This channel leverages the Mobile core service’s SDK (available <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">here</a>).<br /> 詳しくは、 <a href="../../channels/using/about-push-notifications.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general-2}

* このリリースでは、インターフェイスリストに新しいフィルターおよび検索機能が導入されています。この新機能は、例えば、ログ（配信、追跡）、サービス（購読、購読履歴）、オーディエンスおよびワークフローの移行に使用できます。
* 顧客プロファイルのタッチポイント数に関するいくつかの表示の問題を修正しました。
* 複数のタイポロジイシューを修正。

#### Emails and SMS messages {#emails-and-sms-messages-2}

* 誤った配達確認を編集できるエラーを修正しました。これらは読み取り専用になりました。
* SMSの長すぎるまたはエンコードの問題が発生した場合に、受信者がブラックリストに登録されていた問題を修正しました。

#### Custom resources {#custom-resources-1}

* カスタムリソースのアドバンスフィルターを使用すると、すべての結果が表示されないエラーを修正しました。

#### Transactional messages {#transactional-messages-1}

* 新しいイベント定義の識別子にプレフィックスが自動的に追加されるようになりました。
* インターフェイス内のトランザクションメッセージを表すアイコンが変更されました。

#### Integrations {#integrations-2}

* Fixed a display error that would occur when a high resolution image was inserted via the **Dynamic image from Adobe Target** option.
* リンク先IDがAMCデータソースに設定されていない場合でも共有オーディエンスを保存できるエラーを修正しました。

## Release 16.7 - July 2016 {#release-16-7---july-2016}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enriched transactional messages<br /> </td> 
   <td> トランザクションテンプレートをAdobe Campaignデータベースとリンクして、トランザクションメッセージのコンテンツを充実させる情報を回復できるようになりました。<br /> 詳しくは、 <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic URLs for images<br /> </td> 
   <td> この新機能により、コンテンツブロックと動的テキストを挿入して、トラッキングおよびパーソナライゼーションの目的で画像ソースをパーソナライズできます。<br /> その後、画像URLにパラメータを入力して、AEMアセット（S7）動的メディアの機能から利益を得ることができます。例えば、"Hello Alsecandre"というパーソナライズされた画像を含む電子メールを、パリでの今後のイベントに関する最新のニュースと共に送信できます。または"Hello Frank， get the latest news about将来のイベントに関する最新ニュース」を参照してください。<br /> 詳しくは、 <a href="../../designing/using/personalizing-urls.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with People Core Service<br /> </td> 
   <td> The Adobe Marketing Cloud <strong>Declared IDs</strong> are now covered by the integration between Adobe Campaign and People Core Service (Profiles &amp; Audiences).<br /> つまり、訪問 <strong>者ID</strong>または <strong>宣言済みIDで構成されるセグメントをインポートしたり、オーディエンスをエクスポート</strong>したりできます。<br /> 詳しくは、 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs<br /> </td> 
   <td> The MTA logs (delivery server) now display the complete history of each message, particularly all of the delivery attempts as well as the associated error statuses, and this has no impact on the application's performance.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### General {#general-3}

* 不必要なフィールドが、完了する必要のあるフィールドの代わりに表示される可能性があるエラーを修正しました。これは、クエリ内の条件を編集する際に比較演算子が複数回変更された後に発生していました。
* Fixed the behavior of the option **[!UICONTROL The last X days/months/quarters/years]** when defining a relative filtering condition for a date field. 計算期間は、サーバーの日時を基準としたスライディング期間になり、カレンダーベースではありません。

#### Workflows {#workflows-1}

* **[!UICONTROL Query]** アクティビティのプロパティでターゲットディメンションを選択する際に、画面に間違った値のリストが返されるエラーを修正しました。
* Fixed an error that would force the **Exists** operator to be selected when adding an average or count aggregate on a collection element in a **[!UICONTROL Query]** activity.

#### Content editing {#content-editing}

* HTMLコンテンツを読み込む際に、表示の問題（レスポンシブデザイン）の発生につながる可能性があるエラーを修正しました。コンテンツを初めて開いたときに、スタイル属性が書き直されることはなくなりました。
* 動的コンテンツバリアントに条件が追加された場合に発生していたブロッキング以外のエラーを修正しました。
* ランディングページのコンテンツにチェックボックスを追加すると発生していたエラーを修正。チェックボックスは使用できませんでした。
* 対象のブロックの先頭にカーソルが置かれた場合にブロック内のテキストを削除すると発生する可能性があるエラーを修正しました。

#### Transactional messages {#transactional-messages-2}

* Webサイトを統合する際に、任意のイベントの有効期限を定義できるようになりました。この日が過ぎると、イベントに対応するメッセージを送信できなくなります。

## Release 16.6 - June 2016 {#release-16-6---june-2016}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Profiles and Services API<br /> </td> 
   <td> The Adobe Campaign <span class="uicontrol">Profiles and Services</span> API is available in the <a href="https://www.adobe.io/products/campaign">adobe.io</a> portal. これにより、Adobe Campaignプロファイルを更新、追加および削除したり、REST呼び出し経由でサービスをサブスクライブまたは登録解除したりできます。<br /> 詳しくは、APIの <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">詳細説明</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### General {#general-4}

* モバイルデバイスでツールチップが無効になり、画面に表示される情報が読みやすくなるようになりました。
* iPad画面の特定のゾーンのコンテンツをスクロールできないエラーを修正しました。
* Internet Explorer11でコンテンツの編集中に発生していた互換性エラーをいくつか修正しました。
* データインポートが初めて失敗したときに詳細ログにアクセスできない可能性があるエラーを修正しました。
* 範囲フィルターが保存されない可能性があるエラーを修正しました。
* リストの表示方法を設定する際に、リソースの要素が表示されないエラーを修正しました。
* クエリエディターのエクスプローラーでエラーを修正しました。検索フィールドによって返された結果は検索履歴に保持され、新しい検索ごとに引き続き表示されていました。

#### Emails and SMS messages {#emails-and-sms-messages-3}

* バウンスにリンクされた情報が配信ログで復元されないエラーを修正しました。
* トランザクションメッセージの動的コンテンツブロックにコンテキストがアクセスできないエラーを修正しました。
* 電子メールのコンテンツの動的テキストにURLリンクを定義できないエラーを修正しました。
* 配信作成ウィザードの上部バーの表示を修正しました。
* 配信のプライマリキーをパーソナライゼーションフィールドとして使用することはできません。

#### Workflows {#workflows-2}

* ワークフローの2つのアクティビティ間のトランジションに、計算され、あるアクティビティから別のアクティビティに転送された要素の数が表示されるようになりました。
* **[!UICONTROL Query]** アクティビティに追加データが追加されると、互換性のないフィールドが非表示になりました。
* データを追加するときに表示される集計定義ウィンドウが改善され、使用中のデータと互換性のあるオファーオプションのみが改善されました（例:平均値を計算することは、数値データでのみ可能です。
* 追加の技術ワークフローを開始または再開することは、管理者権限を持つユーザーのみが実行できるようになりました。

#### Landing pages {#landing-pages-1}

* ランディングページのプロパティで32ビットのAESコーディングキーを省略できるエラーを修正しました。
* 表示条件を定義するとき、またはランディングページに動的コンテンツを追加する際に、クエリエディターが正しく表示されないエラーを修正しました。

#### Custom resources {#custom-resources-2}

* The **[!UICONTROL Switch to parameters]** option is now hidden when defining a filter related to a profile's subscriptions to a service.
* カスタムリソースから0-1タイプのリンクが設定された場合に発生する可能性があるエラーを修正しました。
* Fixed an error that, where relevant, could prevent the defined **Constant default value** from being edited when adding a **Date and time** type field in a custom resource.

## Release 16.5 - May 2016 {#release-16-5---may-2016}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Predefined filters<br /> </td> 
   <td> 管理者は、事前設定されたルールの形式でクエリエディターに表示されるアドバンスフィルターを作成できるようになりました。これらのフィルターを選択すると、例えば、オーディエンスを定義する際に、シンプルなインターフェイスで複雑な設定を簡単に作成できます。<br /> 詳しくは、 <a href="../../developing/using/configuring-filter-definition.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Subscription Services<br /> </td> 
   <td> <span class="uicontrol">新しい購読サービス</span> アクティビティを使用すると、サービスに複数のプロファイルをサブスクライブしたり、単一のアクションでサービスをサブスクライブ解除したりできます。<br /> このアクティビティは、ターゲット設定を実行した後、または特定のデータを含むファイルをインポートした後で使用できます。<br /> 詳しくは、 <a href="../../automating/using/subscription-services.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: data enrichment<br /> </td> 
   <td> The <span class="uicontrol">Additional data</span> tab is now available in <span class="uicontrol">Query</span> type activities. この機能により、クエリが対象とするデータを豊富にし、このデータを悪用された以下のワークフローアクティビティに転送できます。<br /> 追加のデータを追加した後、定義された追加データに基づいて条件を作成することで、最初にターゲット設定されたデータにフィルターレベルを適用できます。<br /> 詳しくは、 <a href="../../automating/using/query.md#enriching-data">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Contextual help<br /> </td> 
   <td> 様々なAdobe Campaign画面でコンテキストヘルプ関数を利用できるようになりました。つまり、シングルクリックで、現在使用している機能のドキュメントに直接アクセスできます。コンテキストヘルプを表示するには、"?"をクリックします。icon in the upper-right corner of the screen, as shown in the example below.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-5}

* Marketing Cloud標準に準拠した新しい機能のインターフェイス。
* 様々なコンボボックスタイプの標準化。

#### Emails and SMS messages {#emails-and-sms-messages-4}

* エラーアドレスマスクが指定されている場合に電子メールが送信されないエラーを修正しました。
* TLSプロトコルが電子メール配信でサポートされるようになりました。MX管理の新しい列では、各ドメインに対して目的のTLS動作を定義できます。
* SMSインターフェイスが改善されました。

#### Workflows {#workflows-3}

* 様々なワークフローインターフェイスの新機能
* クイックアクションの表示時に発生するエラーを修正しました。
* Fixed an error that could cause a workflow to fail when using a **[!UICONTROL Segmentation]** type activity containing a 1-N link.
* ワークフローのトランジションがハイブリッドデバイスで開かないエラーを修正しました。
* ワークフローの開始時に一時停止ボタンが表示されないエラーを修正しました。

#### Content editor {#content-editor}

* コンテンツエディターで、電子メールまたはランディングページに含まれるURLをパーソナライズできるようになりました。Refer to the [detailed documentation](../../designing/using/personalizing-urls.md).
* 配信の作成ウィザードに追加され、そのコンテンツが後で変更された場合に画像が失われる可能性があるエラーを修正しました。

#### Custom resources {#custom-resources-3}

* カスタムリソースの設定画面にカスタマイズされた1- Nタイプリンクを追加すると発生していたエラーを修正しました。
* カスタムリソースの準備および公開時のプログレスバーの表示を改善しました。
* カスタムリソースのリンクリストを表示すると発生していたエラーを修正。

#### Transactional messages {#transactional-messages-3}

* インターフェイスのユーザーフレンドリー性と、トランザクションメッセージエンジンのパフォーマンスと堅牢性が最適化されました。
* トランザクションメッセージテンプレートの発行を一時的に停止できるようになりました。For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* 互換性のないターゲットディメンションを持つコンテンツブロックがトランザクションメッセージテンプレートに追加される可能性があるエラーを修正しました。
* APIプレビューがイベント設定画面に表示されないエラーを修正しました。

#### Audiences and queries {#audiences-and-queries-1}

* クエリーエディターでの日付の使用に関する様々なパッチ。Refer to the [detailed documentation](../../automating/using/editing-queries.md#creating-queries).

#### Administration {#administration}

* ユーザーがログインできなかった「標準ユーザー」セキュリティグループの名前に関するエラーを修正しました。

## Release 16.3 - March 2016 {#release-16-3---march-2016}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interface and navigation<br /> </td> 
   <td> Adobe Campaignインターフェイスが改善され、ナビゲーションと操作がシンプルで直感的になりました。<br /> これで、アプリケーションの上部バーから移動できます。The advanced menus are accessible by selecting the <strong>Adobe Campaign</strong> logo.<br /> 詳しくは、 <a href="../../start/using/interface-description.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Save audience<br /> </td> 
   <td> A new option, <span class="uicontrol">Create then update an audience</span> , is now available in the <span class="uicontrol">Save audience</span> activity. このオプションを使用すると、オーディエンスラベルを手動で入力できます。入力したラベルが既存のオーディエンスに対応する場合、そのラベルは更新されます。オーディエンスが存在しない場合は、作成されます。<br /> また、ワークフローが実行されるたびにオーディエンスが更新されます。<br /> オーディエンス更新モードをいつでも選択できます。オーディエンスを新しいデータで入力するか、すべての実行時にオーディエンスデータ全体を置き換えます。<br /> 詳しくは、 <a href="../../automating/using/save-audience.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Segmentation<br /> </td> 
   <td> <span class="uicontrol">セグメント</span> 化アクティビティで、ユーザーが一時リソースのデータをセグメント化できるようになりました。次に例を示します。インポートされたファイルのデータ。<br /> 詳しくは、 <a href="../../automating/using/segmentation.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-6}

* リストの並べ替え時に発生する表示エラーを修正しました。列の並べ替え順を示す矢印は、特定の種類のデータでのみ反転できます。
* クエリにルールが追加されたときにドロップダウンメニューに表示される要素数が制限される問題を修正しました。

#### Emails and SMS messages {#emails-and-sms-messages-5}

* 電子メールレンダリングレポートにアクセスできない可能性があるエラーを修正しました。
* 送信者のアドレスが指定されていない場合、メッセージの送信準備ステージでエラーが返されるようになりました。

#### Workflows {#workflows-4}

* 特定のファイル形式オプションが表示されましたが、CSV形式ファイルの抽出時に考慮されませんでした。これらのオプションは表示されなくなりました。
* Fixed an error caused when the **[!UICONTROL Delete the source files after transfer]** option was checked for a **[!UICONTROL SFTP]** type file transfer.
* Fixed an error that could prevent the counter and preview of **[!UICONTROL Query]** data from being displayed after refreshing the page.
* ワークフローで特定のトランジション（特に配信アクティビティの後）、またはターゲットとフィルターのディメンションが異なるクエリの後に発生するエラーを修正しました。
* アクティビティを追加した後にワークフローが保存されなかった場合、ワークフローの配信アクティビティにパーソナライゼーションフィールドが挿入されないエラーを修正しました。
* 電子メール配信アクティビティのアウトバウンド移行ターゲットディメンションが表示されないエラーを修正しました。

#### Landing pages {#landing-pages-2}

* ランディングページのローカライズ可能なコンテンツブロックでパーソナライゼーションフィールドが正しく機能しないエラーを修正しました。

#### Custom resources {#custom-resources-4}

* Fixed an error that prevented a search on a custom resource from being carried out if the **[!UICONTROL Add search fields]** option of the resource screen definition was checked and if several fields were selected in the **[!UICONTROL Filter zone composition]** .

## Release 16.2 - February 2016 {#release-16-2---february-2016}

### New capabilities {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> A/B test for emails<br /> </td> 
   <td> コンテンツ、件名または送信者の名前に対してA/Bテストを実行できるようになりました。この新機能では、最大3つの要素をテストできます。<br /> A/Bテストに固有の新しいテンプレートから電子メールを作成する場合、作成ウィザードの新しい手順によって、テストのパラメーターを定義できます。<br /> 詳しくは、 <a href="../../channels/using/designing-an-a-b-test-email.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Brand management<br /> </td> 
   <td> ブランドのIDに影響を与えるパラメーターを一元的に入力するため、1つまたは複数のブランドを定義できるようになりました。Adobe Campaignでは、これらのブランドを作成して、配信またはランディングページテンプレートにリンクできます。<br /> 詳しくは、 <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Incremental query<br /> </td> 
   <td> A new workflow activity, <span class="uicontrol">Incremental query</span> , allows you to carry out a query which, on every execution, targets only the new results. 以前の実行の結果は自動的に除外されます。<span class="uicontrol">スケジューラー</span> アクティビティにリンクして、 <span class="uicontrol">増分クエリーの実行頻度を定義</span> できます。<br /> 詳しくは、 <a href="../../automating/using/incremental-query.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> トランザクションメッセージインターフェイスのユーザーフレンドリー性が向上しました。All business process management linked to transactional messages is currently centralized in the <span class="uicontrol">Marketing plans</span> &gt; <span class="uicontrol">Transactional messages</span> menu. イベント設定も改善されました。イベントは、カスタムリソースから独立して管理されるようになりました。<br /> 詳しくは、 <a href="../../channels/using/about-transactional-messaging.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### General {#general-7}

* レポート、リストおよびクエリのいくつかの表示エラーを修正しました。
* いくつかの互換性を修正し、モバイルデバイスでエラーを表示しました。

#### Emails and SMS messages {#emails-and-sms-messages-6}

* メッセージ（電子メールまたはSMS）の作成時に、パーソナライゼーションフィールドを挿入するために使用されるボタンを使用できない可能性があるエラーを修正しました。
* MブロXによって送信されたSMSメッセージが正しく送信されない可能性があるエラーを修正しました。

#### Audiences and queries {#audiences-and-queries-2}

* フィルタリングディメンションを変更した後、クエリに追加の条件を追加すると発生する可能性があったカウントエラーを修正しました。
* クエリの結果をプレビューすると誤ったページ番号付けが発生する可能性があるエラーを修正しました。

#### Content editing {#content-editing-1}

* パーソナライズされた列挙を使用すると動的コンテンツの設定が正しく考慮されない可能性があるエラーを修正しました。

#### Workflows {#workflows-5}

* Fixed an error that could prevent any action in a workflow from being carried out if there was an empty line in the **[!UICONTROL Fields to update]** tab of an **[!UICONTROL Update data]** activity.
* 地理的/組織単位の情報を含むデータをインポートできないエラーを修正しました。
* Fixed an error caused by adding a **[!UICONTROL Change axis]** type of **[!UICONTROL Exclusion]** rule.
* **[!UICONTROL Segmentation]** アクティビティのアウトバウンドトランジションを操作すると、不要な追加セグメントが作成される可能性があるエラーを修正しました。
* ワークフローテンプレートでファイルを読み込むとエラーが発生する問題を修正しました。
* **[!UICONTROL Load file]** アクティビティの列区切り文字としてスペースが使用されない可能性があるエラーを修正しました。

#### Custom resources {#custom-resources-5}

* 書き出し時にリソースが公開されている場合に、パッケージをインポートした後にカスタムリソースのステータスが再ドラフト化されないエラーを修正しました。

#### Packages {#packages}

* ワークフローを含むパッケージをエクスポートできないエラーを修正しました。
* 同じリソースの複数の要素を選択できない可能性があるエラーを修正しました。

## Release 16.1 - January 2016 {#release-16-1---january-2016}

### New capabilities {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> The following email specific reports have been added: <span class="uicontrol">Complaints</span> , <span class="uicontrol">Opens</span> , and <span class="uicontrol">Unsubscriptions</span> .<br /> 次のレポートが改善されました。 <span class="uicontrol">配信サマリ</span> 、 <span class="uicontrol">バウンスサマリ</span> 、 <span class="uicontrol">配信スループット</span> および <span class="uicontrol">トラッキングインジケータ</span> 。<br /> 詳しくは、 <a href="../../reporting/using/defining-the-report-period.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Query editing<br /> </td> 
   <td> The query editor has been improved and now allows you to scan the <strong>1-N</strong> type links.<br /> 詳しくは、 <a href="../../automating/using/editing-queries.md#creating-queries">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Content personalization<br /> </td> 
   <td> As for email or landing page editing, the input interface for content block display conditions has been improved.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: column definition when importing<br /> </td> 
   <td> <span class="uicontrol">読み込みファイル</span> アクティビティでは、インポートしたファイルの列を詳細に設定できます。データタイプ、日付と時間の形式、空の値またはエラーの場合に適用する処理、および値の再マッピング。<br /> 詳しくは、 <a href="../../automating/using/load-file.md#column-format">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping of SMS encodings<br /> </td> 
   <td> 標準エンコーディングを使用しないプロバイダー向けにパーソナライズされたSMSメッセージのエンコーディングのマッピングを定義できるようになりました。管理者はパーソナライズされたマッピングの設定を実行し、考慮されるべき順序を定義できます。<br /> 詳しくは、 <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-8}

#### General {#general-8}

* ハイブリッド/タッチスクリーンデバイスのInternet ExplorerおよびChromeとの互換性が改善されました。
* 指定された電子メールアドレスに構文エラーが含まれている場合に、新しいユーザー/プロファイル/テストプロファイルに入力されたすべてのデータが失われる可能性があるエラーを修正しました。

#### Emails and SMS messages {#emails-and-sms-messages-7}

* 電子メールプレビュー画面でコンテンツサムネールが生成されない可能性があるエラーを修正しました。
* メッセージの生コンテンツ（電子メールまたはSMS）がメッセージプレビュー画面に表示されない可能性があるエラーを修正しました。

#### Audiences and queries {#audiences-and-queries-3}

* Fixed an error that could prevent a **Query** type audience from being created in the **Service** resource.
* アドバンスモードでクエリの条件を編集すると、関数リストが正しく表示されない可能性があるエラーを修正しました。
* Fixed an error that could prevent a **Query** type audience from being created if it contained criteria based on collections.
* 配信KPIのフィルターを含むクエリが作成されない可能性があるエラーを修正しました。
* ワークフローから作成されたオーディエンスのコンテンツがプレビューされない可能性があるエラーを修正しました。

#### Custom resources {#custom-resources-6}

* カスタムリソースにデフォルト値のあるフィールドが含まれている場合にサーバーがクラッシュする可能性があるエラーを修正しました。
* Fixed an error caused by moving, then deleting an element in the **[!UICONTROL Detail screen configuration]** section while defining screens of a custom resource.
* Fixed an error that occurred when a default value had been defined for an **integer** list that did not include **0** in its range of possible values.
* 再初期化後に、カスタムリソースの詳細画面設定に要素が追加されない可能性があるエラーを修正しました。

#### Workflows {#workflows-6}

* 選択したアクティビティの表示のみではなく、ワークフロー内のすべてのアクティビティのログが表示される可能性があるエラーを修正しました。
* **[!UICONTROL Scheduler]** アクティビティのエラーを修正しました。**[!UICONTROL Day of the month]** このオプションは、アカウントに正しく反映されず、置き換え **[!UICONTROL Week day]** られました。
* Fixed an error that could prevent a **[!UICONTROL Scheduler]** activity from working correctly with the expiration mode set to **[!UICONTROL After a certain number of iterations]** .
* **[!UICONTROL Extract file]** アクティビティを使用してデータをエクスポートする際に発生するエラーを修正しました。エクスポートファイルに存在する行数が、書き出された要素の数よりも劣っていました。
* **[!UICONTROL Load file]** アクティビティのファイルが選択されない可能性があるエラーを修正しました。
* **[!UICONTROL Update data]** アクティビティで更新されるフィールドが削除されないエラーを修正しました。
* ワークフロー実行ログを開いた後、ワークフローに対する変更を保存できないエラーを修正しました。
* Fixed an error that caused a **[!UICONTROL Load file]** activity to be executed twice if it was configured to use the file from its inbound transition and this file had been loaded using a **[!UICONTROL Transfer file]** activity.
* Fixed an error that could prevent certain temporary entities from being correctly processed by an **Exclusion** activity.
* Fixed an error that could prevent a **[!UICONTROL Query]** activity from being executed correctly if the targeting dimension and the filtering dimension configured in the activity were different.
* Fixed an error concerning the automatic naming of outbound transitions added to a **[!UICONTROL Fork]** activity that could prevent the workflow from being saved.

#### Content editing {#content-editing-2}

* コンテンツ編集時にアイコンまたは検索バーの表示が望ましくないというエラーを修正。

#### Landing pages {#landing-pages-3}

* パッケージインポートを使用してランディングページをインポートできないエラーを修正しました。

#### Transactional messages {#transactional-messages-4}

* Message Centerプッシュエージェントオペレーターのセキュリティパラメーターで信頼できるIPアドレスを指定できるようになりました。
* 新しいタイプのイベントが作成されない可能性があるエラーを修正しました。

## Release 15.11 - November 2015 {#release-15-11---november-2015}

### New capabilities {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> Adobe CampaignでSMSメッセージを送信できるようになりました。<br /> 電子メールの場合と同様に、キャンペーンおよびマーケティングアクティビティのリストから新しいSMS配信を作成できます。ワークフローから単一の送信および定期的なSMSメッセージを作成することもできます。<br /> これらのSMS配信は、配信テンプレートのリストから設定できるテンプレートに基づいています。デフォルトのテンプレートを使用できます。<br /> これらのSMS配信は、ほとんどのSMSルーターで使用されるSMPP3.4プロトコルを使用します。<br /> 詳しくは、 <a href="../../channels/using/about-sms-messages.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring transitions<br /> </td> 
   <td> ワークフローの最後の移行でデータとその構造を確認できるようになりました。This allows you to check that the processes applied by each activity correspond to your needs.<br /> </td> 
  </tr> 
  <tr> 
   <td> File pre- and post-processing in workflows<br /> </td> 
   <td> <span class="uicontrol">読み込みファイル</span> を使用して読み込み、ファイル <span class="uicontrol"></span> アクティビティを抽出する際に、データファイルに追加の処理を実行できるようになりました。<br /> デフォルトでは、これらのアクティビティでGZIP形式のファイルを解凍したりzip形式で圧縮したりできます。<br /> 詳しくは <a href="../../automating/using/load-file.md">、ファイルの読み込み</a> および <a href="../../automating/using/extract-file.md">ファイル</a> アクティビティの抽出に関するドキュメントを参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliverability reports<br /> </td> 
   <td> 電子メールのレンダリングレポートが利用できるようになりました。このレポートでは、サポートされているサポートおよびメッセージサービスに従って、メッセージの様々なレンダリングを表示できます。<br /> レポートの概要には、受信したメッセージ、スパムメッセージ、受信されないメッセージ、受信待ちメッセージの数も表示されます。<br /> 詳しくは、 <a href="../../sending/using/email-rendering.md#email-rendering-report-description">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Package Management<br /> </td> 
   <td> It is now possible to import and export images in packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quick actions<br /> </td> 
   <td> 特定のアクションが表示されるのは、リストまたはワークフローで要素を選択した後またはその後にマウスポインターを置いたときです。これらのアクションの一部は、アクセスを容易にするために関係する要素の周りにアイコンとして表示されるようになりました。These quick actions can be used to duplicate an element, delete it, show the detail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-9}

#### General {#general-9}

* 管理者アカウントからインスタンスの一般パラメーターにアクセスできない可能性があるエラーを修正しました。
* **現在は、フローティング** データがカスタムリソースで正しく考慮されます。
* 対応するテンプレートのステータスが変更された場合に発生していた、実行されたシンプルなインポートのリストの表示エラーを修正しました。

#### Landing pages {#landing-pages-4}

* 英語インスタンスのフランス語で誤って表示される可能性のあるランディングページテンプレートの一部の要素を修正しました。

#### Audiences {#audiences}

* Adobe Marketing Cloudからインポートしたオーディエンスがオーディエンスのリストに表示されない可能性があるエラーを修正しました。
* クエリを定義する際に大文字と小文字が区別される可能性があるエラーを修正しました。
* クエリを定義する際にオーディエンスがフィルターされない可能性があるエラーを修正しました。
* オーディエンスでアクションがキャンセルされない可能性があるエラーを修正しました。

#### Workflows {#workflows-7}

* **[!UICONTROL Update data]** アクティビティの更新されたフィールドが手動で設定されない可能性があるエラーを修正しました。
* Fixed an error that could cause the **[!UICONTROL Query]** activity to load infinitely when opened if the workflow had not been saved after having placed the activity in the diagram.
* Fixed an error that could cause the server to stop while counting or previewing an audience selected from a **[!UICONTROL Query]** in a workflow.
* ワークフローのアクティビティが開いたときに表示される重大でないエラーを修正しました。
* Fixed an error that prevented a **[!UICONTROL Scheduler]** activity from being configured to execute a workflow several times a day.
* 特定のワークフローアクティビティにクエリを実行できないフィールドが発生する可能性があるエラーを修正しました。
* Fixed an error that could prevent the user from locating the KPIs added from a **[!UICONTROL Query]** on deliveries in the outbound transition.
* ファイルをワークフローにインポートした後、ファイルのオーディエンスが作成されない可能性があるエラーを修正しました。
* Fixed an error that could prevent data from being updated on profiles if the **location/address3** field of the resource was used.
* ワークフローで、モデレートのモデレートが不可能になるエラーを修正しました。
* SQLを表示できないエラーを修正しました。これにより、ワークフローでの定期的な配信のエラーが発生する可能性がありました。

#### Content editor {#content-editor-1}

* ランディングページまたは電子メールのソースコードで検索が不可能になるエラーを修正しました。

#### Packages {#packages-1}

* 特定のタイプの要素をパッケージ（特にランディングページ、ワークフロー）にエクスポートできない可能性がある様々なエラーを修正。
* ラベルが変更された場合に以前のパッケージインポートラベルが表示される原因となっていたエラーを修正。
* 互換性のないリソースがエクスポート可能なリソースのリストに表示される可能性があるエラーを修正しました。

## Release 15.10 - October 2015 {#release-15-10---october-2015-}

### New capabilities {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Deduplication activity<br /> </td> 
   <td> データの重複排除専用の新しいアクティビティがワークフローで使用できるようになりました。このアクティビティにより、選択した条件に従ってターゲット内の重複をフィルターできます。<br /> 詳しくは、 <a href="../../automating/using/deduplication.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Improved diagram<br /> </td> 
   <td> ワークフローワークスペースから、複数のキーボードショートカットを使用して、アクティビティを選択、開く、削除できるようになりました。<br /> アクティビティの配置も改善され、ワークフローが視覚的に整理されるようになりました。<br /> 詳しくは、 <a href="../../automating/using/workflow-interface.md#workspace">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> The date and time of the export is now automatically added to the labels of the files exported using an <span class="uicontrol">Extract file</span> activity. This way the files generated are unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> The name of the template from which a simplified import was carried out is now visible by default in the import list and in the detail of each import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Improvement and extended possibilities for managing and defining links for custom resources.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-10}

#### Email {#email}

* サービスの購読解除リンクがミラーページから正常に機能しない問題を修正しました。
* 電子メールの編集ページに電子メール配信ラベルが正しく表示されない可能性があるエラーを修正しました。
* Fixed an error that could prevent an external **[!UICONTROL Routing]** account from being selected in a duplicated delivery template.

#### Audiences {#audiences-1}

* クエリで1- Nリンクが使用されている場合、オーディエンス数の間にエラーが発生する問題を修正しました。
* 電子メール配信のターゲットオーディエンスでプロファイルが選択されない可能性があるエラーを修正しました。

#### Workflows {#workflows-8}

* ワークフローで電子メール配信を設定すると表示の問題が発生する可能性があるエラーを修正しました。
* **[!UICONTROL Load file]** アクティビティが正しく動作しない可能性があるエラーを修正しました。空白のエラーメッセージが表示されます。
* **[!UICONTROL Transfer file]** アクティビティが正しく動作しない可能性があるエラーを修正しました。アクセス権が常に正しく考慮されていませんでした。
* Fixed an error that could prevent a file from being exported if the workflow contained a **[!UICONTROL Recurring email]** .
* 電子メール配信をワークフローで作成したり、件名と定義されたコンテンツを考慮しないことがあるというエラーを修正。
* Fixed an error that could prevent a reconciliation key from being selected in an **[!UICONTROL Update data]** activity when configuring the workflow of a simplified import template.
* アクティビティが削除された後にワークフローが保存されない可能性があるエラーを修正しました。

#### Platform {#platform}

* カスタムリソースにその要素のリソースタイプへのリンクが含まれている場合に、新しい要素が作成されない可能性があるエラーを修正しました。
* 特定のログの15分の遅延が書き込まれる可能性があるエラーを修正しました。
* Fixed an error that could prevent the marketing activity list from being displayed when sorted by the **[!UICONTROL Date]** or **[!UICONTROL Indicators]** columns.

#### Landing pages {#landing-pages-5}

* ランディングページをプレビューするためにテストプロファイルを選択すると発生していたエラーを修正。

#### Transactional messages {#transactional-messages-5}

* テストプロファイルでイベントを削除した後にアプリケーションがクラッシュする可能性があるエラーを修正しました。

#### Reports {#reports}

* Fixed an error that could cause incorrect data to be sent for the reports **[!UICONTROL deliveryThroughputReport]** and **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* 動的コンテンツブロックの処理時に発生するHTML tag managementエラーを修正。

## Release 15.8 - August 2015 {#release-15-8---august-2015}

### New capabilities {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> データを簡単にインポートできるようになりました。<br /> 管理者が事前定義したテンプレートを選択し、インポートするデータを含むファイルをアップロードするだけです。テンプレートで定義されているワークフローは、ユーザーに対して透過的に実行され、読み込みの結果とエラーのログの詳細にアクセスできます。<br /> これらのファイルからのデータは、データベースに挿入することも、オーディエンスを直接作成する手段として使用することもできます。<br /> 詳しくは、 <a href="../../automating/using/about-data-import-and-export.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creating programs and campaigns<br /> </td> 
   <td> これで、作成された日が自動的に開始日として使用されるようにキャンペーンおよびプログラムが設定されます。<br /> 終了日は、次のような開始日に従って設定されます。<br /> 
    <ul> 
     <li> プログラムの場合はD+186 </li> 
     <li> キャンペーンの場合はD+61 </li> 
    </ul> For more information, refer to the <a href="../../start/using/programs-and-campaigns.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> The list of tracked URLs is now read only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> 作成中のアカウントのパスワード変更や確認など、イベントのパーソナライズされたトランザクションメッセージを管理できるようになりました。<br /> 詳しくは、 <a href="../../channels/using/about-transactional-messaging.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> 次のような機能が追加されました。テストプロファイル、ステータス管理およびリソースの削除を参照してください。<br /> 詳しくは、 <a href="../../developing/using/resource-statuses.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-11}

#### Display {#display}

* Safariのクエリエディターで2つのフィールドがジャックスタップされる可能性があるエラーを修正しました。

#### Content editor {#content-editor-3}

* 電子メールの件名で文字"&lt;"、"&amp;"および"&gt;"が使用できない問題を修正しました。

#### Email {#email-1}

* 動的テキストの後にユーザーがテキストを追加できないエラーを修正しました。

#### Lists {#lists}

* Fixed an error that prevented the **Message** column in workflow execution logs from being exported correctly.

#### Profiles and audiences {#profiles-and-audiences}

* 要素が複製または削除されたときの二重の確認につながるエラーを修正しました。**Internet Explorer11を使用するハイブリッドデバイス**&#x200B;のみ。

#### Workflows {#workflows-9}

* ワークフローから電子メールが送信されない可能性があるエラーを修正しました。
* **[!UICONTROL Load file]** アクティビティで拒否ファイルの名前が指定されていない場合にワークフローが実行されない可能性があるエラーを修正しました。
* Fixed an error that could prevent a workflow from executing when the **[!UICONTROL Execution frequency]** of a **[!UICONTROL Schedule]** activity was set to **[!UICONTROL Daily]** .

#### Platform {#platform-1}

* 読み込みバランスのとれた環境でサムネールが生成されないエラーを修正しました。

## Release 15.7 - July 2015 {#release-15-7---july-2015}

### New capabilities {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exporting lists<br /> </td> 
   <td> リストからCSV形式でコンテンツをファイルに書き出すことができるようになりました。This function is available in all screens with a <strong>List</strong> mode (for example: profile list).<br /> エクスポートされるデータは、エクスポート時に表示される列のデータです。リストを編集すると、エクスポートするデータを選択できます。<br /> この機能の使用について詳しくは、 <a href="../../automating/using/exporting-lists.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with Adobe Profiles &amp; Audiences<br /> </td> 
   <td> You can now share audiences between Adobe Campaign and your other Adobe Marketing Cloud solutions:<br /> 
    <ul> 
     <li> Export: when you save an audience composed of profiles in a workflow, a new <span class="uicontrol">Share in Adobe Marketing Cloud</span> option allows you to add profiles to an existing audience or to create a new audience. </li> 
     <li> Import: by creating a <strong>List</strong> type audience from the audience management screen, a new option allows you to identify it as an <span class="uicontrol">Adobe Marketing Cloud Audience</span> . その後、既存の共有オーディエンスを選択して、Adobe Campaignにインポートできます。 </li> 
    </ul> For more information on configuring and using this functionality, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic content<br /> </td> 
   <td> 動的コンテンツインターフェイスが改善されました。矢印が表示され、電子メールの本文で直接様々な動的コンテンツを移動できるようになりました。<br /> この機能の使用について詳しくは、 <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic text<br /> </td> 
   <td> From the content editor of an email, you can now define dynamic text:<br /> 
    <ul> 
     <li> 電子メールの件名で、 </li> 
     <li> HTMLモードで、 </li> 
     <li> またはテキストモードで、 </li> 
    </ul> For more information on using this functionality, refer to the <a href="../../designing/using/defining-dynamic-text.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programs and campaigns - Reports<br /> </td> 
   <td> レポートのインターフェイスとグラフィックが改善されました。<br /> この機能の使用について詳しくは、 <a href="../../reporting/using/defining-the-report-period.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-12}

#### Installation {#installation}

* Adobe Campaignインスタンス名が32文字に制限されるようになりました。

#### Workflows {#workflows-10}

* ワークフローでのクエリの編集時に「配信」リソースをターゲット設定できない可能性があるエラーを修正しました。
* ワークフローでのクエリの編集時に特定のリンクされたリソースが処理されない可能性があるエラーを修正しました。
* Fixed an error that could prevent a **Recurring delivery** activity from being modified if the workflow had already been executed.

#### Emails {#emails}

* 動的コンテンツが式エディターで追加されたときに電子メールを送信する前にJavaScript構文エラーがチェックされないエラーを修正しました。

#### Landing pages {#landing-pages-6}

* ランディングページをタブレットから編集できないエラーを修正しました。

#### Assets Core Service {#assets-core-service}

* 編集中の電子メールまたはランディングページから共有リソースを選択すると、使用可能なリソースのリストがAdobe Campaign用にフィルターされるようになりました。

## Release 15.6 - June 2015 {#release-15-6---june-2015}

### New capabilities {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Reconciliation activity<br /> </td> 
   <td> A new <strong>Reconciliation</strong> activity links unidentified data (for example, after importing a file) with existing resources within a workflow.<br /> このアクティビティは、基本的にはデータ管理の目的で使用されます。It responds to two different use cases:<br /> 
    <ul> 
     <li> <strong>関係</strong>の追加: <strong>「関係</strong> 」タブでは、受信データとAdobe Campaignデータベースの他の複数のディメンションの間にリンクを追加できます。 </li> 
     <li> <strong>データの識別</strong>: <strong>「識別」</strong> タブを使用すると、受信データをAdobe Campaignデータベースの既存のディメンションの列に関連付けることができます。アクティビティを離れると、データは指定したディメンションに属するものとして識別されます。 </li> 
    </ul> Refer to the <a href="../../automating/using/reconciliation.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> A new <strong>Extract file</strong> activity allows you to export data from the Adobe Campaign database in the form of an external file from a workflow. <br /> 制限:現時点では、出力ファイルに動的名前を使用することはできません。<br /> 詳細について <a href="../../automating/using/extract-file.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Scheduler activity<br /> </td> 
   <td> Improved widget that allows you to select the execution time of the <strong>Scheduler</strong> activity in a workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Transfer file activity<br /> </td> 
   <td> SFTP is now supported.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> <span class="uicontrol">開発</span> メニューでは、購入や製品テーブルなどの独自のカスタムリソースを作成することで、管理者権限を持つユーザーが提供するデータテンプレートを充実させることができます。<br /> また、あらかじめ用意されているリソースを拡張して、新しいフィールドを追加することもできます。<br /> また、新しいカスタムリソースまたは拡張カスタムリソースに対応するナビゲーションを設定できます。<br /> 詳細について <a href="../../developing/using/data-model-concepts.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> The <strong>Middle name</strong> and <strong>Title</strong> of the test profiles can now be selected when configuring the list of test profiles.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content editor: Dynamic content<br /> </td> 
   <td> 式エディターで定義された条件に従って、ユーザーに動的に表示される異なるコンテンツを定義できます。<br /> 詳細について <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> A <strong>Test profiles</strong> column is now available in an email's sending logs.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-13}

#### Lists {#lists-1}

* リストから要素を削除すると、リストが自動的に更新されるようになりました。
* 1つの列のみを含むリストから要素を選択できないエラーを修正しました。
* ページを更新した後、リストの表示に適用された変更が失われるエラーを修正しました。
* テストプロファイルの中央名とタイトルをテストプロファイルリストに表示できるようになりました。
* Mozilla Firefoxを使用してリストのチェックボックスを選択すると発生していたエラーを修正しました。

#### Audiences {#audiences-2}

* Fixed an error that prevented the **[!UICONTROL Add]** button from being used in the audience interface.

#### Emails {#emails-1}

* 電子メールの編集時に、行でプレビューボタンが2回使用されないというJavaScriptエラーを修正。
* Fixed an error that prevented the **[!UICONTROL Edit properties]** and **[!UICONTROL Show proofs]** buttons from being used on Microsoft Surface Pro3 tablets using Internet Explorer 11.
* 電子メールの送信ログが表示されない可能性があるエラーを修正しました。

#### Landing pages {#landing-pages-7}

* Fixed an error that prevented the **Brand logo** content block from being used when editing content in a landing page.
* ランディングページに有効性の日付が指定されている場合、マーケティングアクティビティリストにランディングページが表示されないエラーを修正しました。

#### Workflows {#workflows-11}

* **セグメント** 化アクティビティの設定時にグループモードでセグメントを正しく動作させないエラーを修正しました。
* **セグメント** 化アクティビティを設定した後、トランジションを選択できないエラーを修正しました。
* **セグメント** 化アクティビティを設定した後、トランジションを削除できないエラーを修正しました。
* **セグメント** アクティビティ内で母集団をカウントおよびプレビューできないエラーを修正しました。
* 繰り返し電子メールを効果的に削除できないエラーを修正しました。
* Fixed an error that caused data from a deleted **Transfer file** activity to appear in a new **Transfer file** activity.
* **除外** アクティビティ内で除外ルールが正しく考慮されないエラーを修正しました。
* ワークフローで電子メール配信アクティビティを削除すると発生していたエラーを修正。対応する配信も、マーケティングアクティビティリストから削除されました。

#### Navigation {#navigation}

* Tabキーを使用して、同じページ上のフィールド間を適切に移動できるようになりました。

## Release 15.4 - April 2015 {#release-15-4---april-2015}

### New capabilities {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Package exports / Package imports<br /> </td> 
   <td> <strong>展開</strong> メニューでは、パッケージをエクスポートして読み込むことによって、管理者権限を持つユーザーが異なるAdobe Campaignインスタンス間のリソースを交換できるようになりました。<br /> 詳細について <a href="../../automating/using/managing-packages.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> All reports (except the <strong>Hot clicks</strong> report) can now be accessed from a program. These reports are:<br /> 
    <ul> 
     <li> プログラム配信のスループット </li> 
     <li> プログラムトラッキングインジケータ </li> 
     <li> ドメイン別のプログラム分類 </li> 
     <li> 配信不能プログラムおよびバウンスプログラム </li> 
     <li> プログラムURLとクリックストリーム </li> 
    </ul> これらのレポートは、特定の期間（例:3か月、6か月など）でフィルターできます。キャンペーンレポートもフィルターできます。<br /> 詳細について <a href="../../reporting/using/about-dynamic-reports.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Email delivery</strong> activity<br /> </td> 
   <td> The <strong>Email delivery</strong> activity in the workflows has been improved. アプリマーケティングアクティビティのリストから、電子メール、定期電子メールおよび繰り返し電子メール実行に関する詳細情報を検索できるようになりました。<br /> 詳細について <a href="../../automating/using/email-delivery.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Segmentation</strong> activity<br /> </td> 
   <td> <strong>セグメント</strong> 化アクティビティがワークフローで利用できるようになりました。このアクティビティにより、同じワークフロー内でアップストリームに配置されたアクティビティによって計算された母集団から、1つまたは複数のセグメントを作成し、セグメントコードをリンクできます。このアクティビティから、セグメントは1つのトランジションまたは複数の異なるトランジションで処理できます。これで、訪問者をフィルターし、各セグメントのサイズを制限してパーソナライゼーションを最適化できるようになりました。例えば、特定の条件に対応するプロファイルをランダムに選択できます。<br /> 詳細について <a href="../../automating/using/segmentation.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Assets Core Service</strong><br /> </td> 
   <td> You can now use shared resources via <strong>Assets Core Service</strong> in your email and landing page contents. Adobe Marketing Cloudから直接共有リソースを管理できます。<br /> 詳細について <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Adobe Target</strong><br /> </td> 
   <td> You can now insert images that are dynamically computed by <strong>Adobe Target</strong> into your Adobe Campaign emails. これにより、Adobe Targetセグメントで定義されている条件に従って、コンテンツをパーソナライズして同じ電子メールの複数バージョンを提供できます。<br /> 詳細について <a href="../../integrating/using/about-campaign-target-integration.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: <strong>Block selector</strong><br /> </td> 
   <td> HTMLコンテンツエディターでブロックを選択すると、編集ゾーンの下部にパンくずリストが表示されます。これにより、様々な要素に簡単に移動して選択できます。<br /> 詳細について <a href="../../designing/using/managing-landing-page-structure-and-style.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3 - March 2015 {#release-15-3---march-2015}

### New capabilities {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> レポートまたはキャンペーンから直接レポートにアクセスできるようになりました。<strong>配信サマリ</strong> レポートがプログラムレベルで追加されました。<br /> 詳細について <a href="../../reporting/using/delivery-summary.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Update data<br /> </td> 
   <td> In the workflows, the available <strong>Update data</strong> activity has a new option, which allows you to automatically link inbound data fields with the fields of an application schema. これにより、フィールドを更新するための選択プロセスが容易になります。<br /> 詳細について <a href="../../automating/using/update-data.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email delivery<br /> </td> 
   <td> In workflows, the advanced options of the <strong>Email delivery</strong> activity can now be accessed via a specific button in the action bar. This button is only available if an <strong>Email delivery</strong> activity is selected. 主なメリットは、アウトバウンドトランジションをアクティビティに追加し、ワークフローに表示されるアクティビティの名前を編集できることです。<br /> 詳細について <a href="../../automating/using/email-delivery.md">は、を</a>参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-14}

#### General {#general-10}

* 配信の作成時に受信者が表示されないエラーを修正しました。
* 「開いている」条件を使用している「受信者」に基づくオーディエンスが使用できない問題を修正しました。
* 空のプロファイルが削除されないエラーを修正しました。
* 配信のプレビュー時に発生するエラーを修正しました。
* マーケティングアクティビティを複製できないエラーを修正しました。
* キャンペーンの削除時に発生するエラーを修正しました。

