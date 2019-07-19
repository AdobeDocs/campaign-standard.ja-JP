---
title: Campaign統合について
seo-title: Campaign統合について
description: Campaign統合について
seo-description: Adobe Campaignでは、他のアドビソリューションを使用して、その他の機能を組み合わせることができます。
page-status-flag: 常にアクティブ化されていない
uuid: 59d7cd99- a6f7-47f1-9b5c- c50e27a2bef8
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: about- campaign- integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 337f2270f3f66d5172084a4e2a19d6185bf097ff

---


# About Campaign integrations{#about-campaign-integrations}

ここでは、Adobe Campaignと他のソリューションおよびサービスの間で利用できる機能統合について説明します。

以下に示す様々な統合によって、Adobe Campaignの配信と高度なキャンペーン管理機能を組み合わせて、ユーザーのエクスペリエンスをパーソナライズするために作成された一連のソリューションと組み合わせることができます。

>[!NOTE]
>
> デフォルトでは、Adobe Campaignは既にAdobe Experience Cloudアカウントにリンクされています。

環境によっては、他のソリューションをAdobe Experience Cloudにリンクすることもできます。これらは組織としてリンクされます（「テナント」とも呼ばれます）。

組織は、管理者がグループとユーザーを設定し、Experience Cloudのシングルサインオンを制御するためのエンティティです。組織は、すべてのExperience Cloud製品およびソリューションにわたるログイン会社のように機能します。ほとんどの場合、組織は会社名です。ただし、会社には多数の組織を持つことができます。User and organization management is detailed in the [Adobe Experience Cloud help portal](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

If you would like to integrate data flows from other systems with Adobe Campaign, have a look at our [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!NOTE]
>
>Adobe Campaign StandardはMicrosoft Dynamics365に接続することもできます。この統合により、CRMシステム内の利用可能なすべてのContactデータの同期を有効にし、関連するすべてのContactデータをキャンペーンアクティビティで利用できるようにします。For more on this integration, refer to [Working with Campaign and Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Allows you to create email contents or forms mapped to the Adobe Campaign database directly in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">CampaignおよびExperience Managerとの連携</a><br/>、 <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Experience ManagerとキャンペーンStandard</a><br/>の統合、 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Experience ManagerとCampaignの使用による電子メールの作成</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">キャンペーンとTargetの操作</a><br/>、 <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">キャンペーンとTargetの統合</a><br/>、 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">リアルタイム</a> ビデオに電子メール画像をパーソナライズ（手順3）
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Allows you to track the success of your email deliveries directly in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">CampaignデータのAnalyticsとの共有</a><br/>， <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">統合キャンペーンレポート</a> ビデオのKPIの共有（手順1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager and People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Allow you to exchange audiences with the different Adobe Experience Cloud applications that you use.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Peopleコアサービス（Profiles&amp; Audiences）</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service and Assets On Demand<br /> </td> 
   <td> Allows you to insert assets from your Adobe Experience Cloud library into emails and landing pages created in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assetsコアサービス</a> またはアセットオンデマンド<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> Allows you to collect Points of Interest data from your mobile application's subscribers to send personalized marketing messages with Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">キャンペーンおよび目標地点データを含む位置ベースのマーケティングメッセージの送信</a> （Analytics for Mobile）<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Allows you to send personalized emails to your customers in Adobe Campaign as a reaction to specific behaviors that are tracked on your website by Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">キャンペーン標準でのExperience Cloud Triggersの使用</a><br/>、 <a href="../../integrating/using/abandonment-triggers-use-cases.md">中断トリガー-キャンペーンの使用事例</a><br/>、 <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">サイトアクティビティ</a> ビデオに基づく再マーケティングメッセージのトリガー（手順2）
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Allows you to edit an email content from Dreamweaver and synchronize it with Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">Dreamweaver</a> ビデオを使用したパーソナライズされた電子メールの作成 <br/>、 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver用Campaign拡張機能の使用</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Allows you to edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor.<br /> </td> 
   <td> <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">Adobe Creative SDKでの画像の変更</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDKs<br /> </td> 
   <td> Allows automation of the Mobile App Property activation process in Adobe Campaign using the Experience Platform SDKs.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Experience Platform SDKを使用したモバイルアプリケーションの設定</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

