---
solution: Campaign Standard
product: campaign
title: エンドポイント
description: APIエンドポイントについて詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 10%

---


# エンドポイント {#endpoints}

Adobe CampaignREST APIで使用可能なエンドポイント：

* **/profileAndServices**:既製のフィールドを操作します。このエンドポイントでは、拡張フィールドにアクセスできません。
* **/profileAndServicesExt**:プロファイルまたはサービスのカスタムリソース拡張時に追加されたカスタムフィールドを操作します。カスタムリソースの詳細については、[この](../../api/using/custom-resources.md)を参照してください。
* **/&lt;transactionalapi>**:トランザクションメッセージAPIとやり取りします(トランザクションメッセージAPIエンドポイントの名前は、インスタンスの設定に応じて異なります)。詳しくは、[こちらの節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/workflow/execution**:ワークフローとのやり取り詳しくは、[こちらの節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**:プライバシーAPIを操作して、プライバシー要求の自動処理を許可します。詳しくは、[こちらの節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/history**:プロファイルのマーケティング履歴を取得します。キャンペーンに統合されたお客様のプロファイルについて詳しくは、[キャンペーンドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)を参照してください。

デフォルトでは、**profileAndServices**&#x200B;および&#x200B;**profileAndServicesExt** APIで使用できる主なリソースは次のとおりです。

* **/プロファイル**:キャンペーンデータベースのプロファイルとやり取りします。サービスにプロファイルを追加するには、**/service**&#x200B;エンドポイントを使用します。 キャンペーンのプロファイルについて詳しくは、[キャンペーンドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)を参照してください。
* **/service**:購読サービスの管理。キャンペーンのサービスについて詳しくは、[キャンペーンドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)を参照してください。

>[!NOTE]
>
>拡張または作成された他のすべてのリソースは、**ProfileAndServicesExt** API経由でのみ利用できます。 アクセスするには、**プロファイル**&#x200B;リソースにリンクする必要があります。
