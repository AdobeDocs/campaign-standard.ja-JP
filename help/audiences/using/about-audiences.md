---
title: オーディエンスについて
description: クエリやリスト、ファイルからオーディエンスを作成する方法と、Adobe Experience Cloud からオーディエンスをインポートする方法について説明します。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# オーディエンスについて{#about-audiences}

オーディエンスは、ルールと属性に基づくプロファイルのリストです。

Adobe Campaign を使用すると、クエリを使用してオーディエンスを手動で作成するか、専用ワークフローを使用してオーディエンスを自動で作成できます。Adobe Experience Cloud の共有オーディエンスを使用することもできます。すべてのオーディエンスは、リストに再グループ化され、Adobe Campaign ホームページ上の **[!UICONTROL Audiences]** カードまたは **[!UICONTROL Audiences]** リンクからアクセスできるようになります。

![](assets/audience_1.png)

Adobe Campaign では、様々な種類のオーディエンスを操作できます。オーディエンスのタイプは、その作成方法に対応します。

* **[!UICONTROL Query]**:は、オーディエンスがオーディエンスのリストを介してAdobe Campaignデータベースのデータに [クエリ](../../automating/using/editing-queries.md#about-query-editor) ()を使用して作成されたことを示します。 クエリが定義したオーディエンスは、それ以降使用されるたびに再計算されます。
* **[!UICONTROL List]**：オーディエンスがプロファイルの固定リストであることを示します。これらのリストは、オーディエンスの保存時にデータディメンションが認識されている[ワークフロー](../../automating/using/get-started-workflows.md)で作成されます。例えば、ターゲティングアクティビティの後（特に「**[!UICONTROL Query]**」）、またはファイルからインポートしたデータの紐付け後などです。
* **[!UICONTROL File]**：オーディエンスが[ファイルインポート](../../automating/using/load-file.md)ワークフローから直接作成されたもので、オーディエンスの保存時にデータディメンションが不明であったことを示します。
* **[!UICONTROL Experience Cloud]**：オーディエンスが Adobe Experience Cloud からインポートされたことを示します。このオプションは、オーディエンス共有機能が設定されている場合にのみ使用できます。詳しくは、[Adobe Experience Cloud からのオーディエンスのインポート](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)を参照してください。

![](assets/audience_type_selection.png)
