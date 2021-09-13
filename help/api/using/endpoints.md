---
title: エンドポイント
description: APIエンドポイントについて詳しく説明します。
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

Adobe Campaign REST APIで使用可能なエンドポイントは次のとおりです。

* **/profileAndServices**:標準のフィールドを操作する。このエンドポイントでは、拡張フィールドにアクセスできません。
* **/profileAndServicesExt**:プロファイルまたはサービスのカスタムリソース拡張時に追加されたカスタムフィールドを操作する。カスタムリソースについて詳しくは、[この節](../../api/using/custom-resources.md)を参照してください。
* **/&lt;transactionalapi>**:トランザクションメッセージAPIとやり取りする（トランザクションメッセージAPIエンドポイントの名前は、インスタンスの設定に応じて異なります）。詳しくは、[この節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/workflow/execution**:ワークフローの操作詳しくは、[この節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**:プライバシーAPIを操作して、プライバシーリクエストの自動処理を許可する。詳しくは、[この節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/history**:プロファイルのマーケティング履歴を取得します。Campaignでの統合顧客プロファイルについて詳しくは、[Campaignのドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)を参照してください。

デフォルトでは、 **profileAndServices**&#x200B;および&#x200B;**profileAndServicesExt** APIで使用できる主なリソースは次のとおりです。

* **/profile**:Campaignデータベースのプロファイルを操作します。プロファイルをサービスに追加するには、**/service**&#x200B;エンドポイントを使用します。 Campaignのプロファイルについて詳しくは、[Campaignのドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)を参照してください。
* **/service**:購読サービスを管理します。Campaignのサービスについて詳しくは、[Campaignのドキュメント](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)を参照してください。

>[!NOTE]
>
>拡張または作成されたその他のリソースはすべて、 **ProfileAndServicesExt** API経由でのみ使用できます。 アクセス可能にするには、**プロファイル**&#x200B;リソースにリンクされている必要があります。
