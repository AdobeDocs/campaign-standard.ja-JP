---
title: 2つの洗練されたオーディエンスの和集合
description: この使用例は、2つの読み取りオーディエンスアクティビティの和集合を示しています。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# 2つの洗練されたオーディエンスの和集合 {#example--union-on-two-refined-audiences}

この例で定義したワークフローは、2つの **[!UICONTROL Read audience]** アクティビティの和集合を示しています。 このワークフローの目的は、18 ～ 30歳のゴールドメンバーまたはシルバーメンバーに電子メールを送信することです。 金と銀の会員を追跡するために、システム内に特定のオーディエンスが既に作成されています。

ワークフローは、次のように設計されています。

![](assets/readaudience_activity_example1.png)

* ゴールドメンバーのオーディエンスを取得し、18 ～ 30年のオーディエンスのみを選択して絞り込む、最初の [読み取りアクティビティ](../../automating/using/read-audience.md) 。
* 銀会員オーディエンスを取得し、18 ～ 30才のプロファイルのみを選択して絞り込む2つ目の **[!UICONTROL Read audience]** アクティビティです。
* 両方の [アクティビティの母集団を1つの最終的な母集団に結合する](../../automating/using/union.md) 和集合 **[!UICONTROL Read audiences]** アクティビティ。
* 電子メ [ール配信](../../automating/using/email-delivery.md) アクティビティ。 **[!UICONTROL Union]** アクティビティからの訪問者に電子メールを送信します。
