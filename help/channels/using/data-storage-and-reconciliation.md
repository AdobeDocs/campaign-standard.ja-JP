---
title: データストレージと紐付け
seo-title: データストレージと紐付け
description: データストレージと紐付け
seo-description: Adobe Campaignでは、ランディングページに入力されたデータをユーザーが1回だけ管理する方法を定義できます。
page-status-flag: 常にアクティブ化されていない
uuid: 5b222ea2-6628-457f- a618- bfc0e5eb93dd
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: 899c7152- f415-4df9- b4b4-5ff3470a4e32
context-tags: landingPage， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Data storage and reconciliation{#data-storage-and-reconciliation}

データ紐付けパラメーターを使用すると、ランディングページに入力されたデータがユーザーによって送信された後にどのように管理されるかを定義できます。

これを行うには、次の手順に従います。

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_parameters_4.png)

1. Select the **[!UICONTROL Reconciliation key]**: these database fields (for example: email, first name, last name) are used to determine whether the visitor has a profile that is already known in the Adobe Campaign database. これにより、定義された更新方法のパラメーターに従って、プロファイルを更新または作成できます。
1. Define the **[!UICONTROL Form parameter mapping]**: this section allows you to map the landing page field parameters and those used in the reconciliation key.
1. Select the **[!UICONTROL Update strategy]**: if the reconciliation key recovers an existing database profile, you can choose for this profile to be updated with the data entered in the form or instead prevent this update.

