---
title: 誕生日配信
description: この例は、誕生日のワークフローです。毎日、その日に誕生日を迎えるプロファイルにメールが送信されます。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%

---

# 誕生日配信 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

この例は、誕生日のワークフローです。毎日、その日に誕生日を迎えるプロファイルにメールが送信されます。

ワークフローを作成するには、次の手順に従います。

* [&#x200B; スケジューラー &#x200B;](../../automating/using/scheduler.md) を使用すると、ワークフローを毎日午前 8 時に開始できます。

  ![](assets/wkf_delivery_example_2.png)

* [&#x200B; クエリ &#x200B;](../../automating/using/query.md) アクティビティを使用すると、ワークフローを実行するたびに、メールを提供したプロファイルと、当日が誕生日となるプロファイルを計算できます。 誕生日の計算は、クエリ編集ツールのパレットにある定義済みフィルターを使用して実行されます。

  ![](assets/wkf_delivery_example_3.png)

* [&#x200B; メール配信 &#x200B;](../../automating/using/email-delivery.md) は繰り返し実行されます。 送信は月単位で集計されます。そのため、1 ヶ月間に送信されたすべてのメールが 1 つの表示に集計されます。1 年間では 365 回の配信が実行されますが、Adobe Campaign インターフェイスでは 12 個の表示（**繰り返し実行**&#x200B;とも呼ばれます）に再グループ化されます。履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

  ![](assets/wkf_delivery_example_4.png)
