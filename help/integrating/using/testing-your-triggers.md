---
title: トリガーのテスト
description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd74905985734412b4fb11ad11d70faf9fcc9ca6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# トリガーのテスト{#testing-your-triggers}

次のトラブルシューティングのヒントは、TriggersをAdobe Campaignと共に使用する場合に発生する最も一般的な問題の解決に役立ちます。

**機能は有効になっているか。**

Triggers -キャンペーン統合がアクティブ化されているかどうかを確認するには、Adobe Campaignのロゴをクリックし、左上隅で **[!UICONTROL Marketing plans]** /を選択し **[!UICONTROL Transactional messages]**&#x200B;ます。 項目が表示され **[!UICONTROL Experience Cloud Triggers]** ます。

表示されたら、次の手順に進みます。

ログインしていない場合は、アドビのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 機能の [アクティブ化を参照してください](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**トリガーを作成してみます。**

「キャンペーンでのマッピングされたトリガーの [作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 」で説明されている手順に従って、トリガーを作成します。

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガーの終点の接続に失敗したことを意味します。 TriggersがExperience Cloudでプロビジョニングされているかどうかを確認します(アクティベーションサービス)。 ログインしていない場合は、アドビのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloud会社名
* IMS組織ID
* Analyticsログイン会社(Marketing Cloud会社名と同じ名前を使用できます)

**トリガーを公開してみる**

「キャンペーンでのマッピングされたトリガーの [作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 」で説明されている手順に従って、トリガーを発行します。

パブリケーションが成功した場合は、次のステップに進みます。 インスタンスが存在しない場合は、アドビに連絡してインスタンスを再起動し、もう一度やり直してください。

**Webサイトからのトリガーの生成**

トランザクションテンプレートを編集および公開するには、 [トランザクションメッセージテンプレートの編集](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) （英語のみ）に記載されている手順に従います。 次に、Webサイトからのトリガーの生成をテストします。

トリガーがAnalyticsによって受け取られた場合は、次のステップに進みます。 そうでない場合は、次の項目を確認します。

* トリガーはAnalyticsに対して有効です
* MCIDとAnalyticsを使用するWebサイトがDTMで有効になっています
* トリガーの作成時には、正しいAnalyticsレポートスイートが使用されます

**トリガーはキャンペーンが受け取ったか。**

トリガが受信されていない場合は、トリガがパイプラインから受信されたかどうかを確認します。

見つからない場合は、アドビに連絡して、パイプラインエンドポイントの設定を確認してください。

該当する場合は、次のガイドラインに従います。

* キャンペーンデータソースの調整IDの種類を確認してください。
* 顧客IDデータソースは顧客属性を介して作成されます。
* Datasource IDを確認します。
* データソースの設定後にキャンペーンインスタンスを再起動するようアドビに依頼します。
* トリガーレポートでトリガーの解析の問題を確認します。

**トリガーのステータスは保留中ですか？**

そうでない場合は、次の手順に進みます。 該当する場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルがブロックリスト上にないことを確認します。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか。**

メッセージが無効な場合は、次の項目を確認します。

* 無効とマークされたトリガーエンリッチメントパーソナライゼーションフィールドについては、関連するeventCusResourceコレクションからトランザクションテンプレートを検証します。
* メッセージの形式の検証

