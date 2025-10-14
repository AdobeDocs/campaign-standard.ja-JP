---
title: Microsoft Dynamics 365 統合の使用
description: Microsoft Dynamics 365 をCampaign Standardと統合して使用する方法を学ぶ
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 1%

---

# Microsoft Dynamics 365 統合の使用

Microsoft Dynamics 365 とのAdobe Campaign Standard統合で実行されるデータフローはいくつかあります。 これらのフローについて詳しくは、[&#x200B; このページ &#x200B;](../../integrating/using/d365-acs-self-service-app-workflows.md) を参照してください。

データフローの詳細については、このドキュメントの [&#x200B; データフロー &#x200B;](#data-flows) の節を参照してください。

## Adobe Campaign Standardのユーザーエクスペリエンス

Microsoft Dynamics 365 で連絡先が作成、変更または削除されると（削除が有効になっている場合）、その連絡先はCampaign Standardに送信されます。 これらの連絡先は、Campaign のプロファイル画面に表示され、マーケティングキャンペーンでターゲットに設定できます。 以下のプロファイル画面を参照してください。

![](assets/MSdynamicsACS-usage1.png)

Campaign でオプトアウト属性を変更しても、「**一方向（Microsoft Dynamics 365 に対するキャンペーン）**」または「**双方向**」を選択し、その特定の属性を正しくマッピングしていると、Dynamics 365 に反映されます。

## Microsoft Dynamics 365 ユーザーエクスペリエンス

エグレスの場合、次のメールマーケティングイベントが Campaign から Dynamics 365 に送信され、Microsoft Dynamics 365 のタイムライン ビューにカスタムアクティビティとして表示されます。

* Adobe Campaign メール送信

* Adobe Campaign メールの開封

* Adobe Campaign メール URL のクリック

* Adobe Campaign E メールバウンス

連絡先のタイムラインを表示するには、Dynamics 365 ドロップダウンメニューの Sales Hub をクリックして、連絡先リストに移動します。 次に、左側のメニューバーで「連絡先」をクリックし、連絡先を選択します。

>[!NOTE]
>
>Adobe Campaignこれらのイベントを表示するには、AppSource のMicrosoft Dynamics 365 **アプリの** Microsoft Dynamics 365 インスタンスにインストールする必要があります。 [詳細情報](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

以下に、「Dynamics ユーザー」の連絡先画面のスナップショットを示します。 タイムライン ビューでは、キャンペーン名「2019LoyaltyCamp」と配信名「DM190」に関連付けられたメールが Dynamics ユーザーに送信されたことがわかります。 Dynamics ユーザーがメールを開き、メールの URL をクリックしました。これらのアクションは両方ともイベントを作成し、以下も表示されます。 右隅を見ると、関係アシスタント（RA）カードが表示されます。現在は、クリックされた URL を追跡するタスクが含まれています。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Dynamics ユーザーのタイムライン ビューのクローズアップについては、以下を参照してください。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

次に、リレーションシップ アシスタント（RA）カードのクローズアップを示します。 AppSource アプリには、Adobeメール URL のクリックイベントを監視するワークフローが含まれています。 このイベントが発生すると、タスクが作成され、期限が設定されます。 これにより、タスクが RA カードに表示され、追加の可視性が得られます。 同様のワークフローが、Adobeのメールバウンスイベントにも存在し、無効なメールアドレスを紐付けするためのタスクを追加します。 これらのワークフローは、ソリューションでオフにできます。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

送信イベントの件名をクリックすると、以下のようなフォームが表示されます。 オープンイベントとバウンスイベントのフォームは似ています。

![](assets/do-not-localize/mirror_page_url_send.png)

メール URL のクリックイベント用のフォームは、クリックされた URL の属性を追加します。

![](assets/do-not-localize/mirror_page_url_click.png)

以下は、属性のリストと説明です。

* **件名**：イベントの件名です。メール配信のキャンペーン ID と配信 ID で構成されます

* **所有者**: プロビジョニング後の手順で作成されたアプリケーションユーザー

* **関連**：連絡先の名前

* **キャンペーン名**:Campaign Standardのキャンペーン ID

* **配信名**:Campaign Standardの配信 ID

* **送信日/開封日/クリック日/バウンス日**：イベントが作成された日時

* **トラッキング URL**：クリックされた URL

* **ミラーページ URL**：送信、開封、クリックまたはバウンスされたメールのミラーページの URL。 メールミラーページの有効期限は、対応する Campaign メールチャネルアクティビティの設定画面で変更できます。 [詳細情報](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>オプトアウトの場合、Microsoft Dynamics 365 でオプトアウト属性を変更すると、**一方向（Microsoft Dynamics 365 に対するキャンペーン）または** 双方向 **オプトアウトの設定を選択し** その特定の属性が正しくマッピングされていれば、Campaign に反映されます。

## データフロー {#data-flows}

### 連絡先とカスタムエンティティの入口

新規、更新、削除されたレコード（メモ：削除を有効にする必要があります）は、Microsoft Dynamics 365 の連絡先テーブルから Campaign のプロファイルテーブルに送信されます。

テーブルマッピングは、統合アプリケーション UI で設定して、Microsoft Dynamics 365 のテーブル属性を Campaign のテーブル属性にマッピングできます。 必要に応じて、テーブルマッピングを変更して属性を追加または削除できます。

データフローの最初の実行は、マッピングされたすべてのレコード（「非アクティブ」とマークされたレコードを含む）を転送するように設計されています。その後、統合は増分更新のみを処理します。 ただし、データが再生されたり、フィルターが設定されたりすると、例外が発生します。基本的な属性ベースのフィルタリングルールを設定して、Campaign に同期するレコードを決定できます。

基本的な置き換えルールは、統合アプリケーション UI で設定して、属性値を別の値（例：「#00FF00」は「緑」、「1 は「F」）に置き換えることができます。

レコードの量に応じて、最初のデータ転送に Campaign SFTP ストレージを使用する必要がある場合があります。 [詳細情報](#initial-data-transfer)。

連絡先の入力を機能させるには、キャンペーンプロファイル テーブル属性 externalId に Dynamics 365 の連絡先属性 contactId を設定する必要があります。 Campaign カスタムエンティティには、Dynamics 365 の一意の ID 属性も入力する必要があります。ただし、この属性は、任意の Campaign カスタムエンティティ属性に保存できます（つまり、externalId である必要はありません）。

>[!NOTE]
>
>カスタムエンティティを入力するには、同期されたカスタムエンティティの Dynamics 365 内で変更追跡を有効にする必要があります。

#### カスタムエンティティ

[Microsoft Dynamics 365 とAdobe Campaign Standardの統合 &#x200B;](../../integrating/using/d365-acs-get-started.md) は、カスタムエンティティをサポートしており、Dynamics 365 のカスタムエンティティを Campaign の対応するカスタムリソースに同期できます。

カスタムリソースの新しいデータは、セグメント化やパーソナライゼーションなど、いくつかの目的で使用できます。

統合では、リンクされたテーブルとリンクされていないテーブルの両方がサポートされます。 リンクは最大 3 つのレベル （レベル 1-> レベル 2-> レベル 3）までサポートされます。

>[!IMPORTANT]
>
>Campaign のカスタムリソースレコードに個人情報が含まれている場合は、特定の推奨事項が適用されます。 詳しくは、[この節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data)を参照してください。
>

カスタムエンティティデータフローを設定する場合は、次の点に注意することが重要です。

* Campaign のカスタムリソースの作成と変更は慎重に行うべき操作で、エキスパートユーザーのみが実行する必要があります。
* カスタムエンティティのデータフローでは、同期されたカスタムエンティティの Dynamics 365 内で変更追跡を有効にする必要があります。
* 統合の並列処理が原因で、親およびリンクされた子レコードが Dynamics 365 でほぼ同時に作成された場合、その親レコードよりも前に新しい子レコードを Campaign に書き込める可能性がわずかながらあります。

* **1 カーディナリティ シンプルリンク** オプションを使用して親と子が Campaign 側でリンクされている場合、親レコードが Campaign に到達するまで、子レコードは（UI または API 経由で）非表示になりアクセスできなくなります。

* （Campaign での **1 基数のシンプルリンク** の場合）子レコードが Dynamics 365 で更新または削除され、Campaign に親レコードが表示される前にその変更が Campaign に書き込まれる場合（可能性は低いですが、リモートで表示される可能性があります）、その更新または削除は Campaign で処理されず、エラーが発生します。 更新の場合、更新されたレコードを同期するには、該当するレコードを Dynamics 365 で再度更新する必要があります。 削除の場合、Dynamics 365 には削除または更新するレコードがないので、問題のレコードはキャンペーン側で個別に処理する必要があります。

* 非表示の子レコードがあり、それにアクセスする方法がないと思われる状況になった場合は、カーディナリティ リンクタイプを一時的に **0 または 1 のカーディナリティ シンプルリンク** に変更して、それらのレコードにアクセスできます。

Campaign カスタムリソースのより包括的な概要については、[&#x200B; この節 &#x200B;](../../developing/using/key-steps-to-add-a-resource.md) を参照してください。

### メールマーケティングイベントフロー{#email-marketing-event-flow}

メールマーケティングイベントは、Campaign からMicrosoft Dynamics 365 に送信され、タイムラインビューに表示されます。

サポートされるマーケティングイベントタイプ：
* 送信 – 受信者に送信されるメール
* 開く – 受信者が開いたメール
* クリック – 受信者がクリックしたメール内の URL
* バウンス – 受信者へのメールにハードバウンスが発生した

次のイベント属性が Dynamics 365 内に表示されます。
* マーケティングキャンペーン名
* メール配信名
* タイムスタンプ
* メールのミラーページ URL
* クリックされた URL （クリックイベントのみ）

メールマーケティングイベントは、タイプ（送信、開く、クリック、バウンス）ごとに有効/無効にできるので、選択したイベントタイプのみが Dynamics 365 に渡されます。

### オプトアウトフロー {#opt-out-flow}

オプトアウト（ブロックリストなど）の値はシステム間で同期されます。オンボーディング時に次のオプションから選択できます。

* **一方向（Microsoft Dynamics 365 から Campaign）**:Dynamics 365 は、オプトアウトの情報源です。 オプトアウト属性は、Dynamics 365 からCampaign Standardに一方向に同期されます」
* **単方向（Microsoft Dynamics 365 に対する Campaign）**：オプトアウトの情報源はCampaign Standardです。 オプトアウト属性は、Campaign Standardから Dynamics 365 に一方向に同期されます
* **双方向**:Dynamics 365 とCampaign Standardはどちらも信頼できる情報源です。 オプトアウト属性は、Campaign Standardと Dynamics 365 間で双方向に同期されます

または、システム間のオプトアウト同期を管理する別のプロセスがある場合、統合のオプトアウトデータフローを無効にできます。

>[!NOTE]
>
>統合アプリケーション UI では、**一方向（Microsoft Dynamics 365 から Campaign）** および **双方向** オプトアウトのユースケースが、別のオプトアウトワークフローで設定されます。 [詳細情報](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>**一方向（Campaign からMicrosoft Dynamics 365）** オプトアウトのユースケースは例外で、入口（プロファイルへの連絡）ワークフロー内で設定されます。
>

ビジネス要件は企業間で異なる場合があるので、オプトアウトフローマッピングは顧客が指定する必要があります。 キャンペーン側では、オプトアウトマッピングに使用できるのは OOTB オプトアウト属性のみです。

* ブロックリスト
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

Dynamics 365 では、ほとんどのオプトアウトフィールドに「dono」というプレフィックスが付きますが、データタイプに互換性がある場合は、オプトアウトのために他の属性を利用することもできます。

### 初回のデータ転送 {#initial-data-transfer}

Microsoft Dynamics 365 から取り込むレコードの数によっては、最初のデータ転送に時間がかかる場合があります。 最初のデータ転送が完了すると、統合機能によって増分更新が取得されます。
