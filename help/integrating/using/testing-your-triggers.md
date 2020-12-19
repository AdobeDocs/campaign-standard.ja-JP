---
solution: Campaign Standard
product: campaign
title: トリガーのテスト
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# トリガーのテスト{#testing-your-triggers}

次のトラブルシューティングのヒントは、TriggersをAdobe Campaignと共に使用する場合に発生する最も一般的な問題の解決に役立ちます。

**機能は有効になっているか。**

Triggers -キャンペーン統合がアクティブ化されているかどうかを確認するには、Adobe Campaignのロゴをクリックし、左上隅にある&#x200B;**[!UICONTROL Marketing plans]**/**[!UICONTROL Transactional messages]**&#x200B;を選択します。 **[!UICONTROL Experience Cloud Triggers]**&#x200B;項目が表示されます。

表示されたら、次の手順に進みます。

ログインしていない場合は、Adobeのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 [機能の有効化](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)を参照してください。

**トリガーを作成してみます。**

[キャンペーン](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)でのマッピングされたトリガーの作成で説明されている手順に従って、トリガーを作成します。

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガーの終点の接続に失敗したことを意味します。 TriggersがExperience Cloudでプロビジョニングされているかどうかを確認します(アクティベーションサービス)。 ログインしていない場合は、Adobeのアカウントエグゼクティブまたはプロのサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloud会社名
* IMS 組織 ID
* Analyticsログイン会社(Marketing Cloud会社名と同じにすることができます)

**トリガーを公開してみる**

[キャンペーン](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)でマップされたトリガーを作成してトリガーを発行するには、&lt;a0/>に記載されている手順に従います。

パブリケーションが成功した場合は、次のステップに進みます。 インスタンス名がない場合は、Adobeに問い合わせてインスタンスを再起動し、もう一度やり直してください。

**Webサイトからのトリガーの生成**

[トランザクションメッセージテンプレート](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template)の編集で説明されている手順に従って、トランザクションテンプレートを編集し、公開します。 次に、Webサイトからのトリガーの生成をテストします。

トリガーがAnalyticsで受け取られた場合は、次の手順に進みます。 そうでない場合は、次の項目を確認します。

* トリガーはAnalyticsで有効です
* MCIDとAnalyticsを使用するWebサイトがDTMで有効になっている
* トリガーの作成時には、正しいAnalyticsレポートスイートが使用されます。

**トリガーはキャンペーンが受け取ったか。**

トリガが受信されていない場合は、トリガがパイプラインから受信されたかどうかを確認します。

そうでない場合は、Adobeに連絡して、パイプラインエンドポイントの設定を確認してください。

該当する場合は、次のガイドラインに従います。

* キャンペーンデータソースの調整IDの種類を確認してください。
* 顧客IDデータソースは顧客属性を介して作成されます。
* Datasource IDを確認します。
* データソースの設定後にキャンペーンインスタンスを再起動するようにAdobeに依頼します。
* トリガーレポートでトリガーの解析の問題を確認します。

**トリガーのステータスは保留中ですか？**

そうでない場合は、次の手順に進みます。 該当する場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルがブロックリストにないことを確認します。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか。**

メッセージが無効な場合は、次の項目を確認します。

* 無効とマークされたトリガーエンリッチメントパーソナライゼーションフィールドについては、関連するeventCusResourceコレクションからトランザクションテンプレートを検証します。
* メッセージの形式の検証

