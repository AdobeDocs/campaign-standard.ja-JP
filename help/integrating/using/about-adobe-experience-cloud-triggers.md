---
title: Adobe Experience Cloud Triggers について
description: アドビのAnalyticsを使用している顧客の行動をトラッキングすることで、Adobe Campaign内の顧客にパーソナライズした電子メールを送信できるようになりました。
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 4%

---


# Adobe Experience Cloud Triggers について{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

Adobe Experience Cloudでは、様々なトリガー、つまり、監視したい顧客行動（Webサイトで訪問を放棄した顧客がWebサイトで検索を行ったが購入は行わなかった顧客、セッション期限が切れた顧客など）を定義します。 トリガーを作成する場合は、トリガーの条件と、イベントーでAdobe Campaignに送信される（アップロードされる）データを定義します。

Adobe Campaignでは、以前に作成したトリガーを選択し、イベントデータをdatamartデータに拡張し、そのトリガーにリンクされたトランザクションメッセージテンプレートを定義します。 例えば、ある顧客がWebサイトでの訪問を放棄した場合、イベントがAdobe Campaignに送信され、そのイベントをが15分以内に顧客に送信されるリマーケティング電子メールを通じて活用できます。

**関連トピック：**

* トリガーの様々なタイプについて説明します。 [Adobe Experience Cloudドキュメント](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html)。
* サイトアクティビティに基づくリマーケティングメッセージの [トリガー（英語）のビデオをご覧ください](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) 。
* 2つの [放棄トリガーの使用例を発見します](../../integrating/using/abandonment-triggers-use-cases.md)。

## Triggersユーザープロセス {#triggers-user-process}

>[!CAUTION]
>
>メインユーザーの手順を実行する前に、機能を設定する必要があります。 詳しくは、機能の [アクティブ化](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)、ソリューションおよびサービスの [設定](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) 、およびキャンペーンでのマッピングされたトリガーの [作成を参照してください](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)。

Adobe Campaignでのユーザープロセスの主な手順は次のとおりです。

1. 既存のAdobe Experience Cloudトリガーにリンクしたトリガーイベントを作成します。
1. トリガーイベントを公開します。
1. トランザクションメッセージテンプレートのコンテンツを定義します。
1. テンプレートをテストします(テストプロファイルを作成し、配達確認を送信します)。
1. トランザクションメッセージテンプレートを公開します。

完全な使用例については、 [この節で説明します](../../integrating/using/abandonment-triggers-use-cases.md)。

## 重要な注意事項 {#important-notes}

以下に、トリガー —キャンペーン統合を使用する前に考慮すべき重要な注意事項を示します。

* トリガーに対するプッシュ通知はサポートされていません。 電子メールとSMSのみがサポートされます。
* 電子メールID、ページ名など、Analyticsで取得したメタデータを使用して、トリガーを拡張できます。
* トリガーをCampaign Standardに格納されたプロファイルに調整し、プロファイルのフィールドを使用してメッセージをパーソナライズできます。
* トリガーを受け取ると、処理および調整が行われ、送信されます。 受け取るトリガーの量、テンプレートで使用されるパーソナライゼーションフィールドの数に応じて、約5 ～ 15分かかります。

>[!NOTE]
>
>ベストプラクティスと技術上の制限について詳しくは、 [トリガーのベストプラクティスと制限を参照してください](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)。

