---
solution: Campaign Standard
product: campaign
title: 配信の概要
description: すぐに使用できる配信サマリレポートを使用して、送信数、バウンス数、開数など、配信の統計情報を確認します。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryCirculationReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 1%

---


# 配信の概要{#delivery-summary}

この **[!UICONTROL Delivery summary]** レポートは、電子メールまたは複数の電子メールに関連するメイン情報を詳細に示します。

![](assets/campaign_reports_1.png)

各表は、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

配信統計 **表には** 、次のような送信済み電子メールに使用できるデータが含まれます。

* **[!UICONTROL Processed/sent]**:配信の送信の合計数です。
* **[!UICONTROL Delivered]**:送信されたメッセージの合計数に関連して、正常に送信されたメッセージの数。 発生したエラー（バウンス）が考慮されます。 しかし、苦情（スパム申告）や「不在」などの不在メッセージは考慮されません。
* **[!UICONTROL Bounces + Errors]**:配信および自動返信処理中に発生したエラーの合計数で、送信されたメッセージの合計数に関連して計算されたエラーの合計数。

「 **開く」および「クリック数** 」の表には、各配信の受信者アクティビティに使用できる次のようなデータが含まれます。

* **クリック**:配信内でコンテンツがクリックされた回数。
* **開く**:配信でメッセージが開かれた回数。
* **個別オープン**:配信を開いた受信者の数。
* **個別クリック数**:配信内のコンテンツをクリックした受信者の数。

「 **Domain repartition** 」（ドメインの再パーティション）テーブルには、受信者のドメインに従って配信のステータスが表示されます。
