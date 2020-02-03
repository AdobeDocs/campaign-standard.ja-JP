---
title: オーディエンスについて
description: クエリ、リストまたはファイルからオーディエンスを作成する方法と、Adobe Experience cloudからオーディエンスをインポートする方法について説明します。
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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# オーディエンスについて{#about-audiences}

オーディエンスは、ルールと属性に基づくプロファイルのリストです。

Adobe Campaignでは、クエリを使用してオーディエンスを手動で作成したり、専用のワークフローを自動的に使用したりできます。 また、Adobe Experience cloudの共有オーディエンスを使用することもできます。 すべてのオーディエンスが、Adobe Campaignのホームページまたはリンクからカードを介し **[!UICONTROL Audiences]**てアクセスできるリストに再グループ化さ**[!UICONTROL Audiences]** れます。

![](assets/audience_1.png)

Adobe Campaignでは、様々なオーディエンスタイプを操作できます。 オーディエンスのタイプは、作成方法に対応します。

* **[!UICONTROL Query]**:オーディエンスが、オーディエンスのリストからAdobe Campaign[データベース](../../automating/using/editing-queries.md#about-query-editor)のデータに関するクエリから作成されたことを示します。 クエリによって定義されたオーディエンスは、それ以降の使用のたびに再計算されます。
* **[!UICONTROL List]**:オーディエンスが固定されたプロファイルリストであることを示します。 これらのリストは、オーディエンスの保[存時に](../../automating/using/discovering-workflows.md)、データディメンションが認識されるワークフローで作成されます。 例えば、アクティビティのターゲット設定(特に**[!UICONTROL Query]** )後、またはファイルからインポートされたデータの調整後などです。
* **[!UICONTROL File]**:オーディエンスがファイルの読み込みワークフローから直接作成され[たこと](../../automating/using/load-file.md)、およびオーディエンスの保存時にデータディメンションが不明であったことを示します。
* **[!UICONTROL Experience Cloud]**:オーディエンスがAdobe Experience cloudから読み込まれたことを示します。 このオプションは、オーディエンス共有機能が設定されている場合にのみ使用できます。 詳しくは、Adobe Experience cloudからのオ[ーディエンスの読み込みを参照してください](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)。

![](assets/audience_type_selection.png)
