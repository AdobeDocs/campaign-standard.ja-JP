---
title: トリガーのテスト
description: Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題を解決するのに役立つ、トラブルシューティングのヒントを説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# トリガーのテスト{#testing-your-triggers}

Adobe Campaignでトリガーを使用する際に発生する可能性のある最も一般的な問題を解決するのに役立つトラブルシューティングのヒントを次に示します。

**機能はアクティブ化されていますか？**

「トリガー - Campaign」統合がアクティブかどうかを確認するには、左上隅のAdobe Campaign ロゴをクリックして、**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** を選択します。 **[!UICONTROL Experience Cloud Triggers]** の項目が表示されます。

表示された場合は、次の手順に進みます。

そうでない場合は、Adobe アカウントのエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 [&#x200B; 機能のアクティベート &#x200B;](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality) を参照してください。

**トリガーを作成してみる**

[Campaign でのマッピングされたトリガーの作成 &#x200B;](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) の手順に従って、トリガーを作成します。

トリガーを作成した場合は、次の手順に進みます。 そうでない場合は、トリガーエンドポイントの接続が失敗したことを示します。 Experience Cloud（アクティベーションサービス）でトリガーがプロビジョニングされているかどうかを確認します。 そうでない場合は、Adobe アカウントのエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。 次の情報が必要です。

* Marketing Cloudの会社名
* 組織 ID
* Analytics ログイン会社（Marketing Cloudの会社名と同じ場合があります）

**トリガーを公開してみてください**

[Campaign でのマッピングされたトリガーの作成 &#x200B;](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) の手順に従って、トリガーを公開します。

公開が成功した場合は、次の手順に進みます。 そうでない場合は、Adobeに連絡してインスタンスを再起動し、もう一度試してください。

**Web サイトからトリガーを生成**

[&#x200B; トランザクションメッセージテンプレートの編集 &#x200B;](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) の手順に従って、トランザクションテンプレートを編集して公開します。 次に、web サイトからトリガーを生成するテストを行います。

Analytics がトリガーを受け取った場合は、次の手順に進みます。 表示されない場合は、次の項目を確認してください。

* Analytics に対してトリガーが有効になっています
* MCID と Analytics を使用する web サイトは、DTM で有効になっています
* トリガーの作成時には、正しい Analytics レポートスイートが使用されます

**Campaign はトリガーを受け取っていますか？**

そうでない場合は、パイプラインからトリガーを受信したかどうかを確認します。

設定されていない場合は、Adobeに連絡して、パイプラインエンドポイントの設定を確認してください。

その場合は、次のガイドラインに従います。

* Campaign データソースで紐付け ID タイプを確認します。
* CustomerId データソースは、顧客属性を使用して作成されます。
* データソース ID を確認します。
* データソース設定の後、Campaign インスタンスを再起動するようにAdobeに依頼します。
* トリガーレポートでトリガーの解析の問題を確認します。

**トリガーは保留中ステータスですか？**

そうでない場合は、次の手順に進みます。 その場合は、次のガイドラインに従います。

* トランザクションテンプレートが公開されていることを確認します。
* プロファイルがオンになっていないことを確認します。^ブロックリスト。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか？**

メッセージが無効な場合は、次の項目を確認してください。

* 無効とマークされたトリガーエンリッチメントパーソナライゼーションフィールドについて、関連する eventCusResource コレクションからトランザクションテンプレートを検証します。
* メッセージ形式の検証
