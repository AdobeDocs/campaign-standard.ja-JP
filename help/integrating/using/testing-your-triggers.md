---
title: トリガーのテスト
description: Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題を解決するためのトラブルシューティングのヒントを説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
TQID: 'https://experienceleague.adobe.com/bbNySA5tCj7hDs3YG9AlPGgOUS42r3or0j-QhwIzXEw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 1%
---
# トリガーのテスト{#testing-your-triggers}

次のトラブルシューティングのヒントは、Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題を解決するのに役立ちます。

**機能はアクティブ化されていますか？**

トリガー - Campaign統合が有効になっているかどうかを確認するには、左上隅にあるAdobe Campaign ロゴをクリックし、**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**&#x200B;を選択します。 **[!UICONTROL Experience Cloud Triggers]**&#x200B;項目が表示されます。

表示されたら、次のステップに進みます。

そうでない場合は、Adobeのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 [機能のアクティブ化](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)を参照してください。

**トリガーを作成してみてください**

トリガーを作成するには、[Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)でマッピングされたトリガーの作成に記載されている手順に従います。

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガーエンドポイントの接続に失敗したことを意味します。 トリガーがExperience Cloud （アクティベーションサービス）でプロビジョニングされているかどうかを確認します。 そうでない場合は、Adobeのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloudの会社名
* 組織 ID
* Analytics Login Company （Marketing Cloudの会社名と同じ場合があります）

**トリガーを公開してみてください**

トリガーを公開するには、[Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)でマッピングされたトリガーの作成に記載されている手順に従います。

公開が成功した場合は、次の手順に進みます。 そうでない場合は、Adobeに連絡してインスタンスを再起動し、もう一度試してください。

**Web サイトからトリガーを生成**

「[&#x200B; トランザクションメッセージテンプレートの編集](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template)」の手順に従って、トランザクションテンプレートを編集および公開します。 続いて、web サイトからのトリガーの生成をテストします。

トリガーがAnalyticsで受信された場合は、次の手順に進みます。 そうでない場合は、次の項目を確認してください。

* Analyticsのトリガーが有効になっています
* MCIDとAnalyticsを使用したweb サイトはDTMで有効になっています
* トリガーの作成中に適切なAnalytics レポートスイートが使用される

**トリガーはCampaignで受信されますか？**

そうでない場合は、トリガーがパイプラインから受け取られたかどうかを確認します。

そうでない場合は、Adobeに連絡して、パイプラインのエンドポイントの設定を確認します。

その場合は、次のガイドラインに従います。

* Campaign データソースの紐付けID タイプを確認します。
* CustomerId データソースは、顧客属性を使用して作成されます。
* データソース IDを確認します。
* データソース設定後にCampaign インスタンスを再起動するようにAdobeに依頼します。
* トリガーレポートのトリガー解析の問題を確認します。

**トリガーは保留中のステータスですか？**

そうでない場合は、次のステップに進みます。 その場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルが共有ブロックリストにないことを確認します。
* タイポロジルールの適用を確認してください。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか？**

メッセージが無効な場合は、次の項目を確認してください。

* 無効としてマークされたトリガーエンリッチメントパーソナライゼーションフィールドの場合は、関連するeventCusResource コレクションからトランザクションテンプレートを検証します。
* メッセージ形式の検証
