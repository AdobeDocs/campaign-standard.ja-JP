---
solution: Campaign Standard
product: campaign
title: Campaign 統合の概要
description: アドビの各ソリューションが提供する様々な機能を Campaign と組み合わせることができます。
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: トリガー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 90%

---


# Campaign 統合について{#get-started-campaign-integrations}

この節では、Adobe Campaign の現在のバージョンと他のソリューションおよびサービスとの間で使用できる機能統合について説明します。

次に示す各統合では、Adobe Campaign の配信と詳細なキャンペーン管理機能を、一連のソリューションと組み合わせることで、ユーザーエクスペリエンスをパーソナライズできます。

>[!NOTE]
>
> デフォルトでは、Adobe Campaign は既に Adobe Experience Cloud アカウントにリンクされています。

環境によっては、Adobe Experience Cloud に他のソリューションをリンクすることができます。これらは組織（テナントとも呼ばれます）としてリンクされます。

組織とは、管理者がグループとユーザーを設定し、Experience Cloud でのシングルサインオンを制御できるエンティティのことです。組織は、すべての Experience Cloud 製品およびソリューションにまたがるログイン会社のように機能します。ほとんどの場合、組織は勤務先の会社名です。ただし、1 つの会社が多くの組織を持つことができます。ユーザーと組織の管理について詳しくは、[Adobe Experience Cloud ヘルプポータル](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html)を参照してください。

他のシステムのデータフローを Adobe Campaign と統合する場合は、[API のドキュメント](../../api/using/get-started-apis.md)を参照してください。

>[!NOTE]
>
>Adobe Campaign Standard は、Microsoft Dynamics 365 にも接続できます。この統合により、CRM システムで利用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティで利用できます。この統合について詳しくは、[Campaign と Dynamics 365 の使用](../../integrating/using/d365-acs-get-started.md)を参照してください。


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
   <td> Experience Manager<br /> 6.1、6.2、6.3、6.4、6.5<br /> </td> 
   <td> E メールコンテンツや Adobe Campaign データベースにマッピングされたフォームを Adobe Experience Manager で直接作成することができます。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">キャンペーンとExperience Managerの操作</a>、 <a href="https://helpx.adobe.com/jp/experience-manager/6-4/sites/administering/using/campaignstandard.html">Experience ManagerとCampaign Standardの</a>統合 <a href="https://gn.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">、Experience Managerとキャンペーンを含む電子メールの作成</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic、Standard<br /> </td> 
   <td> Adobe Campaign で作成、送信された E メールが開封されたときに Adobe Target が動的に自動生成した画像を挿入することができます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">キャンペーンとターゲットの使用</a>、キャンペーンとターゲットの <a href="https://docs.adobe.com/content/help/ja-JP/target/using/integrate/campaign-and-target.html">統合</a>、リアル <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> タイムビデオでの電子メール画像のパーソナライズ（手順3）
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard、Premium <br /> </td> 
   <td> E メール配信の成功を Adobe Analytics で直接追跡できます。<br /> </td> 
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
   <td> Assets コアサービスと Assets On Demand<br /> </td> 
   <td> Adobe Campaign で作成した E メールとランディングページに Adobe Experience Cloud ライブラリからアセットを挿入することができます。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets コアサービス</a>と Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest（Analytics for Mobile）<br /> </td> 
   <td> モバイルアプリケーションの購読者から Points of Interest データを収集し、Adobe Campaign を使用してパーソナライズされたマーケティングメッセージを送信できます。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Campaign および Points of Interest データを利用した位置情報マーケティングメッセージの送信</a>（Analytics for Mobile）<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Adobe Analytics によって Web サイト上で追跡される特定の行動に応じて、Adobe Campaign を使用して顧客にパーソナライズされた E メールを送信できます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Campaign Standard での Experience Cloud Triggers の使用</a>、<a href="../../integrating/using/abandonment-triggers-use-cases.md">離脱トリガー（Campaign の使用例）</a>、<a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">サイトアクティビティに基づくリマーケティングメッセージのトリガー</a>ビデオ（手順 2）
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Dreamweaver で E メールコンテンツを編集し、Adobe Campaign と同期できます。<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">Dreamweavervideoを使用してパーソナライズされた電子メールを作成し、</a> Dreamweaver向けキャンペーン拡張機能を <a href="https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html">使用する</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDK<br /> </td> 
   <td> Experience PlatformSDK を使用して、Adobe Campaign でのモバイルアプリケーションプロパティのアクティベーションプロセスを自動化できます。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html">Experience Platform SDK を使用したモバイルアプリケーションの設定</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

