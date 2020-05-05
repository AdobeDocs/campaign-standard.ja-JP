---
title: キャンペーン統合の概要
description: Adobe Campaignを使用すると、他のアドビソリューションを使用し、それぞれ異なる機能を組み合わせることができます。
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# Campaign 統合について{#get-started-campaign-integrations}

この節では、Adobe Campaignの現在のバージョンと他のソリューションおよびサービスとの間で使用できる機能統合について説明します。

以下に示す様々な統合により、Adobe Campaignの配信機能と高度なキャンペーン管理機能を組み合わせて、ユーザ体験をパーソナライズできるように作成された一連のソリューションを使用できます。

>[!NOTE]
>
> デフォルトでは、Adobe Campaignは既にAdobe Experience Cloudアカウントにリンクされています。

環境に応じて、他のソリューションもAdobe Experience Cloudにリンクできます。 組織（テナントとも呼ばれる）としてリンクされます。

組織とは、管理者がグループとユーザーを設定し、Experience Cloud でのシングルサインオンを制御できるエンティティのことです。組織は、すべての Experience Cloud 製品およびソリューションにまたがるログイン会社のように機能します。ほとんどの場合、組織は勤務先の会社名です。ただし、1 つの会社が多くの組織を持つことができます。ユーザーと組織の管理について詳しくは、 [Adobe Experience Cloudヘルプポータルを参照してください](https://marketing.adobe.com/resources/help/ja_JP/mcloud/organizations.html)。

他のシステムのデータフローをAdobe Campaignと統合する場合は、 [APIのドキュメントをご覧ください](../../api/using/get-started-apis.md)。

>[!NOTE]
>
>Adobe Campaign標準はMicrosoft Dynamics 365にも接続できます。 この統合により、CRMシステムで使用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティに提供できます。 この統合の詳細については、「キャンペーンとDynamics 365の [操作」を参照してください](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。


<table> 
 <thead> 
  <tr> 
   <th> ソリューション<br /> </th> 
   <th> 使用例<br /> </th> 
   <th> <br />を参照してください。 </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4, 6.5<br /> </td> 
   <td> E メールコンテンツや Adobe Campaign データベースにマッピングされたフォームを Adobe Experience Manager で直接作成することができます。<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">キャンペーンおよびExperience Manager</a><br/>、 <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrate Experience ManagerとCampaign Standardの連携</a> 、Experience Managerとキャンペーンを使用した電子メールの <br/><a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">作成</a> 
    </td> 
  </tr> 
  <tr> 
   <td> ターゲット<br /> クラシック、標準<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">キャンペーンとターゲットの使用</a> 、キャンペーンとターゲットの <br/>統合 <a href="https://marketing.adobe.com/resources/help/ja_JP/target/a4t/c_campaign_and_target.html">、リアルタイムビデオでの電子メール画像のパーソナライズ</a><br/><a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> （手順3）
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> 電子メール配信の成功をAdobe Analyticsで直接追跡できます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Analyticsとキャンペーンデータを共有</a><br/>、統合キャンペーンレポートビデオの <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">KPIを</a> 共有（手順1）
    </td> 
  </tr> 
  <tr> 
   <td> AdobeオーディエンスマネージャーとPeopleコアサービス(プロファイルとオーディエンス)<br /> </td> 
   <td> Allow you to exchange audiences with the different Adobe Experience Cloud applications that you use.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Peopleコアサービス(プロファイルとオーディエンス)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service and Assets On Demand<br /> </td> 
   <td> Adobe Campaign で作成した E メールとランディングページに Adobe Experience Cloud ライブラリからアセットを挿入することができます。<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assetsコアサービス</a> 、またはAssets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> 目標地点(Analytics for Mobile)<br /> </td> 
   <td> モバイルアプリのサブスクリプションから目標地点データを収集し、パーソナライズされたマーケティングメッセージをAdobe Campaignと共に送信できます。<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">場所ベースのマーケティングメッセージとキャンペーンおよび目標地点データの送信</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Adobe AnalyticsがWebサイト上で追跡する特定の行動に対する反応として、Adobe Campaign的にパーソナライズされた電子メールを顧客に送信できます。<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Campaign StandardでのExperience Cloud Triggersの使用</a><br/>、 <a href="../../integrating/using/abandonment-triggers-use-cases.md">放棄トリガー —キャンペーンの使用例</a><br/>、サイトのアクティビティ <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">（ビデオ）に基づくリマーケティングメッセージの</a> トリガー（手順2）
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Dreamweaverから電子メールコンテンツを編集し、Adobe Campaignと同期できます。<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">Dreamweaver</a> ビデオを使用してパーソナライズした電子メールを作成 <br/>する、Dreamweaver用キャンペーン拡張機能の <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">使用</a> 
  </td> 
  </tr> 
  <tr> 
   <td> エクスペリエンスプラットフォームSDK<br /> </td> 
   <td> Experience Platform SDKを使用したAdobe Campaignでのモバイルアプリのプロパティアクティベーションプロセスの自動化を可能にします。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Experience Platform SDKを使用したモバイルアプリケーションの設定</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

