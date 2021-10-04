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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 1%

---

# トリガーのテスト{#testing-your-triggers}

次のトラブルシューティングのヒントは、Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題の解決に役立ちます。

**機能は有効化されていますか。**

トリガー- Campaign 統合がアクティブ化されているかどうかを確認するには、左上隅のAdobe Campaignロゴをクリックし、 **[!UICONTROL Marketing plans]** / **[!UICONTROL Transactional messages]** を選択します。 **[!UICONTROL Experience Cloud Triggers]** 項目が表示されます。

表示されたら、次の手順に進みます。

そうでない場合は、担当のAdobeアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 [ 機能の有効化 ](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality) を参照してください。

**トリガー**

[Campaign でのマッピングされたトリガーの作成 ](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) で説明されている手順に従って、トリガーを作成します。

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガーのエンドポイント接続が失敗したことを意味します。 トリガーがExperience Cloud(Activation Services) でプロビジョニングされているかどうかを確認します。 そうでない場合は、担当のAdobeアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloud会社名
* IMS 組織 ID
* Analytics ログイン会社名 (Marketing Cloud会社名と同じ )

**トリガー**

[Campaign でのマッピングされたトリガーの作成 ](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) で説明されている手順に従って、トリガーを公開します。

公開が成功した場合は、次の手順に進みます。 そうでない場合は、Adobeに連絡してインスタンスを再起動し、もう一度やり直してください。

**Web サイトからトリガーを生成する**

[ トランザクションメッセージテンプレートの編集 ](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) で説明されている手順に従って、トランザクションテンプレートを編集し、公開します。 次に、Web サイトからのトリガーの生成をテストします。

トリガーが Analytics で受信された場合は、次の手順に進みます。 そうでない場合は、次の項目を確認します。

* トリガーは Analytics で有効
* MCID と Analytics を使用する Web サイトは、DTM で有効になっています
* トリガーの作成時には、適切な Analytics レポートスイートが使用されます

**トリガーは Campaign で受信されますか？**

そうでない場合は、トリガーがパイプラインから受信されたかどうかを確認します。

そうでない場合は、Adobeに連絡して、パイプラインエンドポイントの設定を確認してください。

その場合は、次のガイドラインに従います。

* Campaign データソースで紐付け ID タイプを確認します。
* 顧客 ID データソースは、顧客属性を使用して作成されます。
* データソース ID を確認します。
* Adobeに、データソース設定の後で Campaign インスタンスを再起動するように依頼します。
* トリガーレポートでのトリガー解析の問題を確認します。

**トリガーのステータスは保留中ですか？**

そうでない場合は、次の手順に進みます。 その場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルがオンになっていないことを確ブロックリスト認します。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか？**

メッセージが無効な場合は、次の項目を確認します。

* 無効とマークされたトリガーエンリッチメントのパーソナライゼーションフィールドについては、関連する eventCusResource コレクションからトランザクションテンプレートを検証します。
* メッセージ形式の検証
