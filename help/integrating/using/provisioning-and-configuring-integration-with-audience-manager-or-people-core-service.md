---
title: Audience Manager または People コアサービスとの統合のプロビジョニングと設定
description: '様々なAdobe Experience cloudソリューションでオーディエンスまたはセグメントの共有を開始するためのAudience Manager/Peopleコアサービス統合の設定方法について説明します。 '
page-status-flag: never-activated
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e887fff76660dcb0369d4222e1ab3ac391c3a2d

---


# Audience Manager または People コアサービスとの統合のプロビジョニングと設定{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Adobe CampaignのAudience ManagerとPeopleコアのプロビジョニングと設定には、次の2つの手順を実行します。アドビ [にリクエストを送信し](#submitting-request-to-adobe) 、Adobe Campaign [で統合を設定します](#configuring-the-integration-in-adobe-campaign)。

## アドビへの依頼の送信 {#submitting-request-to-adobe}

Audience Manager(AAM)またはPeopleコアサービスの統合により、Adobe Campaignでオーディエンスやセグメントの読み込みと書き出しを行うことができます。

この統合を最初に設定する必要があります。この統合のプロビジョニングを依頼するには、次の情報を記載のうえ、[Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) まで E メールを送信します。

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
   <td> 組織の IMS Org ID. <br> IMS組織IDは、Experience cloudの管理メニューで確認できます。 これは、Adobe Experience Cloud への初回接続時に付与されるものです。 </td> 
  </tr> 
  <tr> 
   <td> <strong>環境：</strong><br /> </td> 
   <td> 例：実稼働環境 </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM または People コアサービス</strong><br /> </td> 
   <td> 例：Adobe Audience Managerを参照してください。 プロビジョニングチームに、Audience Managerライセンスを所有しているかどうかに関わらず、必ず言及してください。</td> 
  </tr> 
  <tr> 
   <td> <strong>宣言済み ID または訪問者 ID</strong><br /> </td> 
   <td> 例：宣言済みID </td> 
  </tr> 
  <tr> 
   <td> <strong>追加情報</strong><br /> </td> 
   <td> 役に立つ情報またはコメント（ある場合） </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Campaignでの統合の設定 {#configuring-the-integration-in-adobe-campaign}

このリクエストを送信した後、アドビは統合のプロビジョニングに進み、お客様に連絡して、設定の最終決定に必要な詳細と情報を提供します。

* [手順1:Adobe Campaignで外部アカウントを設定または確認する](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [手順2:データソースの設定](#step-2--configure-the-data-sources)
* [手順3:キャンペーントラッキングサーバーの設定](#step-3--configure-campaign-tracking-server)
* [手順4:訪問者IDサービスの設定](#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

まず、Adobe Campaignで外部アカウントを設定または確認する必要があります。 これらのアカウントはアドビによって設定され、必要な情報がお客様に伝えられているはずです。

これをおこなうには：

1. 詳細設定メニューで、管理/アプリケ **ーション設定/外部アカウントを選択します**。

   この統合で使用できる次の外部アカウントの1つを選択します。

   ![](assets/integration_aam_1.png)

1. 次の形 **[!UICONTROL Receiver server]** 式で入力します
1. とを入力し **[!UICONTROL AWS Access Key ID]**&#x200B;ます **[!UICONTROL Secret Access Key]****[!UICONTROL AWS Region]**。

これで、外部アカウントがこの統合用に設定されました。

### 手順2:データソースの設定 {#step-2--configure-the-data-sources}

Audience Manager内に、次の2つのデータソースが作成されます。Adobe Campaign(MID)およびAdobe Campaign(DeclaredId)。 同時に、Adobe Campaignでは次の2つのデータソースを使用できます。

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:これは、デフォルトで訪問者ID用に設定される、あらかじめ用意されたデータソースです。 Campaign から作成されたセグメントは、このデータソースの一部になります。
* **宣言済みIDデータ** ・ソース：このデータソースは、Audience Managerで作成し、データソース定義にマッピ **[!UICONTROL DeclaredId]** ングする必要があります。

異なるドメインを持つ複数のWebサイトの場合、Adobe CampaignはECIDに基づく調整をサポートしません。

データソースを設 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** 定するには：

1. // **[!UICONTROL Administration]** で、 **[!UICONTROL Application settings]** を選 **[!UICONTROL Shared Data Sources]**&#x200B;択します **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**。

   ![](assets/integration_aam_2.png)

1. ドロッ **[!UICONTROL Adobe Campaign]** プダウン **[!UICONTROL Data Source/ Alias]** からを選択します。
1. アドビから提供さ **[!UICONTROL AAM Destination ID]** れたを入力します。

   ![](assets/integration_aam_3.png)

1. カテゴリ **[!UICONTROL Reconciliation process]** では、調整条件を変更せず、常に調整条件を使用するようお勧めしま **[!UICONTROL Visitor ID]**&#x200B;す。
1. Click **[!UICONTROL Save]**.

データソースを作 **[!UICONTROL Declared ID]** 成するには：

1. // **[!UICONTROL Administration]** で、ボ **[!UICONTROL Application settings]** タン **[!UICONTROL Shared Data Sources]**&#x200B;をクリックし **[!UICONTROL Create]** ます。
1. データソース **[!UICONTROL Label]** のを編集します。
1. ドロップダ **[!UICONTROL Data Source/ Alias]** ウンで、Audience Managerのデータソースに対応するデ **[!UICONTROL DeclaredID]** ータソースを選択します。
1. アドビから提供されたおよびを入力して、デ **[!UICONTROL Data Source / Alias]** ータソ **[!UICONTROL AAM Destination ID]** ースを設定します。
1. 必要に応じてを **[!UICONTROL Reconciliation process]** 設定します。
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>このフ **[!UICONTROL AAM Destination ID]** ィールドは、 [Campaign-Triggers統合用の共有データソースを設定する場合は必須で](../../integrating/using/configuring-triggers-in-experience-cloud.md)はありません。 **[!UICONTROL Priority]** が必要なのは、トリガー — Campaign統合を設定する場合のみです。 優先度は、最初に設定するデータソースを決定します。 優先度は1や100など任意の数値です。 優先度が高いほど、調整中の優先度が高くなります。

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

People コアサービスまたは Audience Manager との統合を設定する場合は、Campaign トラッキングサーバーも設定する必要があります。

ここでは、キャンペーントラッキングサーバーがドメイン(CNAME)に登録されていることを確認する必要があります。 ドメイン名のデリゲーションについて詳しくは、[この記事](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf)を参照してください。

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

訪問者 ID サービスを Web のプロパティや Web サイトで設定したことがない場合は、次の[ドキュメント](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html)を参照してサービスの設定方法を確認するか、次の[ビデオ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)をご覧ください。

設定とプロビジョニングが完了し、統合を使用してオーディエンスまたはセグメントをインポートおよびエクスポートできるようになりました。
