---
title: オーディエンスについて
description: クエリー、リストーまたはファイルからオーディエンスを作成する方法と、Adobe Experience Cloudからを読み込む方法について説明します。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# オーディエンスについて{#about-audiences}

オーディエンスは、ルールと属性に基づくプロファイルのリストです。

Adobe Campaignを使用すると、クエリを使用して手動でオーディエンスを作成したり、専用ワークフローを自動的に使用したりできます。 Adobe Experience Cloudの共有オーディエンスーを使用することもできます。 すべてのオーディエンスは、リストに再グループ化され、Adobe Campaignホームページ上の **[!UICONTROL Audiences]** カードまたはリンクからアクセスできるようにな **[!UICONTROL Audiences]** ります。

![](assets/audience_1.png)

Adobe Campaignでは、様々な種類のオーディエンスを操作できます。 オーディエンスのタイプは、その作成方法に対応します。

* **[!UICONTROL Query]**: オーディエンスが、オーディエンスのリストのAdobe Campaignデータベースの [クエリ](../../automating/using/editing-queries.md#about-query-editor) から作成されたことを示します。 クエリが定義したオーディエンスは、それ以降の使用のたびに再計算されます。
* **[!UICONTROL List]**: は、オーディエンスがプロファイルの固定リストであることを示します。 これらのリストは、オーディエンスの保存時にデータディメンションが認識される [ワークフロー](../../automating/using/get-started-workflows.md)（ワークフロー）で作成されます。 例えば、アクティビティのターゲット設定(特に **[!UICONTROL Query]** )後、またはファイルからインポートしたデータの調整後などです。
* **[!UICONTROL File]**: は、オーディエンスが [ファイルの読み込み](../../automating/using/load-file.md) 、ワークフローから直接作成されたもので、オーディエンスの保存時にデータディメンションが不明であったことを示します。
* **[!UICONTROL Experience Cloud]**: は、オーディエンスがAdobe Experience Cloudから読み込まれたことを示します。 このオプションは、オーディエンス共有機能が設定されている場合にのみ使用できます。 詳しくは、「Adobe Experience Cloudからのオーディエンスの [読み込み](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)」を参照してください。

![](assets/audience_type_selection.png)
