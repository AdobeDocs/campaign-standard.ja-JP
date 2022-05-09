---
title: トリガーのテスト
description: Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題を解決するのに役立つトラブルシューティングのヒントを説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# トリガーのテスト{#testing-your-triggers}

次のトラブルシューティングのヒントは、Adobe Campaignでトリガーを使用する際に発生する最も一般的な問題を解決するのに役立ちます。

**機能は有効化されていますか？**

トリガー- Campaign 統合が有効になっているかどうかを確認するには、左上隅のAdobe Campaignロゴをクリックし、 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. 次のように表示されます。 **[!UICONTROL Experience Cloud Triggers]** 項目。

表示されたら、次の手順に進みます。

そうでない場合は、Adobeのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 詳しくは、 [機能の有効化](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**トリガー**

次に示す手順に従います： [Campaign でのマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) をクリックしてトリガーを作成

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガーエンドポイントの接続に失敗したことを意味します。 トリガーがExperience Cloud(Activation services) でプロビジョニングされているかどうかを確認します。 そうでない場合は、Adobeのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloud会社名
* 組織 ID
* Analytics ログイン会社名 (Marketing Cloud会社名と同じ )

**トリガーの公開**

次に示す手順に従います： [Campaign でのマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) をクリックして、トリガーを公開します。

公開が成功した場合は、次の手順に進みます。 そうでない場合は、Adobeに連絡してインスタンスを再起動し、もう一度試してください。

**Web サイトからトリガーを生成する**

次に示す手順に従います： [トランザクションメッセージテンプレートの編集](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) トランザクションテンプレートを編集して公開する場合。 次に、Web サイトからのトリガーの生成をテストします。

Analytics がトリガーを受け取った場合は、次の手順に進みます。 そうでない場合は、次の項目を確認します。

* トリガーは Analytics で有効になっています
* MCID と Analytics を使用する Web サイトは、DTM で有効になっています
* トリガーの作成時に、適切な Analytics レポートスイートが使用される

**トリガーは Campaign で受信されますか？**

そうでない場合は、トリガーがパイプラインから受信されたかどうかを確認します。

そうでない場合は、Adobeに連絡して、パイプラインエンドポイントの設定を確認してください。

その場合は、次のガイドラインに従います。

* Campaign データソースで紐付け ID タイプを確認します。
* 顧客 ID データソースは、顧客属性を使用して作成されます。
* データソース ID を確認します。
* Adobeに、データソースの設定後に Campaign インスタンスを再起動するよう依頼します。
* トリガーレポートでトリガー解析の問題を確認します。

**トリガーのステータスは保留中ですか？**

そうでない場合は、次の手順に進みます。 その場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルがにないことを確認しブロックリストます。
* タイポロジルールの適用を確認する。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか？**

メッセージが無効な場合は、次の項目を確認してください。

* 無効とマークされたトリガーエンリッチメントパーソナライゼーションフィールドについては、関連する eventCusResource コレクションからトランザクションテンプレートを検証します。
* メッセージ形式の検証
