---
title: エンドポイント
description: API エンドポイントの詳細情報。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 11%

---

# エンドポイント {#endpoints}

Adobe Campaign REST API で使用可能なエンドポイントは次のとおりです。

* **/profileAndServices**：標準提供フィールドとやり取りする。 このエンドポイントでは、拡張フィールドにアクセスできません。
* **/profileAndServicesExt**：プロファイルまたはサービスのカスタムリソース拡張時に追加されたカスタムフィールドを操作します。 カスタムリソースについて詳しくは、[ この節 ](../../api/using/custom-resources.md) を参照してください。
* **/&lt;transactionAPI>**：トランザクションメッセージ API を操作します（トランザクションメッセージ API エンドポイントの名前は、インスタンスの設定によって異なります）。 詳しくは、[この節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/workflow/execution**：ワークフローを操作します。 詳しくは、[この節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**：プライバシー API を操作して、プライバシーリクエストの自動処理を許可します。 詳しくは、[この節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/history**：プロファイルのマーケティング履歴を取得します。 Campaign の統合顧客プロファイルについて詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html) を参照してください。

デフォルトでは、**profileAndServices** および **profileAndServicesExt** API で使用できる主なリソースは次のとおりです。

* **/profile**:Campaign データベース内のプロファイルを操作します。 サービスにプロファイルを追加するには、**/service** エンドポイントを使用します。 Campaign のプロファイルについて詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html) を参照してください。
* **/service**：購読サービスを管理します。 Campaign のサービスについて詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html) を参照してください。

>[!NOTE]
>
>拡張または作成されたその他すべてのリソースは、**ProfileAndServicesExt** API からのみ使用できます。 アクセスするには、これらのプロファイルが **プロファイル** リソースにリンクされている必要があります。
