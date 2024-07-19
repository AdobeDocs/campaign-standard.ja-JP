---
title: 配信の概要
description: 標準の配信概要レポートを使用すると、送信数、バウンス数、開封数など、配信統計について説明できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryCirculationReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: d6ddc022-16ad-438b-8c6e-fc6abc704f09
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 1%

---

# 配信の概要{#delivery-summary}

**[!UICONTROL Delivery summary]** レポートには、1 つまたは複数のメールに関連する主な情報の詳細が表示されます。

![](assets/campaign_reports_1.png)

各テーブルは、概要番号とグラフで表されます。 それぞれのビジュアライゼーション設定で、詳細の表示方法を変更できます。

**配信統計** テーブルには、次のような送信済みメールに使用できるデータが含まれています。

* **[!UICONTROL Processed/sent]**：配信に対する送信の合計数。
* **[!UICONTROL Delivered]**：送信されたメッセージの合計数に対して、正常に送信できたメッセージの数。 発生したエラー（バウンス）は考慮されます。 ただし、スパム報告や「不在」などの不在メッセージは考慮されません。
* **[!UICONTROL Bounces + Errors]**：配信と自動返信処理の間に、送信されたメッセージの合計数に関して累積したエラーの合計数。

**開封とクリック数** テーブルには、各配信の受信者アクティビティに関する次のような使用可能なデータが含まれています。

* **クリック**：配信でコンテンツがクリックされた回数。
* **開封**：配信でメッセージが開かれた回数。
* **ユニーク開封数**：配信されたメッセージを開いた受信者の数。
* **ユニーククリック数**：配信のコンテンツをクリックした受信者の数。

**ドメインの再パーティション** テーブルには、受信者のドメインに応じた配信のステータスが表示されます。
