---
title: エンドポイント
description: APIエンドポイントについて詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---


# エンドポイント {#endpoints}

Adobe CampaignREST APIで使用可能なエンドポイント：

* **/profileAndServices**:既製のフィールドを操作します。 このエンドポイントでは、拡張フィールドにアクセスできません。
* **/profileAndServicesExt**:プロファイルまたはサービスのカスタムリソース拡張時に追加されたカスタムフィールドを操作します。 For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**:トランザクションメッセージAPIとやり取りします(トランザクションメッセージAPIエンドポイントの名前は、インスタンスの設定に応じて異なります)。 詳しくは、[この節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/workflow/execution**:ワークフローとのやり取り 詳しくは、[この節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**:プライバシーAPIを操作して、プライバシー要求の自動処理を許可します。 詳しくは、[この節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/history**:プロファイルのマーケティング履歴を取得します。 キャンペーンに統合されたお客様プロファイルについて詳しくは、 [キャンペーンのドキュメントを参照してください](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

デフォルトでは、 **profileAndServices** APIおよびprofileAndServicesExt **** APIで使用できる主なリソースは次のとおりです。

* **/プロファイル**:キャンペーンデータベースのプロファイルとやり取りします。 サービスにプロファイルを追加するには、 **/service** endpointを使用します。 キャンペーンのプロファイルについて詳しくは、 [キャンペーンのドキュメントを参照してください](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:購読サービスの管理。 キャンペーンのサービスについて詳しくは、 [キャンペーンのドキュメントを参照してください](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>拡張または作成された他のすべてのリソースは、ProfileAndServicesExt **** APIを介してのみ使用できます。 アクセス可能にするには、 **プロファイル** ・リソースにリンクする必要があります。
