---
title: 誕生日配信
description: この例は、誕生日のワークフローです。 毎日、その日が誕生日のプロファイルにメールが送信されます。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 52%

---

# 誕生日配信 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

この例は、誕生日のワークフローです。 毎日、その日が誕生日のプロファイルにメールが送信されます。

ワークフローを構築するには、次の手順に従います。

* [&#x200B; スケジューラー](../../automating/using/scheduler.md)を使用すると、毎日8時にワークフローを開始できます。

  ![](assets/wkf_delivery_example_2.png)

* 「[&#x200B; クエリ &#x200B;](../../automating/using/query.md)」アクティビティを使用すると、ワークフローが実行されるたびに、メールを提供し、その誕生日が現在の日付であるプロファイルを計算できます。 誕生日の計算は、クエリ編集ツールのパレットにある定義済みフィルターを使用して実行されます。

  ![](assets/wkf_delivery_example_3.png)

* [&#x200B; メール配信](../../automating/using/email-delivery.md)は繰り返し行われます。 送信は月単位で集計されます。 そのため、1 ヶ月間に送信されたすべてのメールが 1 つの表示に集計されます。 1 年間では 365 回の配信が実行されますが、Adobe Campaign インターフェイスでは 12 個の表示（**繰り返し実行**&#x200B;とも呼ばれます）に再グループ化されます。 履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

  ![](assets/wkf_delivery_example_4.png)
