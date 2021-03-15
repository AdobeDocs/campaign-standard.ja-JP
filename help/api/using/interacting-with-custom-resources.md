---
solution: Campaign Standard
product: campaign
title: カスタムリソース
description: API/を使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---


# カスタムリソースの操作 {#interacting-with-custom-resources}

**/customResources**&#x200B;エンドポイントを使用すると、キャンペーンのカスタムリソースをRESTで公開できます。 このAPIに基づき、カスタムエンティティと外部エンドポイントの統合を利用できます。

/customResourcesエンドポイントの動作は、/profileAndServicesエンドポイントとまったく同じです。

このAPIで公開されるカスタムリソースは次のとおりです。

* プロファイルエンティティにリンクされているすべてのエンティティ
* プロファイルエンティティの子にリンクされているすべてのエンティティ
* プロファイルにリンクされていないすべてのエンティティと、その子と孫です。

>[!NOTE]
>/profileAndServicesExtで使用できるカスタムリソースは、/customResources APIに公開されません。

次に、カスタムリソースからメタデータを取得する例を示します。

```
GET /customResources/resourceType/<customResourceName>
```

作成、更新または削除を行うには、GET、POST、PATCH、DELETEを使用します。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>プライバシーAPIエンドポイントとワークフロー(/privacy/privacyTool)は、プロファイルエンティティにリンクされていないカスタムリソースを管理していません。
>これらのカスタムリソースのPIIを管理およびクリーンアップする責任はあります。 プライバシーツールの詳細については、[ここ](../../api/using/creating-a-privacy-request.md)をクリックしてください。

