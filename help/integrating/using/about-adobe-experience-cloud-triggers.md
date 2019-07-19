---
title: Adobe Experience Cloud Triggersについて
seo-title: Adobe Experience Cloud Triggersについて
description: Adobe Experience Cloud Triggersについて
seo-description: Adobe Analyticsの顧客から特定の行動を追跡することで、Adobe Campaignで顧客にパーソナライズされた電子メールを送信できるようになりました。
page-status-flag: 常にアクティブ化されていない
uuid: 0aa4bd6e-1bb5-4d0b-913b- eca93f050acd
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- trigger
discoiquuid: e526b205-2d01-4a8b-9685- ba1d9a1a1f459f
context-tags: トリガー、概要;トリガー、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

Adobe Experience Cloudでは、様々なトリガー（例えば、Webサイトでの訪問を破棄した顧客、Webサイトでの訪問を破棄したが、購入しなかったクライアント、セッションが期限切れになったクライアントなど）を定義します。トリガーを作成するときに、トリガーの条件と、イベント（プロ広告）で送信されるデータをAdobe Campaignに定義します。

Adobe Campaignでは、以前に作成したトリガーを選択し、イベントデータを使用してイベントデータを豊かにし、そのトリガーにリンクされているトランザクションメッセージテンプレートを定義します。例えば、クライアントがWebサイトに訪問したときに、イベントがAdobe Campaignに送信され、その後15分以内にクライアントに送信されるリマーケティング電子メール経由でこのイベントを利用できます。

**関連トピック:**

* Learn about the different types of triggers: [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Watch the [Trigger Remarketing Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) video.
* Discover our two [Abandonment Triggers use cases](../../integrating/using/abandonment-triggers-use-cases.md).

## Triggers user process {#triggers-user-process}

>[!CAUTION]
>
>メインユーザー手順を実行する前に、機能を設定する必要があります。For more on this refer to [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) and [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

Adobe Campaignでは、ユーザープロセスの主な手順を次に示します。

1. 既存のAdobe Experience Cloudトリガーにリンクされているトリガーイベントを作成します。
1. トリガーイベントを発行します。
1. トランザクションメッセージテンプレートのコンテンツを定義します。
1. テンプレートをテストします（テストプロファイルの作成と配達確認の送信）。
1. トランザクションメッセージテンプレートを発行します。

Complete use cases are described in [this section](../../integrating/using/abandonment-triggers-use-cases.md).

## Important notes {#important-notes}

Triggers- Campaign統合を使用する前に考慮すべき重要な注意事項を以下に示します。

* プッシュ通知は、トリガーに対してはサポートされていません。電子メールとSMSのみがサポートされています。
* 電子メールID、ページ名など、Analyticsでキャプチャされたメタデータを使用してトリガーを充実させることができます。
* トリガーをキャンペーンStandardに保存されているプロファイルに調整し、プロファイルのフィールドを使用してメッセージをパーソナライズできます。
* トリガーが受信されるとすぐに処理され、調整されて送信されます。受信トリガーの数（テンプレートで使用されるパーソナライゼーションフィールドの数）によって、約5~15分かかります。

>[!NOTE]
>
>For more on best practices and technical limitations, refer to [Triggers best practices and limitations](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

