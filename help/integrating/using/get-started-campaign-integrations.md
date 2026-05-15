---
title: Campaign 統合の基本を学ぶ
description: アドビの各ソリューションが提供する様々な機能を Campaign と組み合わせることができます。
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
TQID: https://experienceleague.adobe.com/ertIWjv9n88c9As-BDvGXtzsod8Bce4yTYEVpmeZeEo
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: bb6c4d97-79f4-412c-a764-b541e9f9facdid: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: df0d6518-6f49-46e2-b46e-3bcc513f553f
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 760
ht-degree: 78%

---

# Campaign 統合について{#get-started-campaign-integrations}

この節では、Adobe Campaign の現在のバージョンと他のソリューションおよびサービスとの間で使用できる機能統合について説明します。

次に示す各統合では、Adobe Campaign の配信と詳細なキャンペーン管理機能を、一連のソリューションと組み合わせることで、ユーザーエクスペリエンスをパーソナライズできます。

>[!NOTE]
>
> デフォルトでは、Adobe Campaign は既に Adobe Experience Cloud アカウントにリンクされています。

環境によっては、Adobe Experience Cloud に他のソリューションをリンクすることができます。 これらは組織（テナントとも呼ばれます）としてリンクされます。

組織とは、管理者がグループとユーザーを設定し、Experience Cloud でのシングルサインオンを制御できるエンティティのことです。 組織は、すべての Experience Cloud 製品およびソリューションにまたがるログイン会社のように機能します。 ほとんどの場合、組織は勤務先の会社名です。 ただし、1 つの会社が多くの組織を持つことができます。 ユーザーと組織の管理について詳しくは、[Adobe Experience Cloud ヘルプポータル](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ja)を参照してください。

他のシステムのデータフローを Adobe Campaign と統合する場合は、[API のドキュメント](../../api/using/get-started-apis.md)を参照してください。

>[!NOTE]
>
>Adobe Campaign Standard は、Microsoft Dynamics 365 にも接続できます。この統合により、CRM システムで利用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティで利用できます。 この統合について詳しくは、[Campaign と Dynamics 365 の使用](../../integrating/using/d365-acs-get-started.md)を参照してください。


<table> 
 <thead> 
  <tr> 
   <th> ソリューション<br /> </th> 
   <th> 使用例<br /> </th> 
   <th> 参照<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> メールコンテンツや Adobe Campaign データベースにマッピングされたフォームを Adobe Experience Manager で直接作成することができます。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">CampaignおよびExperience Managerの操作</a>、<a href="https://helpx.adobe.com/jp/experience-manager/6-4/sites/administering/using/campaignstandard.html">Experience ManagerとCampaign Standardの連携</a>、<a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html">Experience ManagerおよびCampaignとのメール作成</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Adobe Campaign で作成、送信されたメールが開封されたときに Adobe Target が動的に自動生成した画像を挿入することができます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md"> キャンペーンとターゲットの操作</a>、<a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=ja"> キャンペーンとターゲットの統合</a>、<a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"> リアルタイム </a>のビデオでのメール画像のパーソナライズ（手順3）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> メール配信の成功を Adobe Analytics で直接追跡できます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Analytics との Campaign データの共有</a>、<a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Campaign で統合レポートを作成するための KPI の共有</a>ビデオ（手順 1）
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager と People コアサービス（プロファイルとオーディエンス）<br /> </td> 
   <td> お使いの Adobe Experience Cloud の各アプリケーションとオーディエンスを交換できます。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People コアサービス（プロファイルとオーディエンス）</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Adobe Real-Time Customer Data Platform （RTCDP） <br /> </td> 
   <td> Adobe CampaignとAdobe Real-time Customer Data Platform （RTCDP）の連携により、セグメントデータを共有し、Adobe Campaignにオーディエンスをインポートすることができます。</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">ソースと宛先の基本を学ぶ</a></td>
  </tr> 
  <tr> 
   <td> Adobe Asset コアサービスとAssets On Demand<br /> </td> 
   <td> Adobe Campaign で作成したメールとランディングページに Adobe Experience Cloud ライブラリからアセットを挿入することができます。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets コアサービス</a>と Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest（Analytics for Mobile）<br /> </td> 
   <td> モバイルアプリケーションの購読者から Points of Interest データを収集し、Adobe Campaign を使用してパーソナライズされたマーケティングメッセージを送信できます。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Campaign および Points of Interest データを利用した位置情報マーケティングメッセージの送信</a>（Analytics for Mobile）<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Cloud Triggers<br /> </td> 
   <td> Adobe Analytics によって Web サイト上で追跡される特定の行動に応じて、Adobe Campaign を使用して顧客にパーソナライズされたメールを送信できます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Campaign Standard での Experience Cloud Triggers の使用</a>、<a href="../../integrating/using/abandonment-triggers-use-cases.md">離脱トリガー（Campaign の使用例）</a>、<a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">サイトアクティビティに基づくリマーケティングメッセージのトリガー</a>ビデオ（手順 2）
    </td> 
  </tr> 
    <tr> 
   <td> Adobe Journey Orchestration<br /> </td> 
   <td> Adobe Journey Orchestrationのコンテキストで、Adobe Campaign Standardのトランザクションメッセージング機能を使用して、標準操作で電子メール、プッシュ通知、SMSを送信できます。<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html">Adobe Journey OrchestrationおよびAdobe Campaign Standardの操作</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Dreamweaver でメールコンテンツを編集し、Adobe Campaign と同期できます。<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=ja">Dreamweaverでパーソナライズされたメールを作成</a>動画、<a href="https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html">DreamweaverのCampaign拡張機能を使用</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Platform SDK<br /> </td> 
   <td> Experience PlatformSDK を使用して、Adobe Campaign でのモバイルアプリケーションプロパティのアクティベーションプロセスを自動化できます。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html">Experience Platform SDK を使用したモバイルアプリケーションの設定</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
