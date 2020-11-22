---
solution: Campaign Standard
product: campaign
title: 2 つの絞り込まれたオーディエンスの和集合
description: この使用例は、2つの読み取りオーディエンスアクティビティの和集合を示しています。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# 2 つの絞り込まれたオーディエンスの和集合 {#example--union-on-two-refined-audiences}

この例で定義したワークフローは、2 つの「**[!UICONTROL Read audience]**」アクティビティの和集合を示しています。このワークフローの目的は、18～30 歳のゴールドメンバーまたはシルバーメンバーに E メールを送信することです。ゴールドメンバーとシルバーメンバーを追跡するために、システム内に個別のオーディエンスが既に作成されています。

ワークフローは、次のように設計されています。

![](assets/readaudience_activity_example1.png)

* A first [Read audience](../../automating/using/read-audience.md) activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* 2 つ目の「**[!UICONTROL Read audience]**」アクティビティ。シルバーメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* A [Union](../../automating/using/union.md) activity that unites populations from both **[!UICONTROL Read audiences]** activities into one final population.
* An [Email delivery](../../automating/using/email-delivery.md) activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.
