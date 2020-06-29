---
title: 誕生日配信
description: 次の例は、誕生日のワークフローです。 毎日、その日の誕生日を持つプロファイルに電子メールが送られます。
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# 誕生日配信 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

次の例は、誕生日のワークフローです。 毎日、その日の誕生日を持つプロファイルに電子メールが送られます。

ワークフローを構築するには、次の手順に従います。

* この [スケジューラーでは](../../automating/using/scheduler.md) 、毎日午前8時にワークフローを開始できます。

   ![](assets/wkf_delivery_example_2.png)

* [クエリ](../../automating/using/query.md) アクティビティを使用すると、ワークフローが実行されるたびに、電子メールを提供したプロファイルと、その誕生日が現在の日付に含まれているユーザーを計算できます。 誕生日の計算は、クエリ編集ツールのパレットにある定義済みのフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* 電子メ [ール配信](../../automating/using/email-delivery.md) は定期的に発生します。 送信は月別に集計されます。 1か月の間に送信されるすべての電子メールは、1つの表示に集計されます。 したがって、1年後には365個の配信が実行されますが、Adobe Campaignインターフェイスでは12個の表示( **繰り返し実行**)に再グループ化されます。 履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_delivery_example_4.png)
