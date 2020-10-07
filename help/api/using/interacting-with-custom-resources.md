---
title: カスタムリソース
description: API/を使用したカスタムリソース管理の詳細
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
source-wordcount: '183'
ht-degree: 3%

---


# カスタムリソースの操作 {#interacting-with-custom-resources}

**/customResources** エンドポイントを使用すると、ACSカスタムリソースをRESTで公開できます。 このAPIに基づき、カスタムエンティティと外部エンドポイントの統合を利用できます。

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
>これらのカスタムリソースのPIIを管理およびクリーンアップする責任はあります。 プライバシーツールの詳細については、 [ここをクリックしてください](../../api/using/creating-a-privacy-request.md)。

