---
solution: Campaign Standard
product: campaign
title: Audience Manager または People コアサービスとの統合のプロビジョニングと設定
description: 'Audience Manager/Peopleコアサービスの統合を設定して、別のAdobe Experience Cloudソリューションとのオーディエンスやセグメントの共有を開始する方法について説明します。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Peopleコアサービスの統合
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 40%

---

# Audience Manager または People コアサービスとの統合のプロビジョニングと設定{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Adobe CampaignのAudience ManagerとPeopleコアのプロビジョニングと設定には、次の2つの手順を実行します。[Adobe](#submitting-request-to-adobe)にリクエストを送信し、[Adobe Campaign](#configuring-the-integration-in-adobe-campaign)で統合を設定します。

## アドビへの依頼の送信 {#submitting-request-to-adobe}

Audience Manager(AAM)またはPeopleコアサービスの統合により、Adobe Campaignでオーディエンスやセグメントをインポートおよびエクスポートできます。

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

## Adobe Campaignでの統合の設定{#configuring-the-integration-in-adobe-campaign}

このリクエストを送信すると、Adobeは統合のプロビジョニングに進み、お客様に設定を完了させるために必要な詳細と情報を提供するようお問い合わせいたします。

* [手順 1：Adobe Campaign での外部アカウントの設定または確認](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [手順2:データソースの設定](#step-2--configure-the-data-sources)
* [手順 3：Campaignトラッキングサーバーの設定](#step-3--configure-campaign-tracking-server)
* [手順 4：訪問者 ID サービスの設定](#step-4--configure-the-visitor-id-service)

### 手順 1：Adobe Campaign での外部アカウントの設定または確認 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

最初に、Adobe Campaignで外部アカウントを設定または確認する必要があります。 これらのアカウントはAdobeが設定し、お客様に必要な情報を伝える必要があります。

それには、次の手順に従います。

1. 詳細設定メニューから、**管理/アプリケーション設定/外部アカウント**&#x200B;を選択します。

   この統合で使用できる次の外部アカウントの1つを選択します。

   ![](assets/integration_aam_1.png)

1. 次の形式で&#x200B;**[!UICONTROL Receiver server]**&#x200B;を入力します。
1. **[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**&#x200B;および&#x200B;**[!UICONTROL AWS Region]**&#x200B;を入力します。

これで、外部アカウントがこの統合用に設定されました。

### 手順2:データソースの設定{#step-2--configure-the-data-sources}

Audience Manager内で次の2つのデータソースが作成されます。Adobe Campaign(MID)とAdobe Campaign(DeclaredId)。 同時に、次の2つのデータソースがAdobe Campaignで使用できます。

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:これは、訪問者IDにデフォルトで設定されている標準のデータソースです。Campaign から作成されたセグメントは、このデータソースの一部になります。
* **宣言さ** れたIDデータソース：このデータソースは、Audience Managerのデータソース定義を使用して作成およびマ **[!UICONTROL DeclaredId]** ッピングする必要があります。

異なるドメインを持つ複数のWebサイトの場合、Adobe CampaignはECIDに基づく紐付けをサポートしません。

**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**&#x200B;データソースを設定するには：

1. **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、「**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**」を選択します。

   ![](assets/integration_aam_2.png)

1. **[!UICONTROL Data Source/ Alias]**&#x200B;ドロップダウンで&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;を選択します。
1. Adobeが提供する&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;を入力します。

   ![](assets/integration_aam_3.png)

1. **[!UICONTROL Reconciliation process]**&#x200B;カテゴリでは、紐付け条件を変更せず、常に&#x200B;**[!UICONTROL Visitor ID]**&#x200B;を使用することをお勧めします。
1. 「**[!UICONTROL Save]**」をクリックします。

**[!UICONTROL Declared ID]**&#x200B;データソースを作成するには：

1. **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、「**[!UICONTROL Create]**」ボタンをクリックします。
1. データソースの&#x200B;**[!UICONTROL Label]**&#x200B;を編集します。
1. 「 **[!UICONTROL Data Source/ Alias]** 」ドロップダウンで、「Audience Manager」から&#x200B;**[!UICONTROL DeclaredID]**&#x200B;データソースに対応するデータソースを選択します。
1. Adobeが提供する&#x200B;**[!UICONTROL Data Source / Alias]**&#x200B;と&#x200B;**[!UICONTROL AAM Destination ID]**&#x200B;を入力して、データソースを設定します。
1. 必要に応じて&#x200B;**[!UICONTROL Reconciliation process]**&#x200B;を設定します。
1. 「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>
>**[!UICONTROL AAM Destination ID]**&#x200B;フィールドは、[Campaignとトリガーの統合](../../integrating/using/configuring-triggers-in-experience-cloud.md)用に共有データソースを設定する場合は必須ではありません。 **[!UICONTROL Priority]** は、トリガー- Campaign統合を設定する場合にのみ必要です。優先度によって、最初に設定されるデータソースが決まります。 優先度は、1や100など、任意の数値です。 優先度が高いほど、紐付け時の優先順位が高くなります。

### 手順 3：キャンペーントラッキングサーバーの設定 {#step-3--configure-campaign-tracking-server}

People コアサービスまたは Audience Manager との統合を設定する場合は、Campaign トラッキングサーバーも設定する必要があります。

ここでは、キャンペーントラッキングサーバーがドメイン(CNAME)に登録されていることを確認する必要があります。 ドメイン名の設定に関する詳細は、[この記事](https://helpx.adobe.com/jp/campaign/kb/domain-name-delegation.html)を参照してください。

### 手順 4：訪問者 ID サービスの設定 {#step-4--configure-the-visitor-id-service}

訪問者 ID サービスを web のプロパティや web サイトで設定したことがない場合は、次の[ドキュメント](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html?lang=ja)を参照してサービスの設定方法を確認するか、次の[動画](https://helpx.adobe.com/jp/marketing-cloud/how-to/email-marketing.html#step-two)をご覧ください。

設定とプロビジョニングが完了し、統合を使用してオーディエンスまたはセグメントをインポートおよびエクスポートできるようになりました。
