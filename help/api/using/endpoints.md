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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# エンドポイント {#endpoints}

Adobe Campaign REST APIで使用可能なエンドポイントは次のとおりです。

* **/profileAndServices**:既製のフィールドを操作します。 このエンドポイントでは、拡張フィールドにアクセスできません。
* **/profileAndServicesExt**:プロファイルまたはサービスのカスタムリソース拡張中に追加されたカスタムフィールドを操作します。 For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI&gt;**:トランザクションメッセージAPIとやり取りします（トランザクションメッセージAPIエンドポイントの名前は、インスタンスの設定によって異なります）。 詳しくは、[この節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/workflow/execution**:ワークフローとのやり取り 詳しくは、[この節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**:プライバシーAPIを操作して、プライバシーリクエストの自動処理を許可します。 詳しくは、[この節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/history**:プロファイルのマーケティング履歴を取得します。 Campaignの統合顧客プロファイルについて詳しくは、Campaignのドキュメントを参照 [してください](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

デフォルトでは、profileAndServices APIとprofileAndServicesExt APIで使用できる主なリソ **ースは** 、次 **** のとおりです。

* **/profile**:campaignデータベースのプロファイルを操作します。 サービスにプロファイルを追加するには、 **/serviceエンドポイントを使** 用します。 Campaignのプロファイルについて詳しくは、Campaignのドキュメントを参照 [してください](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:サブスクリプションサービスを管理します。 Campaignのサービスの詳細については、Campaignのドキュメントを参照 [してください](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>拡張または作成されたその他のリソースは、ProfileAndServicesExt **** APIを介してのみ使用できます。 アクセスするには、 **Profile** リソースにリンクする必要があります。
