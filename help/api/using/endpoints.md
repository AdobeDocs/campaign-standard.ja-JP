---
title: エンドポイント
description: API エンドポイントについて詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 10%
---
# エンドポイント {#endpoints}

Adobe Campaign REST APIで使用できるエンドポイント：

* **/profileAndServices**：標準搭載のフィールドを操作します。 このエンドポイントでは拡張フィールドにアクセスできません。
* **/profileAndServicesExt**: プロファイルまたはサービスのカスタム リソースの拡張中に追加されたカスタム フィールドを操作します。 カスタムリソースについて詳しくは、[この節](../../api/using/custom-resources.md)を参照してください。
* **/&lt;transactionalAPI>**: トランザクションメッセージ APIを操作します（トランザクションメッセージ API エンドポイントの名前は、インスタンス設定によって異なります）。 詳しくは、[この節](../../api/using/managing-transactional-messages.md)を参照してください。
* **/ワークフロー/実行**: ワークフローを操作します。 詳しくは、[この節](../../api/using/controlling-a-workflow.md)を参照してください。
* **/privacy/privacyTool**: privacy APIと対話して、プライバシーリクエストの自動処理を許可します。 詳しくは、[この節](../../api/using/creating-a-privacy-request.md)を参照してください。
* **/履歴**: プロファイルのマーケティング履歴を取得します。 Campaignでの統合顧客プロファイルについて詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)を参照してください。

デフォルトでは、**profileAndServices**&#x200B;および&#x200B;**profileAndServicesExt** APIで使用できる主なリソースは次のとおりです。

* **/プロファイル**: Campaign データベースのプロファイルを操作します。 プロファイルをサービスに追加するには、**/service** エンドポイントを使用します。 Campaignのプロファイルについて詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)を参照してください。
* **/サービス**：購読サービスを管理します。 Campaignのサービスについて詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)を参照してください。

>[!NOTE]
>
>拡張または作成された他のすべてのリソースは、**ProfileAndServicesExt** API経由でのみ使用できます。 アクセスするには、これらのユーザーを&#x200B;**プロファイル** リソースにリンクする必要があります。
