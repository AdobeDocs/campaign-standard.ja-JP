---
solution: Campaign Standard
product: campaign
title: オーディエンスについて
description: クエリやリスト、ファイルからオーディエンスを作成する方法と、Adobe Experience Cloud からオーディエンスをインポートする方法について説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 91%

---

# オーディエンスについて{#about-audiences}

オーディエンスは、ルールと属性に基づくプロファイルのリストです。

Adobe Campaign を使用すると、クエリを使用してオーディエンスを手動で作成するか、専用ワークフローを使用してオーディエンスを自動で作成できます。Adobe Experience Cloud の共有オーディエンスを使用することもできます。すべてのオーディエンスは、リストに再グループ化され、Adobe Campaign ホームページ上の **[!UICONTROL Audiences]** カードまたは **[!UICONTROL Audiences]** リンクからアクセスできるようになります。

![](assets/audience_1.png)

Adobe Campaign では、様々な種類のオーディエンスを操作できます。オーディエンスのタイプは、その作成方法に対応します。

* **[!UICONTROL Query]**:オーディエンスが、Adobe Campaignデータベースのクエ [](../../automating/using/editing-queries.md#about-query-editor) リオンデータを使用してオーディエンスが作成されたことを示します。クエリが定義したオーディエンスは、それ以降使用されるたびに再計算されます。
* **[!UICONTROL List]**：オーディエンスがプロファイルの固定リストであることを示します。これらのリストは、オーディエンスの保存時にデータディメンションが認識されている[ワークフロー](../../automating/using/get-started-workflows.md)で作成されます。例えば、ターゲティングアクティビティの後（特に「**[!UICONTROL Query]**」）、またはファイルからインポートしたデータの紐付け後などです。
* **[!UICONTROL File]**：オーディエンスが[ファイルインポート](../../automating/using/load-file.md)ワークフローから直接作成されたもので、オーディエンスの保存時にデータディメンションが不明であったことを示します。
* **[!UICONTROL Experience Cloud]**：オーディエンスが Adobe Experience Cloud からインポートされたことを示します。このオプションは、オーディエンス共有機能が設定されている場合にのみ使用できます。詳しくは、[Adobe Experience Cloud からのオーディエンスのインポート](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)を参照してください。

![](assets/audience_type_selection.png)
