---
title: カスタムリソースの操作
description: API を使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# カスタムリソースの操作 {#interacting-with-custom-resources}

この **/customResources** endpoint を使用すると、Campaign のカスタムリソースを REST で表示できます。 この API に基づいて、カスタムエンティティと外部エンドポイントの統合を利用できます。

/customResources エンドポイントの動作は、/profileAndServices エンドポイントとまったく同じです。

この API 内で公開されるカスタムリソースは次のとおりです。

* /profileAndServicesExt に公開されていないすべてのエンティティ
* プロファイルにリンクされていないすべてのエンティティと、そのエンティティの子と孫。
* デフォルトでは、何にもリンクされていないすべてのエンティティと、その子と孫に関連付けられています。

>[!NOTE]
>/profileAndServicesExt の下にあるカスタムリソースは、/customResources API では公開されません。


次に、カスタムリソースからメタデータを取得する例を示します。

```
GET /customResources/resourceType/<customResourceName>
```

作成、更新または削除を実行するには、GET、POST、PATCH、DELETEが使用されます。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>プライバシー API エンドポイントとワークフロー (/privacy/privacyTool) は、プロファイルエンティティにリンクされていないカスタムリソースを管理していません。
>これらのカスタムリソースの PII を管理およびクリーンアップする必要があります。 プライバシーツールについて詳しくは、 [ここをクリック](../../api/using/creating-a-privacy-request.md).
