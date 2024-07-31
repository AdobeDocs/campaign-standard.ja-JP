---
title: Audience Manager または People コアサービスとの統合のプロビジョニングと設定
description: 様々なAdobe Experience Cloud ソリューションでオーディエンスやセグメントの共有を開始するために、Audience Manager/People コアサービスの統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 60386a9e6e424d76b1de0f2ecbeab48dd06fb354
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 43%

---

# Audience Manager または People コアサービスとの統合のプロビジョニングと設定{#integration-with-audience-manager-or-people-core-service}

Adobe CampaignでのAudience Managerコアと People コアのプロビジョニングと設定には、[ 統合へのリクエストの送信 ](#submitting-request-to-adobe) 次に [Adobe CampaignでのAdobeの設定 ](#configuring-the-integration-in-adobe-campaign) の 2 つの手順があります。

## アドビへのリクエストの送信 {#submitting-request-to-adobe}

Audience Manager（AAM）または People コアサービスの統合により、Adobe Campaignでオーディエンスやセグメントの読み込みおよび書き出しを行うことができます。

この統合を最初に設定する必要があります。この統合のプロビジョニングをリクエストするには、以下を添えてAdobeサポートにお問い合わせください。

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
   <td> 所属する組織の組織 ID。<br>組織 ID を見つけるには、<a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ja">このページ</a>を参照してください。</td> 
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

## Adobe Campaignでの統合の設定 {#configuring-the-integration-in-adobe-campaign}

このリクエストを送信すると、Adobe側で統合のプロビジョニングが進められます。また、設定を完了するための詳細情報がお客様に届きます。

* [手順 1：Adobe Campaign での外部アカウントの設定または確認](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [手順 2：データソースの設定](#step-2--configure-the-data-sources)
* [手順 3：Campaignトラッキングサーバーの設定](#step-3--configure-campaign-tracking-server)
* [手順 4：訪問者 ID サービスの設定](#step-4--configure-the-visitor-id-service)

### 手順 1：Adobe Campaign での外部アカウントの設定または確認 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

まず、Adobe Campaignで外部アカウントを設定または確認する必要があります。 これらのアカウントはAdobeが設定する必要があり、必要な情報がお客様に伝えられている必要があります。

それには、次の手順に従います。

1. 詳細メニューで、「**管理/アプリケーション設定/外部アカウント**」を選択します。

   この統合で利用可能な以下の外部アカウントのいずれかを選択します。

   ![](assets/integration_aam_1.png)

1. 次の形式で **[!UICONTROL Receiver server]** を入力します
1. **[!UICONTROL AWS Access Key ID]**、**[!UICONTROL Secret Access Key]**、**[!UICONTROL AWS Region]** を入力します。

これで、この統合用に外部アカウントが設定されました。

### 手順 2：データソースの設定 {#step-2--configure-the-data-sources}

Audience Manager 内では、Adobe Campaign（MID）とAdobe Campaign（DeclaredId）の 2 つのデータソースが作成されます。 同時に、Adobe Campaignでは次の 2 つのデータソースを使用できます。

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**：これは、訪問者 ID 用にデフォルトで設定されている標準のデータソースです。 Campaign から作成されたセグメントは、このデータソースの一部になります。
* **宣言済み ID** データソース：このデータソースを作成し、Audience Managerの **[!UICONTROL DeclaredId]** データソース定義にマッピングする必要があります。

異なるドメインを持つ複数の web サイトの場合、Adobe Campaignは ECID に基づく紐付けをサポートしていません。

**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** データソースを設定するには：

1. **[!UICONTROL Administration]**/**[!UICONTROL Application settings]**/**[!UICONTROL Shared Data Sources]** で、「**[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**」を選択します。

   ![](assets/integration_aam_2.png)

1. **[!UICONTROL Data Source/ Alias]** ドロップダウンで「**[!UICONTROL Adobe Campaign]**」を選択します。
1. Adobeから提供された **[!UICONTROL AAM Destination ID]** を入力します。

   ![](assets/integration_aam_3.png)

1. **[!UICONTROL Reconciliation process]** カテゴリでは、紐付け条件を変更せず、常に **[!UICONTROL Visitor ID]** を使用することをお勧めします。
1. 「**[!UICONTROL Save]**」をクリックします。

**[!UICONTROL Declared ID]** のデータソースを作成するには：

1. **[!UICONTROL Administration]**/**[!UICONTROL Application settings]**/**[!UICONTROL Shared Data Sources]** で、「**[!UICONTROL Create]**」ボタンをクリックします。
1. データソースの **[!UICONTROL Label]** を編集します。
1. **[!UICONTROL Data Source/ Alias]** ドロップダウンで、Audience Managerの **[!UICONTROL DeclaredID]** データソースに対応するデータSourceを選択します。
1. Adobeから提供された **[!UICONTROL Data Source / Alias]** と **[!UICONTROL AAM Destination ID]** を入力して、データソースを設定します。
1. 必要に応じて **[!UICONTROL Reconciliation process]** を設定します。
1. 「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>
>[ キャンペーンとトリガーの統合 ](../../integrating/using/configuring-triggers-in-experience-cloud.md) 用に共有データソースを設定している場合、「**[!UICONTROL AAM Destination ID]**」フィールドは必須ではありません。 **[!UICONTROL Priority]** は、トリガー - キャンペーン統合を設定する場合にのみ必要です。 優先度は、最初に設定されるデータSourceを決定します。 優先度には、1 や 100 などの任意の数を指定できます。 優先度が高いほど、紐付け時の環境設定が高くなります。

### 手順 3：Campaignトラッキングサーバーの設定 {#step-3--configure-campaign-tracking-server}

People コアサービスまたは Audience Manager との統合を設定する場合は、Campaign トラッキングサーバーも設定する必要があります。

共有オーディエンスが訪問者 ID で機能できるようにするには、トラッキングサーバードメインを、クリックした URL またはメイン web サイトのサブドメインにする必要があります。

>[!IMPORTANT]
>
> Campaign トラッキングサーバーがドメインに登録されていることを確認する必要があります（CNAME）。ドメイン名の設定について詳しくは、[ この記事 ](https://helpx.adobe.com/jp/campaign/kb/domain-name-delegation.html) を参照してください。

### 手順 4：訪問者 ID サービスの設定 {#step-4--configure-the-visitor-id-service}

訪問者 ID サービスを web プロパティや web サイトで設定したことがない場合は、次の[ドキュメント](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html?lang=ja)を参照してサービスの設定方法を確認するか、次の[ビデオ](https://helpx.adobe.com/jp/marketing-cloud/how-to/email-marketing.html#step-two)をご覧ください。

Experience Cloud ID サービスの `setCustomerID` 関数と統合コード `AdobeCampaignID` を使用して、顧客 ID を宣言済み ID と同期します。`AdobeCampaignID` は、[手順 2：データソースの設定](#step-2--configure-the-data-sources)で設定した受信者データソースに設定された調整キーの値と一致させる必要があります。

設定とプロビジョニングが完了し、統合を使用してオーディエンスやセグメントの読み込みおよび書き出しを行えるようになりました。
