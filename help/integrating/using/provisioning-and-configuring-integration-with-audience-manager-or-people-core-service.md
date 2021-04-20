---
solution: Campaign Standard
product: campaign
title: Audience Manager または People コアサービスとの統合のプロビジョニングと設定
description: 'Adobe Experience Cloudの様々なソリューションで開始共有オーディエンスやセグメントにAudience Manager/ユーザーコアサービスを統合する方法について説明します。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 40%

---


# Audience Manager または People コアサービスとの統合のプロビジョニングと設定{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Adobe CampaignのAudience ManagerとPeopleコアのプロビジョニングと設定には、2つの手順があります。[リクエストをAdobe](#submitting-request-to-adobe)に送信し、[Adobe Campaign](#configuring-the-integration-in-adobe-campaign)で統合を設定します。

## アドビへの依頼の送信 {#submitting-request-to-adobe}

Audience Manager(AAM)またはPeopleコアサービスの統合により、オーディエンスやセグメントの読み込みと書き出しをAdobe Campaignで実行できます。

この統合を最初に設定する必要があります。この統合のプロビジョニングをリクエストするには、次の情報を記載のうえ、[Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) まで E メールを送信します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>依頼のタイプ：</strong><br /> </td> 
   <td> AAM／People コアサービスと Campaign の統合の設定 </td> 
  </tr> 
  <tr> 
   <td> <strong>組織名：</strong><br /> </td> 
   <td> 所属する組織の名前 </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS Org ID</strong><br /> </td> 
   <td> 所属する組織の IMS 組織 ID。<br> IMS 組織 ID は、Adobe Experience Cloud の管理メニューで確認できます。これは、Adobe Experience Cloud への初回接続時に付与されるものです。 </td> 
  </tr> 
  <tr> 
   <td> <strong>環境：</strong><br /> </td> 
   <td> 例：本番環境 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM または People コアサービス</strong><br /> </td> 
   <td> 例： Adobe Audience Managerプロビジョニングチームに Audience Manager のライセンスを所有しているかどうかを確認してください。</td> 
  </tr> 
  <tr> 
   <td> <strong>宣言済み ID または訪問者 ID</strong><br /> </td> 
   <td> 例：宣言済み ID </td> 
  </tr> 
  <tr> 
   <td> <strong>追加情報</strong><br /> </td> 
   <td> 役に立つ情報またはコメント（ある場合） </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Campaign{#configuring-the-integration-in-adobe-campaign}での統合の設定

このリクエストを提出した後、Adobeは統合のプロビジョニングに進み、お客様に連絡して、設定の最終決定に必要な詳細と情報を提供します。

* [手順 1：Adobe Campaign での外部アカウントの設定または確認](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [手順2:データソースの設定](#step-2--configure-the-data-sources)
* [手順 3：キャンペーントラッキングサーバーの設定](#step-3--configure-campaign-tracking-server)
* [手順 4：訪問者 ID サービスの設定](#step-4--configure-the-visitor-id-service)

### 手順 1：Adobe Campaign での外部アカウントの設定または確認 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

まず、Adobe Campaign中の外部アカウントを設定または確認する必要があります。 これらのアカウントはAdobeが設定し、必要な情報がお客様に伝えている必要があります。

それには、次の手順に従います。

1. 詳細設定メニューで、**管理/アプリケーション設定/外部アカウント**&#x200B;を選択します。

   この統合で使用できる次の外部アカウントのいずれかを選択します。

   ![](assets/integration_aam_1.png)

1. **[!UICONTROL Receiver server]**&#x200B;を次の形式で入力してください
1. **[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**、**[!UICONTROL AWS Region]**&#x200B;を入力します。

これで、外部アカウントはこの統合用に設定されます。

### 手順2:データソースの設定{#step-2--configure-the-data-sources}

次の2つのデータソースがオーディエンスマネージャー内に作成されます。Adobe Campaign(MID)とAdobe Campaign(DeclaredId)。 同時に、次の2つのデータソースをAdobe Campaignで使用できます。

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:これは、デフォルトで訪問者IDに設定される、すぐに使用できるデータソースです。Campaign から作成されたセグメントは、このデータソースの一部になります。
* **宣言済み** IDデータソース：このデータソースを作成し、Audience Managerの **[!UICONTROL DeclaredId]** データソース定義にマッピングする必要があります。

異なるドメインを持つ複数のWebサイトの場合、Adobe CampaignはECIDに基づく調整をサポートしません。

**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;データソースを設定するには：

1. **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;を選択します。

   ![](assets/integration_aam_2.png)

1. **[!UICONTROL Data Source/ Alias]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;を選択します。
1. Adobeが提供する&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;を入力します。

   ![](assets/integration_aam_3.png)

1. **[!UICONTROL Reconciliation process]**&#x200B;カテゴリでは、調整条件を変更せず、常に&#x200B;**[!UICONTROL Visitor ID]**&#x200B;を使用することをお勧めします。
1. 「**[!UICONTROL Save]**」をクリックします。

**[!UICONTROL Declared ID]**&#x200B;データソースを作成するには：

1. **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、**[!UICONTROL Create]**&#x200B;ボタンをクリックします。
1. データソースの&#x200B;**[!UICONTROL Label]**&#x200B;を編集します。
1. 「**[!UICONTROL Data Source/ Alias]**」ドロップダウンで、Audience Managerの&#x200B;**[!UICONTROL DeclaredID]**&#x200B;データソースに対応するデータソースを選択します。
1. Adobeが提供する&#x200B;**[!UICONTROL Data Source / Alias]**&#x200B;と&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;を入力して、データソースを設定します。
1. 必要に応じて&#x200B;**[!UICONTROL Reconciliation process]**&#x200B;を設定します。
1. 「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>
>**[!UICONTROL AAM Destination ID]**&#x200B;フィールドは、[キャンペーントリガー統合](../../integrating/using/configuring-triggers-in-experience-cloud.md)用に共有データソースを設定する場合は不要です。 **[!UICONTROL Priority]** は、トリガー-キャンペーン統合を設定する場合にのみ必要です。優先度によって、最初に設定されるデータソースが決まります。 優先度は、1や100など任意の数値です。 優先度が高いほど、調整時の優先順位が高くなります。

### 手順 3：キャンペーントラッキングサーバーの設定 {#step-3--configure-campaign-tracking-server}

People コアサービスまたは Audience Manager との統合を設定する場合は、Campaign トラッキングサーバーも設定する必要があります。

ここでは、キャンペーントラッキングサーバーがドメイン(CNAME)に登録されていることを確認する必要があります。 ドメイン名の設定について詳しくは、[この記事](https://helpx.adobe.com/jp/campaign/kb/domain-name-delegation.html)を参照してください。

### 手順 4：訪問者 ID サービスの設定 {#step-4--configure-the-visitor-id-service}

訪問者 ID サービスを web のプロパティや web サイトで設定したことがない場合は、次の[ドキュメント](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/setup-aam-analytics.html)を参照してサービスの設定方法を確認するか、次の[動画](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)をご覧ください。

設定とプロビジョニングが完了し、統合を使用してオーディエンスまたはセグメントをインポートおよびエクスポートできるようになりました。
