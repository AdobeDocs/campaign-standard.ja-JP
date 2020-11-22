---
solution: Campaign Standard
product: campaign
title: 誕生日配信
description: この例は、誕生日のワークフローです。毎日、その日が誕生日のプロファイルに E メールが送られます。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# 誕生日配信 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

この例は、誕生日のワークフローです。毎日、その日が誕生日のプロファイルに E メールが送られます。

ワークフローを構築するには、次の手順に従います。

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* [クエリ](../../automating/using/query.md) アクティビティを使用すると、ワークフローが実行されるたびに、電子メールを提供したプロファイルと、その誕生日が現在の日付に含まれているユーザーを計算できます。 誕生日の計算は、クエリ編集ツールのパレットにある定義済みフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* 電子メ [ール配信](../../automating/using/email-delivery.md) は定期的に発生します。 送信は月単位で集計されます。そのため、1 ヶ月間に送信されたすべての E メールが 1 つの表示に集計されます。1 年間では 365 回の配信が実行されますが、Adobe Campaign インターフェイスでは 12 個の表示（**繰り返し実行**&#x200B;とも呼ばれます）に再グループ化されます。履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_delivery_example_4.png)
