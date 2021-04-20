---
solution: Campaign Standard
product: campaign
title: 誕生日配信
description: この例は、誕生日のワークフローです。毎日、その日が誕生日のプロファイルに E メールが送られます。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 68%

---


# 誕生日配信 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

この例は、誕生日のワークフローです。毎日、その日が誕生日のプロファイルに E メールが送られます。

ワークフローを構築するには、次の手順に従います。

* [スケジューラー](../../automating/using/scheduler.md)を使用すると、毎日午前8時にワークフローの開始を行うことができます。

   ![](assets/wkf_delivery_example_2.png)

* [クエリ](../../automating/using/query.md)アクティビティを使用すると、電子メールを提供したプロファイルを計算できます。このユーザーの誕生日は、ワークフローが実行されるたびに現在の日になります。 誕生日の計算は、クエリ編集ツールのパレットにある定義済みフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* [電子メール配信](../../automating/using/email-delivery.md)が定期的に発生しています。 送信は月単位で集計されます。そのため、1 ヶ月間に送信されたすべての E メールが 1 つの表示に集計されます。1 年間では 365 回の配信が実行されますが、Adobe Campaign インターフェイスでは 12 個の表示（**繰り返し実行**&#x200B;とも呼ばれます）に再グループ化されます。履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_delivery_example_4.png)
