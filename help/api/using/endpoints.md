---
title: エンドポイント
description: API エンドポイントの詳細を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# エンドポイント {#endpoints}

Adobe Campaign REST API で使用可能なエンドポイントは次のとおりです。

* **/profileAndServices**：標準搭載のフィールドを操作します。 このエンドポイントでは、拡張フィールドにアクセスできません。
* **/profileAndServicesExt**：プロファイルまたはサービスのカスタムリソース拡張時に追加されたカスタムフィールドを操作します。 カスタムリソースについて詳しくは、 [この節](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**：トランザクションメッセージ API とのやり取り（トランザクションメッセージ API エンドポイントの名前は、インスタンスの設定に応じて異なります）。 詳しくは、[この節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/workflow/execution**：ワークフローの操作 詳しくは、[この節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**：プライバシー API を操作して、プライバシーリクエストの自動処理を許可します。 詳しくは、[この節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/history**：プロファイルのマーケティング履歴を取得します。 Campaign での統合顧客プロファイルについて詳しくは、 [Campaign ドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

デフォルトでは、 **profileAndServices** および **profileAndServicesExt** API は次のとおりです。

* **/profile**:Campaign データベースからプロファイルを操作します。 サービスにプロファイルを追加するには、 **/service** endpoint. Campaign のプロファイルについて詳しくは、 [Campaign ドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**：購読サービスを管理します。 Campaign のサービスについて詳しくは、 [Campaign ドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>拡張または作成されたその他のリソースは、 **ProfileAndServicesExt** API のみ。 これらは、 **プロファイル** リソースに割り当てられます。
