---
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
TQID: 'https://experienceleague.adobe.com/NPcDi1kh8Ye1Y14CAwVxBLW-0qwHnpFRUQ2WYj7BJbI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 85%
---
# オーディエンスについて{#about-audiences}

オーディエンスは、ルールと属性に基づくプロファイルのリストです。

Adobe Campaign を使用すると、クエリを使用してオーディエンスを手動で作成するか、専用ワークフローを使用してオーディエンスを自動で作成できます。 Adobe Experience Cloud の共有オーディエンスを使用することもできます。 すべてのオーディエンスは、リストに再グループ化され、Adobe Campaign ホームページ上の **[!UICONTROL Audiences]** カードまたは **[!UICONTROL Audiences]** リンクからアクセスできるようになります。

![](assets/audience_1.png)

Adobe Campaign では、様々な種類のオーディエンスを操作できます。 オーディエンスのタイプは、その作成方法に対応します。

* **[!UICONTROL Query]**: オーディエンスのリストを介して、Adobe Campaign データベースのデータに対して[&#x200B; クエリ &#x200B;](../../automating/using/editing-queries.md#about-query-editor)を使用してオーディエンスが作成されたことを示します。 クエリが定義したオーディエンスは、それ以降使用されるたびに再計算されます。
* **[!UICONTROL List]**：オーディエンスがプロファイルの固定リストであることを示します。 これらのリストは、オーディエンスの保存時にデータディメンションが認識されている[ワークフロー](../../automating/using/get-started-workflows.md)で作成されます。 例えば、アクティビティのターゲティング後（特に&#x200B;**[!UICONTROL Query]**）、またはファイルからインポートされたデータの紐付け後に行います。
* **[!UICONTROL File]**：オーディエンスが[ファイルインポート](../../automating/using/load-file.md)ワークフローから直接作成されたもので、オーディエンスの保存時にデータディメンションが不明であったことを示します。
* **[!UICONTROL Experience Cloud]**：オーディエンスが Adobe Experience Cloud からインポートされたことを示します。 このオプションは、オーディエンス共有機能が設定されている場合にのみ使用できます。 詳しくは、[Adobe Experience Cloud からのオーディエンスのインポート](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)を参照してください。

![](assets/audience_type_selection.png)
