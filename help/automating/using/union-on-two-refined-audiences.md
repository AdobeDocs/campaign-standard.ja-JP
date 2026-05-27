---
title: 2 つの絞り込まれたオーディエンスの和集合
description: このユースケースは、2つの「オーディエンスを読み取り」アクティビティの結合を示しています。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
TQID: https://experienceleague.adobe.com/NZA7DqSxrgPvNPfo4dgWvyJaOp-2Ma07MZJuHff3sAA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 43%

---

# 2 つの絞り込まれたオーディエンスの和集合 {#example--union-on-two-refined-audiences}

この例で定義したワークフローは、2 つの「**[!UICONTROL Read audience]**」アクティビティの和集合を示しています。 このワークフローの目標は、18歳から30歳のゴールドまたはシルバーのメンバーにメールを送信することです。 ゴールドメンバーとシルバーメンバーを追跡するために、システム内に個別のオーディエンスが既に作成されています。

ワークフローは、次のように設計されています。

![](assets/readaudience_activity_example1.png)

* ゴールドメンバーのオーディエンスを取得し、18歳から30歳までのプロファイルのみを選択して絞り込む最初の[ オーディエンスの読み取り](../../automating/using/read-audience.md) アクティビティ。
* 2 つ目の「**[!UICONTROL Read audience]**」アクティビティ。シルバーメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* 両方の&#x200B;**[!UICONTROL Read audiences]** アクティビティの母集団を1つの最終母集団に統合する[Union](../../automating/using/union.md) アクティビティ。
* **[!UICONTROL Union]** アクティビティから送信された母集団に電子メールを送信する[電子メール配信](../../automating/using/email-delivery.md) アクティビティ。
