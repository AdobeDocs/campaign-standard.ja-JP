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

* 最初の[オーディエンス](../../automating/using/read-audience.md)読み取りアクティビティ。Gold membersオーディエンスを取得し、18 ～ 30年のプロファイルのみを選択して絞り込みます。
* 2 つ目の「**[!UICONTROL Read audience]**」アクティビティ。シルバーメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* [和集合](../../automating/using/union.md)アクティビティ。両方の&#x200B;**[!UICONTROL Read audiences]**&#x200B;アクティビティの母集団を1つの最終母集団に結合します。
* [電子メール配信](../../automating/using/email-delivery.md)アクティビティ。**[!UICONTROL Union]**&#x200B;アクティビティからの訪問者に電子メールを送信します。
