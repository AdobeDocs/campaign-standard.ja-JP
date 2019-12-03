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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff05128d664db7afba57b020f59b9a98fc656f56

---


# カスタムリソースの操作 {#interacting-with-custom-resources}

/customResourcesエ **ンドポイントを使用すると** 、ACSカスタムエンティティをRESTで公開できます。 このAPIに基づいて、カスタムエンティティと外部エンドポイントの統合を利用できます。

/customResourcesの動作は、/profileAndServicesエンドポイントとまったく同じです。

このAPI内で公開されるカスタムエンティティは次のとおりです。

* 縦断図形にリンクされたすべての図形
* プロファイルエンティティの子にリンクされているすべてのエンティティ
* 縦断にリンクされていないすべてのエンティティと、これらのエンティティの子と孫です。

>[!NOTE]
>/profileAndServicesExtで使用できるカスタムエンティティは、/customResources APIに公開されません。

カスタムリソースからメタデータを取得する例を次に示します。

```
GET /customResources/resourceType/<customResourceName>
```

作成、更新、または削除を行うには、GET、POST、PATCH、DELETEが使用されます。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>プライバシーAPIエンドポイントとワークフロー(/privacy/privacyTool)は、プロファイルエンティティにリンクされていないカスタムリソースを管理していません。
>これらのカスタムリソースのPIIを管理し、クリーンアップする必要があります。 プライバシーツールの詳細については、ここをク [リックしてくださ](../../api/using/creating-a-privacy-request.md)い。

