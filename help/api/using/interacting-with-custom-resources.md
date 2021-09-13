---
title: カスタムリソース
description: APIを使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---

# カスタムリソースの操作 {#interacting-with-custom-resources}

**/customResources**&#x200B;エンドポイントを使用すると、CampaignのカスタムリソースをRESTで公開できます。 このAPIに基づいて、カスタムエンティティと外部エンドポイントの統合を利用できます。

/customResourcesエンドポイントの動作は、/profileAndServicesエンドポイントとまったく同じです。

このAPIで公開されるカスタムリソースは次のとおりです。

* /profileAndServicesExtに公開されていないすべてのエンティティ
* プロファイルにリンクされていないすべてのエンティティと、それらのエンティティの子と孫。
* デフォルトでは、何にもリンクされていないすべてのエンティティと、その子と孫が対象となります。

>[!NOTE]
>/profileAndServicesExtの下にあるカスタムリソースは、 /customResources APIでは公開されません。


次に、カスタムリソースからメタデータを取得する例を示します。

```
GET /customResources/resourceType/<customResourceName>
```

作成、更新または削除を実行するには、GET、POST、PATCH、DELETEが使用されます。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>プライバシーAPIエンドポイントとワークフロー(/privacy/privacyTool)は、プロファイルエンティティにリンクされていないカスタムリソースを管理しません。
>これらのカスタムリソースのPIIを管理およびクリーンアップする責任はユーザーが負います。 プライバシーツールの詳細については、[ここ](../../api/using/creating-a-privacy-request.md)をクリックしてください。
