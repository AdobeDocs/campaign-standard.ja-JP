---
title: オーディエンスについて
seo-title: オーディエンスについて
description: オーディエンスについて
seo-description: クエリー、リストまたはファイルからオーディエンスを構築する方法、およびAdobe Experience Cloudからのオーディエンスの読み込み方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: b3996642-96ec-489e- b146- c8c2cb52aa32
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: 管理-オーディエンス
discoiquuid: 750prop8d-67a5-4180- bfec-2a8e3098c812
context-tags: オーディエンス，ウィザード;オーディエンス、概要;配信、オーディエンス、戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# About audiences{#about-audiences}

オーディエンスは、ルールと属性に基づくプロファイルのリストです。

Adobe Campaignでは、クエリを使用して手動でオーディエンスを作成したり、専用ワークフローを使用して自動的にオーディエンスを作成したりできます。Adobe Experience Cloudから共有オーディエンスを使用することもできます。All of the audiences are regrouped into a list that can be accessed via the **[!UICONTROL Audiences]** card on the Adobe Campaign home page or from the **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

Adobe Campaignでは、様々なオーディエンスタイプを操作できます。オーディエンスのタイプは、そのオーディエンスの作成方法に対応します。

* **[!UICONTROL Query]**:オーディエンスは、Adobe Campaignデータベースからのデータの [クエリー](../../automating/using/editing-queries.md#about-query-editor) からオーディエンスが作成されたことを示します。クエリによって定義されたオーディエンスは、それぞれの使用時に再計算されます。
* **[!UICONTROL List]**:オーディエンスがプロファイルの固定リストであることを示します。These lists are created in a [workflow](../../automating/using/discovering-workflows.md), where the data dimension is known when saving the audience. For example, after targeting activities (especially **[!UICONTROL Query]** ) or after the reconciliation of data imported from a file.
* **[!UICONTROL File]**:は、オーディエンスが [ファイルインポート](../../automating/using/load-file.md) ワークフローから直接作成され、オーディエンスを保存するときにデータディメンションが不明であることを示します。
* **[!UICONTROL Experience Cloud]**:は、オーディエンスがAdobe Experience Cloudからインポートされたことを示します。このオプションは、オーディエンス共有機能が設定されている場合にのみ使用できます。For more information, see [Importing an audience from the Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

