---
solution: Campaign Standard
product: campaign
title: トリガーのテスト
description: Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題を解決するのに役立つトラブルシューティングのヒントを説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: トリガー
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: d3482dfad245807aedee6deb36fd67e43c7a66b9
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# トリガーのテスト{#testing-your-triggers}

Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題の解決に役立つトラブルシューティングのヒントを示します。

**機能は有効化されていますか。**

トリガー- Campaign統合が有効になっているかどうかを確認するには、左上隅のAdobe Campaignロゴをクリックし、**[!UICONTROL Marketing plans]** /**[!UICONTROL Transactional messages]**&#x200B;を選択します。 **[!UICONTROL Experience Cloud Triggers]**&#x200B;項目が表示されます。

表示されたら、次の手順に進みます。

そうでない場合は、Adobeアカウントのエグゼクティブまたはプロフェッショナルサービスのパートナーにお問い合わせください。 [機能の有効化](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)を参照してください。

**トリガー**

[Campaignでのマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)で説明されている手順に従って、トリガーを作成します。

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガーエンドポイントの接続に失敗します。 トリガーがExperience Cloud（Activationサービス）でプロビジョニングされているかどうかを確認します。 そうでない場合は、担当のAdobeアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloud会社名
* IMS 組織 ID
* Analyticsログイン会社名(Marketing Cloud会社名と同じ)

**トリガー**

[Campaignでのマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)で説明されている手順に従って、トリガーを公開します。

公開が成功した場合は、次の手順に進みます。 そうでない場合は、Adobeに問い合わせてインスタンスを再起動し、もう一度やり直してください。

**Webサイトからトリガーを生成する**

[トランザクションメッセージテンプレートの編集](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template)で説明されている手順に従って、トランザクションテンプレートを編集し、公開します。 次に、Webサイトからのトリガーの生成をテストします。

Analyticsがトリガーを受け取った場合は、次の手順に進みます。 そうでない場合は、次の項目を確認します。

* トリガーがAnalyticsに対して有効
* MCIDとAnalyticsを使用するWebサイトは、DTMで有効になっています
* トリガーの作成時には、適切なAnalyticsレポートスイートが使用されます

**トリガーはCampaignで受信されますか？**

そうでない場合は、トリガーがパイプラインから受信されたかどうかを確認します。

そうでない場合は、Adobeに問い合わせて、パイプラインエンドポイントの設定を確認してください。

その場合は、次のガイドラインに従います。

* Campaignデータソースで紐付けIDタイプを確認します。
* 顧客IDデータソースは、顧客属性を使用して作成します。
* データソースIDを確認します。
* Adobeに、データソース設定の後でCampaignインスタンスを再起動するよう依頼します。
* トリガーレポートでのトリガー解析の問題を確認します。

**トリガーのステータスは保留中か**

そうでない場合は、次の手順に進みます。 その場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルが正しくされていないことを確ブロックリスト認します。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか？**

メッセージが無効な場合は、次の項目を確認します。

* 無効とマークされたトリガーエンリッチメントのパーソナライゼーションフィールドについては、関連するeventCusResourceコレクションからトランザクションテンプレートを検証します。
* メッセージ形式の検証
