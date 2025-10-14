---
title: カスタムリソースとのやり取り
description: API を使用したカスタムリソース管理の詳細情報/
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
ht-degree: 0%

---

# カスタムリソースとのやり取り {#interacting-with-custom-resources}

**/customResources** エンドポイントを使用すると、Campaign のカスタムリソースを REST で公開できます。 この API に基づいて、カスタムエンティティと外部エンドポイントの統合を使用できます。

/customResources エンドポイントの動作は、/profileAndServices エンドポイントとまったく同じです。

この API 内で公開されるカスタムリソースは次のとおりです。

* /profileAndServicesExt で公開されないすべてのエンティティ
* プロファイルにリンクされていないすべてのエンティティ。これらのエンティティについては、その子と孫。
* デフォルトでは、何にもリンクされていないすべてのエンティティ、およびその子と孫です。

>[!NOTE]
>/profileAndServicesExt 以下で使用可能なカスタムリソースは、/customResources API では公開されません。


次に、カスタムリソースからメタデータを取得する例を示します。

```
GET /customResources/resourceType/<customResourceName>
```

作成、更新、削除を行うには、GET、POST、PATCH、DELETEを使用します。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>プライバシー API エンドポイントとワークフロー（/privacy/privacyTool）が、プロファイルエンティティにリンクされていないカスタムリソースを管理していません。
>これらのカスタムリソースの PII を管理およびクリーンアップする責任があります。 プライバシーツールについて詳しくは、[&#x200B; ここをクリック &#x200B;](../../api/using/creating-a-privacy-request.md) してください。
