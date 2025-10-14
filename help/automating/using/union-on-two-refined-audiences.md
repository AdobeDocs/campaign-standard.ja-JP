---
title: 2 つの絞り込まれたオーディエンスの和集合
description: このユースケースは、2 つのオーディエンスを読み取りアクティビティの和集合を示しています。
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
source-wordcount: '156'
ht-degree: 43%

---

# 2 つの絞り込まれたオーディエンスの和集合 {#example--union-on-two-refined-audiences}

この例で定義したワークフローは、2 つの「**[!UICONTROL Read audience]**」アクティビティの和集合を示しています。このワークフローの目標は、18～30 歳のゴールドまたはシルバーメンバーにメールを送信することです。 ゴールドメンバーとシルバーメンバーを追跡するために、システム内に個別のオーディエンスが既に作成されています。

ワークフローは、次のように設計されています。

![](assets/readaudience_activity_example1.png)

* 最初の [&#x200B; オーディエンスを読み取り &#x200B;](../../automating/using/read-audience.md) アクティビティでは、ゴールドメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* 2 つ目の「**[!UICONTROL Read audience]**」アクティビティ。シルバーメンバーオーディエンスを取得し、18～30 歳のプロファイルのみを選択して絞り込みます。
* 両方の **[!UICONTROL Read audiences]** アクティビティの母集団を 1 つの最終的な母集団に統合する [&#x200B; 結合 &#x200B;](../../automating/using/union.md) アクティビティ。
* **[!UICONTROL Union]** アクティビティから取得した母集団にメールを送信する [&#x200B; メール配信 &#x200B;](../../automating/using/email-delivery.md) アクティビティ。
