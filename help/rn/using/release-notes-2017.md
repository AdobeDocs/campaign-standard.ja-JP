---
title: リリースノート2017
seo-title: リリースノート2017
description: リリースノート2017
seo-description: このページには、Adobe Campaign Standardの2017リリースすべてが一覧表示されます。
page-status-flag: 常にアクティブ化されていない
uuid: d73f8186- e309-441b-969d-71d0a1c33cf4
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: 参照
topic-tags: campaign- standard- release
discoiquuid: 1fats9b3b-9b3e-4587-9c46- b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2017{#release-notes}

Adobe Campaign Standardの2017年リリースを探しますか。

各リリースには、新機能およびパッチが含まれています。そのコンテンツを表示するには、リリースをクリックします。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 17.10 - October 2017 {#release-17-10---october-2017}

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
   <td> Fatigue Management<br /> </td> 
   <td> 疲労管理を使用すると、プロファイルとの通信を管理するために疲労ルールを作成できます。疲労ルールは容易に構築できますが、複数チャネルにわたるメッセージのカウント（トランザクションメッセージを含む）、特定の配信のカウントまたは特定のプロファイルへのルール適用などの機能に非常に柔軟性があります。<br /> 詳しくは、 <a href="../../administration/using/fatigue-rules.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> URLからインポートすると、Webサイトからクリエイティブコンテンツをすばやく取得して、あらゆる配信の電子メールを作成できます。さらに、第三者がURL経由でコンテンツを直接共有できるようにすることで、クリエイティブプロセスを効率化できます。インポートされたコンテンツは、単一の配信またはテンプレートレベルで柔軟に使用して、ワークフローベースのすべてのキャンペーンのブランドの一貫性を確保し、ワークフローベースのメッセージまたはトランザクションメッセージにして、A/Bまたは多変量テストを含めることができます。URLからインポートすると、すべてのリンクが自動的に変換および追跡され、動的レポートを使用して電子メールのパフォーマンスが監視されます。<br /> 詳しくは、 <a href="../../designing/using/importing-content-from-a-url.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### Platform {#platform}

* zipファイルのサイズが適切に解凍されない問題を修正しました。
* ブランド管理のセキュリティが強化されました。ブランド名と送信者のアドレスを変更することが、アドビのテクニカル管理者向けに予約されました。
* セキュリティ、ユーザ生成コンテンツ（画像、ミラーページ、ランディングページなど）の改善は、adobe.comドメインでは提供できません。ブランドを使用することで、独自のドメインを使用してこれらのリソースを処理することが必須となりました。
* マーケティングアクティビティを表示およびフィルタリングする際のインターフェイスの問題を修正しました。
* 購読のREST API呼び出しで購読日フィールドを更新できない問題を修正しました。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* メッセージ内のリストタイプオーディエンスをターゲット設定しないと、準備ができない問題を修正しました。
* 多言語電子メール配信機能に言語が追加されていません。
* ユーザーがコンテンツを変更して保存すると、配信ダッシュボードに表示されるコンテンツサムネールが自動的に更新されるようになりました。
* タイムゾーン関連の問題を修正し、配信を開けない問題を修正しました。

#### Push notifications {#push-notifications}

* When configuring the push notification channel, the push provider platform for iOS should be **apns** and for Android **gcm**.
* iOSモバイルアプリをAdobe Campaignインターフェイスに追加できないエラーを修正しました。
* GCMおよびFCM対応のAndroidモバイルアプリケーションでプッシュ通知がサポートされるようになりました。
* プッシュ通知テンプレートを複製する際にコンテンツを保存できないエラーを修正しました。
* モバイルアプリケーションユーザーのデータを調整して、Adobe Campaignデータベースからプロファイルを作成または更新できるようになりました。
* Adobe Campaignでは、標準プッシュ通知を使用してトランザクションプッシュ通知の処理を優先順位付けするようになりました。

#### Reports {#reports}

* ホットクリック率が電子メールコンテンツに表示されない問題を修正しました。
* ブラックリスト指標で、バウンスではなくハードバウンスとしてカウントされていた問題を修正しました。
* サマリデータに負の数が表示される問題を修正しました。
* 不適切な年齢セグメントのプロファイルがカウントされる問題を修正しました。
* バウンスおよびハードバウンスの計算式が変更されました。

#### Workflows {#workflows}

* Fixed an issue in the **[!UICONTROL Load file]** activity that could lead to errors after manually adding and removing columns in the activity.
* **[!UICONTROL deliverabilityUpdate]** テクニカルワークフローが、午前2時に実行されるようにスケジュールされました。
* エクスポートロールなしでリストエクスポートを実行できるセキュリティの問題を修正しました。
* **[!UICONTROL Reconciliation]** アクティビティの問題を修正しました。
* **[!UICONTROL File Transfer]** アクティビティでのワイルドカード文字の使用に関する問題を修正しました。

#### Profiles and audiences {#profiles-and-audiences}

* 一部の特定のケースで、クエリの条件が正しく考慮されないという問題を修正しました。
* 送信されたが期限切れと期限切れのメッセージが表示された場合にプロファイルにアクセスできない問題を修正しました。

#### Integrations {#integrations}

* Triggers用に作成された一部のデータソースが正しく表示され、選択されない問題を修正しました。

#### Custom resources {#custom-resources}

* リスト画面で、カスタムリソース行がデータなしで表示される問題を修正しました。
* ブール型フィールドが"False"の値をカスタムリソースに表示できない問題を修正しました。

## Release 17.9 - September 2017 {#release-17-9---september-2017}

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
   <td> Library of Email templates<br /> </td> 
   <td> 2つの美しいテーマ（アストロとFeather）でデザインされた、18進数のブランド新規レスポンシブテンプレートを紹介しています。これらのカスタマイズ可能なテンプレートは業界にとらわれず、すぐに使用できる状態です。テンプレートには、さまざまな使用事例のコンテンツが含まれており、これまでよりも迅速かつ効率的かつより美しく、より美しく、より美しく電子メールマーケティングキャンペーンを実施できます。<br /> 詳しくは、 <a href="../../start/using/about-templates.md#content-templates">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic Reporting with Profile Data<br /> </td> 
   <td> 動的レポートにより、完全にカスタマイズ可能なリアルタイムのビジネスレポートが提供されます。このリリースでは、動的レポート機能に対する強力な機能強化が追加され、プロファイルデータへのアクセスが追加されました。これにより、オープンやクリックなどの機能的な電子メールキャンペーンデータに加え、性別、市区町村、郵便番号、年齢などのプロファイルディメンションによる人口統計分析が可能になります。使いやすいドラッグアンドドロップインターフェースで、最も重要な顧客セグメントに対してどのように電子メールキャンペーンが実行されたかを、今まで以上に簡単に判断できます。<br /> 詳しくは、 <a href="../../reporting/using/about-dynamic-reports.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mass Subscription with Origin &amp; Date<br /> </td> 
   <td> この一括購読の機能強化により、ワークフローの購読サービスアクティビティを通じて、購読情報（出発日と日付）をAdobe Campaign Standardデータベースに直接格納できるようになりました。<br /> 詳しくは、 <a href="../../automating/using/subscription-services.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### Platform {#platform-1}

* 一部の顧客は、一意のキーを特定するために一意のキーを管理しないため、Adobe Campaign StandardからのIDを活用する必要があります。This ID (**ACS ID**) can be exported as well as used as a reconciliation key while updating the data. For more information, refer to the [detailed documentation](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* FTPプロトコルは廃止されています。代わりに、SFTPを使用する必要があります。既存の実装をブロックしないため、FTPの既存の設定は以前と同様に機能しますが、新しいアクティビティではこのオプションは表示されません。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* 新しいアラート条件を作成して、アラート通知通知で使用することができます。For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* 通知通知通知には新しいデザインが用意されており、配信されるダッシュボードのユーザーエクスペリエンスが改善されました。
* Now when a routing external account is disabled, a warning is displayed in the impacted deliveries (email, SMS and push) and the **Preview** button is hidden in these deliveries.
* 件名行で動的テキストが有効になっている場合、電子メールコンテンツのA/Bテストのプレビューでエラーが発生する問題を修正しました。

#### Transactional messages {#transactional-messages}

* トランザクションメッセージの送信後3日間など、フォローアップメッセージを送信するタイミングを定義できるようになりました。For more information, refer to the [detailed documentation](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* イベントにリンクされたトランザクションメッセージを送信する際に、日付を定義できるようになりました。
* 受け取ったイベントおよび処理されたイベントにリンクされているプロファイルを削除した後に、フォローアップメッセージを含むワークフローを実行するとSQLエラーが発生する問題を修正しました。
* イベントにリンクされているプロファイルを削除できないエラーを修正しました。
* トラッキングされたリンクのリダイレクトが動作しない可能性がある問題を修正しました。
* 電子メールまたはSMSメッセージの特定のリンクのトラッキングを無効にできない問題を修正しました。

#### Reports {#reports-1}

* **ホットクリック** レポートが改善されました。また、配信で定義された各条件コンテンツに従ってホットクリックを表示したり、定期配信またはトランザクションメッセージの実行ごとにホットクリックを表示したりできます。For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* 強制隔離指標が正しいデータを取得できない問題を修正しました。
* カレンダーウィジェットに新しいプリセット時間枠が追加されました。
* [動的レポート指標](../../reporting/using/indicator-calculation.md) と [キャンペーンのKPI](../../sending/using/confirming-the-send.md) （送信メッセージのダッシュボードに表示される）が、より一貫性のある形で整列されました。
* debian7でパイプラインがクラッシュする可能性がある問題を修正しました。

#### Workflows {#workflows-1}

* インポートされたファイルのリテンションが動作しない可能性がある問題を修正しました。

#### Integrations {#integrations-1}

* Analytics&amp; Campaign統合でeVarおよびイベントがサポートされるようになりました。
* 放棄された買い物かごのコンテンツを含む電子メールを送信する際に、買い物かごから削除された要素のペイロードパラメータがオプションになりました。

#### Profiles and audiences {#profiles-and-audiences-1}

* Adobe Campaignで、アクティブプロファイル数を表示するレポートが提供されるようになりました。このレポートはあくまでも有用な情報です。課金に直接影響することはありません。For more information, refer to the [detailed documentation](../../audiences/using/active-profiles.md).
* プロファイルおよびサービスAPIの使用時にプロファイルをサービスに購読できない問題を修正しました。

## Release 17.7 - July 2017 {#release-17-7---july-2017}

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
   <td> Multilingual email and SMS deliveries<br /> </td> 
   <td> 自動的にセグメント化された顧客の好みの言語に基づいて、複数言語の電子メールおよびSMS配信を定義して実行します。言語および個々のレベルまでのすべての配信のパフォーマンスについてレポートします。<br /> 多くの企業は、自宅および海外での成長に伴い、複数言語でコンテンツを配信することに直面しています。そのため、ローカライズされたメッセージ配信の合理化は、複数の企業にとって効果的な顧客コミュニケーション戦略の重要な部分です。企業内の複数言語の会社、また、顧客がどこに居住しているかにかかわらず、コンテンツを舌レベルでさらにパーソナライズしたいと考えている企業もあります。For more information, refer to the <a href="../../channels/using/creating-a-multilingual-email.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> Adobe Campaign Standard内での重要なシステムアクティビティに関する通知を受信します。例えば、外出中の配信の進行状況や、ワークフローがエラーになったときに通知されます。<br /> リアルタイム通知は、関連する関係者を保持し、アプリケーション内からアクティビティ通知を即時かつ直接操作できるユーザーに提供します。チームの結果は、キャンペーンの高度性、効率性、スムーズな実行に役立ちます。For more information, refer to the <a href="../../administration/using/sending-internal-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery Alerting<br /> </td> 
   <td> Adobe Campaign Standardで直接通知を表示するだけでなく、Adobe Campaignでは電子メール通知システムも提供され、ユーザーまたは重要なシステムアクティビティの外部者に電子メールアラートをトリガーできます。カスタマイズ可能なアラートおよびダッシュボードを作成、管理および受け取り、配信の成功または失敗を追跡します。<br /> Adobe Campaign配信は、電子メールやダッシュボード経由で配信の実行ステータスについて自動的に通知される会社内のすべてのAdobe Campaignユーザーを保持することにより、効率的に実施できます。For more information, refer to the <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encrypted Declared ID in Datasources<br /> </td> 
   <td> 暗号化された連絡先情報（電子メールアドレスまたは電話番号）を宣言IDとして使用して、Campaignの既存のプロファイルを必要とせずに電子メールおよびSMSトリガーを送信します。暗号化された宣言IDはAdobe Campaign Standardでデコードできるので、以前不明な連絡先を含む他のExperience Cloudソリューションからオーディエンスを受信するときに、キャンペーンが新しいマーケティング可能なプロファイルを作成できるようになりました。<br /> 電子メール&amp; SMSの両方にわたってリアルタイムで顧客および不明な見込み客をターゲットにし、既存の顧客ベースの忠誠度を向上し、新規顧客を獲得します。見込み客がAdobe Campaignでこれらのインサイトを認証および活用すると、ファーストパーティcookieデータを（Adobe Audience Manager*から）最大限に活用できます。<br /> * Adobe Audience Managerが必要です。For more information, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> キャンペーンデータをAdobe Analyticsと共有して、コンバージョンによって他のマーケティングや広告の取組みと共に電子メールマーケティング指標を測定し、クリック前の行動とクリック前の行動を統一します。<br /> 全体的なパフォーマンスを直接追跡し、Analyticsの外部プログラムとの同期を解除します。この統合ビューから学習をキャンペーンに適用します。最終的には、オープン、クリックスルー率およびコンバージョン率が向上し、売上高とキャンペーン全体のパフォーマンスが向上します。<br /> Adobe Analyticsが必要です。For more information, refer to the <a href="../../integrating/using/about-campaign-analytics-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> Sender to Senderの情報を組み込むDirect Mailプロバイダーとのフラットなファイル交換がサポートされるようになりました。ダイレクトメールチャネルに対するこの機能強化により、対応する郵便番号を将来の通信から除外することができます。<br /> これにより、マーケティング担当者は、間違ったアドレスを通知し、他のチャネル経由で顧客に関与して、住所の更新を促すことができます。また、マーケティング担当者が不正なアドレスにメールを送信しないように、マーケティング担当者が無駄なマーケティング費用を削減します。<br /> ダイレクトメールはアドオンチャネルとして利用できます。For more information, refer to the <a href="../../channels/using/return-to-sender.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general}

* ユーザーのエクスポートリストが表示される問題を修正しました。Now only users with the **[!UICONTROL Export]** role are allowed to.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* Fixed an issue with the **updateDeliveryExecInfo** workflow that set the **To deliver** indicator to 0 for SMS deliveries.
* In the **Advanced parameters** of the delivery template’s properties, the **Routing** drop-down list now only displays external accounts corresponding to the template message type. 例えば、電子メール配信テンプレートには電子メールの外部アカウントのみが表示されます。
* Fixed an issue with the **[!UICONTROL Text]** preferred email format defined for test profiles.
* 配信のスケジュール定義画面でデフォルトのタイムゾーンを選択すると、JavaScriptエラーが発生する問題を修正しました。
* トラップの送信時にトラップが表示されない問題を修正しました。
* 配信作成ウィザードのテンプレート選択画面で、フォローアップおよびA/Bテストテンプレートがデフォルトで非表示になりました。For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* ユーザーが配信を送信できる問題を修正しました。Now only users with the **[!UICONTROL Start deliveries]** role are allowed to. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

#### Push notifications {#push-notifications-1}

* **キャンペーントラッキングエンドポイント** URLのレポートができなかった問題を修正しました。
* Androidデバイスでプッシュ通知タイトルを表示できない問題を修正しました。
* プッシュ通知にタイトルのみが含まれている（およびメッセージ本文の何もしない）場合に、iOSデバイスでプッシュ通知が表示されない問題を修正しました。
* 配信される配信のメディア添付URLが追跡され、ビデオや画像が配信に埋め込まれない問題を修正しました。MediaAttachmentURLタイプのURLのトラッキングが、プッシュ通知のデフォルトで非アクティブになりました。

#### Reports {#reports-2}

* グラフとテーブル間で値が異なる問題を修正しました。
* プッシュ通知値が電子メール値として表示される問題を修正しました。
* キャンペーン外で配信が作成されたときに、値が不明と表示される問題を修正しました。
* SMSレポートデータがモバイルアプリケーションデータとして表示される問題を修正しました。

#### Workflows {#workflows-2}

* ワークフローログ（時間とテキスト検索）をフィルターできます。For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* 送信前の確認を非アクティブにするために、ワークフロー配信でオプションを使用できるようになりました。
* 定期配信の作成ウィザードでアウトバウンドトランジションを設定できない問題を修正しました。
* 多数の値を持つ列挙を持つカスタムリソースフィールドに基づいてワークフロークエリーアクティビティを使用すると発生していた問題を修正しました

## Release 17.5 - May 2017 {#release-17-5---may-2017}

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
   <td> Direct mail<br /> </td> 
   <td> デジタル障壁を破って、Adobe Campaign Standardの最初のオフラインチャネルであるDirect Mailに接続します。この機能により、ダイレクトチャネルキャンペーンの一部としてダイレクトメールプロバイダーに必要なファイルをパーソナライズして生成できます。ダイレクトメールを利用することで、顧客を再び惹きつけたり、説得力のあるタッチタッチポイントを使用して顧客をアプリ、Webサイト、店舗に誘導したりすることができます。<br /> 詳しくは、 <a href="../../channels/using/about-direct-mail.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> 電子メールBCCを使用すると、個別の受信者に送信される一意の電子メールメッセージを保存できるので、ブランドはそれらのメッセージをアーカイブできます。すべての電子メールにBCC電子メールアドレスを追加することで、Adobe Campaign Standardのユーザーは、この機能を使用して各電子メールの正確なコピーを保持できます。これは金融サービス業界にとって一般的な法的要件であり、顧客サービスセンターはリアルタイムでの競合解決の支援に役立ちます。<br /> 詳しくは、 <a href="../../administration/using/configuring-email-channel.md#archiving-emails">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### Interface updates {#interface-updates}

* In the top bar, the **[!UICONTROL Timeline]** link has been removed and replaced with a link to **[!UICONTROL Programs & Campaigns]** .

#### Emails and SMS messages {#emails-and-sms-messages}

* **[!UICONTROL Retry in progress]** 配信ステータスに間違った色が表示される問題を修正しました。色が青ではなくグレーになりました。

#### Workflows {#workflows-3}

* **[!UICONTROL Transfer file]** アクティビティで実行するアクションを変更すると発生していた問題を修正しました。

#### Reports {#reports-3}

* **[!UICONTROL Spam]****[!UICONTROL Spam rate]** およびインジケーターの計算が変更されました。
* **[!UICONTROL Bounce]** より正確な結果を得るために、指標が改善されました。

#### Push notifications {#push-notifications-2}

* プロファイルのマーケティング履歴でプッシュイベントをクリックできなかった問題を修正しました。
* ワークフローでのプッシュ通知の使用が改善されました。

## Release 17.4 - April 2017 {#release-17-4---april-2017}

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
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> 電子メールまたはランディングページの編集時に、コンテンツエディターで直接画像を強調するために、Creative SDKが提供する全機能にアクセスできるようになりました。<br /> この機能では、追加のCreative Cloudソリューションの獲得は必要ありません。<br /> 詳しくは、 <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional push notifications<br /> </td> 
   <td> モバイルアプリケーションチャネルがAdobe Campaignのトランザクションメッセージング機能に追加されました。トランザクションメッセージで3つのチャネルがサポートされるようになりました。電子メール、SMS、プッシュ通知<br /> 詳しくは、 <a href="../../channels/using/transactional-push-notifications.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Recurring push notifications<br /> </td> 
   <td> ワークフローで定期的なプッシュ通知を設定できるようになりました。新しいコンテンツやプロモーションのチェックアウトに週別リマインダーなどの定期的な更新を期待する状況で、繰り返しプッシュ通知を使用できます。<br /> 詳しくは、 <a href="../../automating/using/push-notification-delivery.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> Amazon Simple Storage Service（S3）コネクターを使用して、データをAdobe Campaignにインポートまたはエクスポートできるようになりました。ワークフローアクティビティで設定できます。設定は外部アカウントで実行されます。<br /> 詳しくは、 <a href="../../administration/using/external-accounts.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration live<br /> </td> 
   <td> Adobe CampaignとDreamweaverの統合がライブになりました。これは、正式にリリースされたDreamweaver（17.0.2）の正式なリリースで機能します。<br /> これには、ここからAdobe Campaign統合拡張機能をインストールする必要があります。 <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> 詳細については、この <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">ビデオ</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### Platform {#platform-2}

* メモリ消費の問題を修正しました。

#### Emails and SMS messages {#emails-and-sms-messages-1}

* メッセージをプレビューする際に、コンテンツを最新の変更と適切に同期できない問題を修正しました。
* MXまたはドメイン電子メール処理ルールが作成または削除できない問題を修正しました。
* 複数のエイリアスを持つ電子メールを送信できない問題を修正しました。
* トラップの送信ログにトラップログが表示されない問題を修正しました。
* コンテンツにURLがない配信のトラッキングURLを表示するとエラーが発生する問題を修正しました。
* 送信されたメッセージで画像のサイズ属性が正しく適用されない問題を修正しました。

#### Transactional messages {#transactional-messages-1}

* rutevinisoidフィールドは、トランザクションメッセージテンプレートにパーソナライゼーションフィールドとして公開されなくなりました。

#### Landing pages {#landing-pages}

* We have optimized the **[!UICONTROL by email]** filter used in landing pages to reconcile new subscribers with database profiles.
* フォーム設定でBooleanフィールドを使用すると、チェックボックスの代わりに無料テキスト入力が表示される問題を修正しました。
* ランディングページのサムネールが生成できない問題を修正しました。

#### Workflows {#workflows-4}

* Fixed a display error when editing an **[!UICONTROL End]** or **[!UICONTROL External Signal]** activity (on Safari only).
* Improved the error message displayed when editing a **[!UICONTROL Read Audience]** activity containing an erroneous audience.
* 購読アクティビティの実行時にSQLエラーが発生する可能性がある問題を修正しました。

#### Integrations {#integrations-2}

* 目標地点データ:場所の購読者のカウント時に発生するエラーを修正しました。

#### Audiences and queries {#audiences-and-queries}

* クエリエディターのコレクションで合計集計と平均集計が使用されない問題を修正しました。
* フィルターのリソースを変更した後、クエリエディターがリロードされない問題を修正しました。

#### Reports {#reports-4}

* テーブルで複数行を選択すると、開く割合指標が正しく計算されない問題を修正しました。
* 指標のみが整数値として表示されるエラーを修正しました。指標を小数で表示できるようになりました。

#### Push notifications {#push-notifications-3}

* MCPNSでの作成に失敗したモバイルアプリにリンクされたAndroidアプリケーションを作成するときにエラーメッセージが表示されなかった問題を修正しました。
* ユーザーが無音通知にサウンドを追加できる問題を修正しました。

## Release 17.2 - March 2017 {#release-17-2---march-2017}

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
   <td> Dynamic reporting<br /> </td> 
   <td> 動的レポート機能により、完全にカスタマイズ可能なリアルタイムのビジネスレポートが生成されます。視覚的な動的ピボットテーブルとグラフィックに基づいて、この機能を使用すると、変数やディメンションをドラッグ&amp;ドロップして、マーケティングキャンペーンの効率と効果を分析できます。また、動的レポートを使用すると、独自のビジネスレポートを最初から作成して保存することもできます。<br /> 詳しくは、 <a href="../../reporting/using/about-dynamic-reports.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration (Labs)<br /> </td> 
   <td> Adobe CampaignとDreamweaverの統合により、アドビソリューションの電子メールキャンペーンを作成するための統合プロセスが提供されるようになりました。<br /> DreamweaverでAdobe Campaignの電子メールを編集し、両方のソリューション間でシームレスにコンテンツを同期できます。<br /> 最初のリリースでは、統合は「ラボ」機能として利用でき、Dreamweaver Pre Release Betaでのみ機能します。アクティブ化する場合は、AC-DW-integration@adobe.comまでお問い合わせください。<br /> 詳しくは、この <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">ビデオ</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> 配信レベルで、またはワークフローを使用して、受信者ごとのカスタム送信時間を手動で定義できるようになりました。<br /> 2つの新しいオプションを使用できます。 <br /> 
    <ul> 
     <li> すべての受信者は、タイムゾーンを考慮してメッセージを受け取ります。 </li> 
     <li> 各受信者は、数式によって定義された日時にメッセージを受け取ります。 </li> 
    </ul> For more information, refer to the <a href="../../sending/using/optimizing-the-sending-time.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications New capabilities<br /> </td> 
   <td> The push notification channel has been enhanced with several new capabilities:<br /> 
    <ul> 
     <li> 新しいオーサリングインターフェイス </li> 
     <li> サイレント通知 </li> 
     <li> インタラクティブなプッシュ </li> 
     <li> リッチコンテンツのサポート </li> 
     <li> ペイロードサイズ計算ツール </li> 
    </ul> For more information, refer to the <a href="../../channels/using/about-push-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Signal activity<br /> </td> 
   <td> Trigger a workflow from another workflow using the new <span class="uicontrol">Signal</span> activity.<br /> 1つのワークフローを別のワークフローから開始することで、より複雑な顧客ジャーニーをサポートできるようになりました。顧客の遍歴を監視し、問題が生じた場合に対応することができます。<br /> いくつかのワークフローアクティビティが更新されました。<br /> 
    <ul> 
     <li> <span class="uicontrol">終了</span> アクティビティ:新しいタブでは、このアクティビティの実行後にトリガーするワークフローを指定できます。 </li> 
     <li> <span class="uicontrol">データ</span> アクティビティの更新:新しい空のアウトバウンドトランジションを使用して <strong>、別のワークフローをトリガーする終了</strong> アクティビティを追加します。空のアウトバウンドトランジションにはデータがなく、システム上の不要なスペースを消費しません </li> 
    </ul> For more information, refer to the <a href="../../automating/using/external-signal.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Read audience activity<br /> </td> 
   <td> 既存のオーディエンスを使用してターゲット化プロセスを開始し、1つのアクティビティで簡単に選択して絞り込むことができます。<br /> 詳しくは、 <a href="../../automating/using/read-audience.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest data<br /> </td> 
   <td> 目標地点データは、Adobe CampaignとMobileのAdobe Analyticsを統合します。A brand can collect data from users' mobile locations - called <strong>Points of Interest</strong> - when users open the brand's app. これにより、ブランドは、ユーザーの所在地に基づいてパーソナライズされたメッセージを送信するためにAdobe Campaignワークフローを活用できます。このチャネルはMobileコアサービスのSDKを利用します。<br /> この機能を使用するには、有料ソリューションであるMobile for Mobileが必要です。<br /> 詳しくは、 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> 任意のレベルでリンクされたリソースをAPIで使用できるようになりました。<br /> 詳しくは、 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-1}

* 配信ログのエクスポート時にプロファイルデータを追加できるようになりました。

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain selected even after unchecking it and saving the delivery.
* トランザクション電子メールの公開を停止できない問題を修正しました。
* 配信をプレビューする前に、コンテンツを最新の変更と適切に同期できない問題を修正しました。

#### Landing pages {#landing-pages-1}

* ランディングページのコンテンツをクリックしたときにユーザーが編集できないエラーを修正しました。

#### Workflows {#workflows-5}

* **[!UICONTROL Load file]** アクティビティの拒否トランジションのコンテンツを読み取れない可能性がある問題を修正しました。
* Fixed an issue that prevented swapped columns to be properly taken into account when configuring a **[!UICONTROL Load file]** activity.

## Release 17.1 - January 2017 {#release-17-1---january-2017}

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
   <td> Log export for external reporting<br /> </td> 
   <td> 配信ログや追跡ログなどのログをエクスポートして、好みのレポートまたはBIツールで処理できます。増分クエリーを使用して単純なワークフローを使用すると、新しいログの定期エクスポートを自動化できます。<br /> リソースピッカーからのログリソースの可用性に加え、 <a href="../../automating/using/incremental-query.md">増分クエリ</a> および <a href="../../automating/using/extract-file.md">ファイル</a> アクティビティの抽出に関する機能強化が行われました。<br /> 
    <ul> 
     <li> <span class="uicontrol">増分クエリー</span> で、日付フィールドを使用して新しいデータまたは更新されたデータを取得できるようになりました。以前は、前回の実行以降に更新されたものであっても、以前の実行からのすべての結果が自動的に除外されていました。 </li> 
     <li> <span class="uicontrol">抽出ファイル</span> で、IDではなく列挙値のラベルをエクスポートできるようになりました。 </li> 
    </ul> これらのアクティビティは、すべての地域および組織単位にアクセスできる管理者が利用できます。<br /> ログの書き出しについて詳しくは、 <a href="../../automating/using/exporting-logs.md">詳細なドキュメント</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketing capabilities for transactional messages<br /> </td> 
   <td> マーケティング担当者は、顧客のマーケティングプロファイルに基づいてトランザクションメッセージを送信できるようになりました。This allows them to:<br /> 
    <ul> 
     <li> Apply marketing typology rules such as <span class="uicontrol">Blacklisted address</span> . </li> 
     <li> メッセージ内に購読解除リンクを含めます。 </li> 
     <li> トランザクションメッセージをグローバル配信レポートに追加します。 </li> 
     <li> 顧客の遍歴のトランザクションメッセージを活用します。 </li> 
    </ul> For more information, refer to the <a href="../../channels/using/profile-transactional-messages.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> The Transactional Messaging API is now available through <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, making it easier to use and to monitor:<br /> 
    <ul> 
     <li> adobe. ioプラットフォームレポートから利益を得ることができます。 </li> 
     <li> IPホワイトリストではなくadobe. ioトークンベースの認証を使用して認証が実行されるようになり、セキュリティプロセスをシンプル化しました。 </li> 
     <li> すべてのAPIが単一のプラットフォームに統合され、プロファイルおよびサービスAPIを既にサポートしている場合、統合にトランザクションメッセージング機能を追加するよりも簡単になりました。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-2}

* **[!UICONTROL Access authorization]** オプションはランディングページのプロパティに戻りました。
* 古い画像が正しい画像ではなくレンダリングされていた問題を修正しました。これは、配信またはランディングページのコンテンツ定義でソース画像が更新された場合に発生していました。
* 既存のSFTP外部アカウントの特定のフィールドをユーザーが編集できない問題を修正しました。
* UIの問題をいくつか修正しました。例えば、ユーザーがプロファイル属性を編集し、UIに問題なく変更を保存できるようになりました。

#### Emails and SMS messages {#emails-and-sms-messages-3}

* HTMLコンテンツを含む配信テンプレートに関する問題を修正しました

#### Push notifications {#push-notifications-4}

* ポストバックがAdobe Campaignサーバーへのポストバックを妨げている可能性がある問題を修正しました。
* Fixed an issue that may have prevented **[!UICONTROL Play a sound]** and **[!UICONTROL Custom fields]** to be taken into account for Android.
* 文字列に使用する余分なエスケープ文字が、文字に追加されていた問題を修正しました。
* 購読者の登録トークンがブラックリストに登録されると、Adobe Campaignの申込者リストの中で対応するステータスがすぐに更新されるようになりました。

#### Workflows {#workflows-6}

* イベントリソース（例えば、rtEvent）に対するクエリーのプレビューが妨げられていた可能性がある問題を修正しました。
* **[!UICONTROL Load file]** アクティビティによって生成された拒否ファイルを、アウトバウンドトランジションで取得し、次のアクティビティで処理できるようになりました。For example, upload the reject file via an SFTP server using **[!UICONTROL Transfer file]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** アクティビティを10分ごとに複数回トリガーするように設定できなくなりました。
* Fixed an issue that may have prevented **[!UICONTROL Use common columns]** from working properly in an **[!UICONTROL Union]** activity.

#### Integrations {#integrations-3}

* Adobe Campaignでイベントトリガーを展開するとエラーが発生する可能性がある問題を修正しました。このエラーは、Adobe Marketing Cloudの破棄トリガーに"30日間の再訪」メタデータが追加された場合に発生していました。
* Peopleコアサービスからオーディエンスをインポートすると、技術ワークフローがTargetディメンションフィールドをクリアする可能性がある問題を修正しました。後続のクエリーでインポートされたオーディエンスを取得できませんでした。
* Fixed an issue that may have caused the **[!UICONTROL Save audience]** activity of a workflow to fail when the option **[!UICONTROL Share in Adobe Marketing Cloud]** was checked.

