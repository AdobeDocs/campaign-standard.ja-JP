---
title: プロファイルについて
description: 連絡先は、Campaignデータベースにプロファイルとして保存され、ライフサイクル全体を通じて更新されます。
page-status-flag: never-activated
uuid: 087f91a4-6e69-488e-9aa0-424d23d396ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: a35e736c-a17b-420c-8411-0debc3c6275a
context-tags: recipient,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fcb6a145b19b68865babba659bf0bfb7623397c8

---


# プロファイルについて{#about-profiles}

Adobe Campaignでは、連絡先をライフサイクル全体を通じて管理できます。作成、インポート、ターゲット設定、アクショントラッキング、更新など 連絡先は、次の情報を含むプロファイルとしてデータベースに保存されます。姓、名、住所、購読、配信など

>[!NOTE]
>
>プロファイルは、Adobe Campaign Standard APIを使用しても利用できます。 For more on this, refer to the [dedicated documentation](../../api/using/retrieving-profiles.md).

![](assets/marketing_history.png)

キャンペーンを作成する際に、単純な条件またはアドバンス条件に従ってプロファイルを選択することで、配信のターゲットを定義できます。 技術的には、プロファイルは、ターゲット設定、資格および追跡の動作に必要なすべての情報を含む、データベース内のエントリです。

プロファイルは次のようになります。組織に応じて、顧客、見込み客、ニュースレターを購読している個人、受信者、ユーザー、またはその他の宗派。 様々なタイプのプロファイルを定義するには、ターゲットディメンシ [ョンを使用しま](../../automating/using/query.md#targeting-dimensions-and-resources)す。
