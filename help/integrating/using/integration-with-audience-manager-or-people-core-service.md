---
title: Audience Manager または People コアサービスとの統合のプロビジョニングと設定
description: Audience Manager/People コアサービスの統合を設定して、様々なAdobe Experience Cloudソリューションとのオーディエンスやセグメントの共有を開始する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 5a7e48da3d62b186f96cd7451fb5a7b2cf94e09c
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 39%

---

# Audience Manager または People コアサービスとの統合のプロビジョニングと設定{#integration-with-audience-manager-or-people-core-service}

Adobe CampaignのAudience Managerと People コアのプロビジョニングと設定では、次の 2 つの手順を実行します。 [リクエストをAdobeに送信中](#submitting-request-to-adobe) その後 [Adobe Campaignでの統合の設定](#configuring-the-integration-in-adobe-campaign).

## アドビへのリクエストの送信 {#submitting-request-to-adobe}

Audience Manager(AAM) または People コアサービスの統合により、Adobe Campaignでオーディエンスやセグメントをインポートおよびエクスポートできます。

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

このリクエストを送信すると、Adobeは統合のプロビジョニングに進み、お客様に連絡して、設定を完了させるために必要な詳細と情報を提供します。

* [手順 1：Adobe Campaign での外部アカウントの設定または確認](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [手順 2：データソースの設定](#step-2--configure-the-data-sources)
* [手順 3：Campaignトラッキングサーバーの設定](#step-3--configure-campaign-tracking-server)
* [手順 4：訪問者 ID サービスの設定](#step-4--configure-the-visitor-id-service)

### 手順 1：Adobe Campaign での外部アカウントの設定または確認 {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

最初に、Adobe Campaignで外部アカウントを設定または確認する必要があります。 これらのアカウントはAdobeが設定し、必要な情報がお客様に伝えられているはずです。

それには、次の手順に従います。

1. 詳細設定メニューから、「 」を選択します。 **管理/アプリケーション設定/外部アカウント**.

   この統合で使用できる次の外部アカウントの 1 つを選択します。

   ![](assets/integration_aam_1.png)

1. 入力 **[!UICONTROL Receiver server]** 次の形式で
1. 次を入力します。 **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** および **[!UICONTROL AWS Region]**.

これで、この統合用に外部アカウントが設定されました。

### 手順 2：データソースの設定 {#step-2--configure-the-data-sources}

Audience Manager 内で作成されるデータソースは、Adobe Campaign(MID) とAdobe Campaign(DeclaredId) の 2 つです。 同時に、Adobe Campaignでは次の 2 つのデータソースを使用できます。

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**：これは、訪問者 ID にデフォルトで設定されている標準のデータソースです。 Campaign から作成されたセグメントは、このデータソースの一部になります。
* **宣言済み ID** データソース：このデータソースは、 **[!UICONTROL DeclaredId]** データソース定義 (Audience Manager)。

異なるドメインを持つ複数の Web サイトの場合、Adobe Campaignは ECID に基づく紐付けをサポートしません。

次の手順で **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** データソース：

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;を選択します。 **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. 選択 **[!UICONTROL Adobe Campaign]** （内） **[!UICONTROL Data Source/ Alias]** 」ドロップダウンリストから選択できます。
1. 次を入力します。 **[!UICONTROL AAM Destination ID]** Adobeが提供

   ![](assets/integration_aam_3.png)

1. Adobe Analytics の **[!UICONTROL Reconciliation process]** カテゴリの場合は、紐付け条件を変更せず、常に **[!UICONTROL Visitor ID]**.
1. 「**[!UICONTROL Save]**」をクリックします。

次の手順で **[!UICONTROL Declared ID]** データソース：

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;をクリックし、 **[!UICONTROL Create]** 」ボタンをクリックします。
1. を編集します。 **[!UICONTROL Label]** 」で指定します。
1. Adobe Analytics の **[!UICONTROL Data Source/ Alias]** 」ドロップダウンで、 **[!UICONTROL DeclaredID]** Audience Managerからのデータソース。
1. データソースを設定するには、 **[!UICONTROL Data Source / Alias]** および **[!UICONTROL AAM Destination ID]** Adobeが提供
1. を設定します。 **[!UICONTROL Reconciliation process]** 必要に応じて。
1. 「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>
>The **[!UICONTROL AAM Destination ID]** フィールドは、 [Campaign とトリガーの統合](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** は、トリガー- Campaign 統合を設定する場合にのみ必要です。 優先度は、最初に設定されるデータソースを決定します。 優先度には、1 や 100 など、任意の数を指定できます。 優先度が高いほど、紐付け時の優先順位が高くなります。

### 手順 3：Campaignトラッキングサーバーの設定 {#step-3--configure-campaign-tracking-server}

People コアサービスまたは Audience Manager との統合を設定する場合は、Campaign トラッキングサーバーも設定する必要があります。

ここでは、Campaign トラッキングサーバーがドメイン (CNAME) に登録されていることを確認する必要があります。 ドメイン名の設定について詳しくは、 [この記事](https://helpx.adobe.com/jp/campaign/kb/domain-name-delegation.html).

### 手順 4：訪問者 ID サービスの設定 {#step-4--configure-the-visitor-id-service}

訪問者 ID サービスを web プロパティや web サイトで設定したことがない場合は、次の[ドキュメント](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html?lang=ja)を参照してサービスの設定方法を確認するか、次の[ビデオ](https://helpx.adobe.com/jp/marketing-cloud/how-to/email-marketing.html#step-two)をご覧ください。

設定とプロビジョニングが完了し、統合を使用してオーディエンスやセグメントのインポートおよびエクスポートを行えるようになりました。
