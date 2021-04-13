---
solution: Campaign Standard
product: campaign
title: カスタムリソース
description: API/を使用したカスタムリソース管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%

---

# カスタムリソースの操作 {#interacting-with-custom-resources}

**/customResources**&#x200B;エンドポイントを使用すると、キャンペーンのカスタムリソースをRESTで公開できます。 このAPIに基づき、カスタムエンティティと外部エンドポイントの統合を利用できます。

/customResourcesエンドポイントの動作は、/profileAndServicesエンドポイントとまったく同じです。

このAPIで公開されるカスタムリソースは次のとおりです。

* /profileAndServicesExtで公開されないすべてのエンティティ
* プロファイルにリンクされていないすべてのエンティティと、その子と孫です。
* デフォルトでは、何にもリンクされていないすべてのエンティティと、その子と孫が表示されます。

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
