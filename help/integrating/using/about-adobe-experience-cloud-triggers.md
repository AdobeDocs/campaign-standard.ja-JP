---
title: Adobe Experience Cloud Triggers について
description: Adobe Analyticsを使用する顧客の特定の行動を追跡することで、Adobe Campaignで顧客にパーソナライズされた電子メールを送信できるようになりました。
page-status-flag: 非活性化の
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとトリガーの連携
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: トリガー，概要；トリガー，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Adobe Experience Cloud Triggers について{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

Adobe Experience cloudでは、様々なトリガー（例えば、Webサイトでの訪問を放棄した顧客、Webサイトでの検索は行ったが購入は行わなかった顧客、セッションの期限が切れた顧客など）を定義します。 トリガーを作成する場合は、トリガーの条件と、イベントでAdobe Campaignに送信（アップロード）されるデータを定義します。

 Adobe Campaignでは、以前に作成したトリガーを選択し、イベントデータにデータマートデータを追加し、そのトリガーにリンクされたトランザクションメッセージテンプレートを定義します。 例えば、顧客がWebサイトでの訪問を中断した場合、イベントがAdobe Campaignに送信され、このイベントを利用できるリマーケティング用の電子メールがクライアントに送信されてから15分以内に発生します。

**関連トピック：**

* 様々なタイプのトリガーについて説明します。 [Adobe Experience cloudドキュメント](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)。
* 「サイトアクティビティ [に基づくリマーケティングメッセージのトリガー](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) 」のビデオをご覧ください。
* 2つの中断トリガ [ーの使用例を発見します](../../integrating/using/abandonment-triggers-use-cases.md)。

## ユーザープロセスのトリガー {#triggers-user-process}

>[!CAUTION]
>
>メインユーザーの手順を実行する前に、機能を設定する必要があります。 この詳細については、「機能のアクテ [ィブ化](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)」、「ソリュ [ーションとサービスの設定](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) 」、「Campaign [でのマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)」を参照してください。

Adobe Campaignのユーザープロセスの主な手順は次のとおりです。

1. 既存のAdobe Experience cloudトリガーにリンクしたトリガーイベントを作成します。
1. トリガーイベントを発行します。
1. トランザクションメッセージテンプレートのコンテンツを定義します。
1. テンプレートをテストします（テストプロファイルを作成し、校正を送信します）。
1. トランザクションメッセージテンプレートを公開します。

この節では、完全な使用例につ [いて説明します](../../integrating/using/abandonment-triggers-use-cases.md)。

## 重要な注意事項 {#important-notes}

以下に、トリガー — Campaign統合を使用する前に考慮すべき重要な注意事項を示します。

* プッシュ通知は、トリガーに対してはサポートされていません。 電子メールとSMSのみがサポートされます。
* 電子メールID、ページ名など、Analyticsで取得したメタデータを使用して、トリガーを強化できます。
* このトリガーをキャンペーン標準に保存されたプロファイルに調整し、プロファイルのフィールドを使用してメッセージをパーソナライズできます。
* トリガーは、受け取るとすぐに処理され、調整され、送信されます。 受け取るトリガーの量、およびテンプレートで使用されるパーソナライゼーションフィールドの数に応じて、約5 ～ 15分かかります。

>[!NOTE]
>
>ベストプラクティスと技術的な制限の詳細については、「トリガーのベストプラク [ティスと制限」を参照してくださ](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)い。

