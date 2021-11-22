---
title: 2 つの絞り込まれたオーディエンスの和集合
description: この使用例は、2 つの「オーディエンスの閲覧」アクティビティの和集合を示しています。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---

# 2 つの絞り込まれたオーディエンスの和集合 {#example--union-on-two-refined-audiences}

この例で定義したワークフローは、2 つの「**[!UICONTROL Read audience]**」アクティビティの和集合を示しています。このワークフローの目的は、18～30 歳のゴールドメンバーまたはシルバーメンバーに E メールを送信することです。ゴールドメンバーとシルバーメンバーを追跡するために、システム内に個別のオーディエンスが既に作成されています。

ワークフローは、次のように設計されています。

![](assets/readaudience_activity_example1.png)

* 最初の [オーディエンスの閲覧](../../automating/using/read-audience.md) 「 」アクティビティ。ゴールドメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* 2 つ目の「**[!UICONTROL Read audience]**」アクティビティ。シルバーメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* A [和集合](../../automating/using/union.md) 両者の母集団を結び付けるアクティビティ **[!UICONTROL Read audiences]** アクティビティを最終的な 1 つの母集団に変換します。
* An [E メール配信](../../automating/using/email-delivery.md) からの母集団に e メールを送信する「 」アクティビティ **[!UICONTROL Union]** アクティビティ。
