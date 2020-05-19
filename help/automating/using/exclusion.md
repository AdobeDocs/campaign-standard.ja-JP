---
title: 除外
description: 除外アクティビティを使用すると、特定の条件に従って1つの訪問者から要素を除外できます。
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# 除外{#exclusion}

## 説明 {#description}

![](assets/exclusion.png)

この **[!UICONTROL Exclusion]** アクティビティを使用すると、特定の条件に従って1つの訪問者から要素を除外できます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Exclusion]** アクティビティは、基本的に、受信トランジション母集団に対して追加のフィルタリングを行うのに使用されます。

主セットは、受信トランジションで定義されます。 他の受信トランジションのメンバは、プライマリセットから除外されます。 除外アクティビティのアウトバウンドトランジションには、他のインバウンドトランジションで発生しなかったプライマリセットのメンバのみが含まれます。

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Exclusion]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 受信トランジション **[!UICONTROL Primary set]** からを選択します。 これは、要素を除外するセットです。 他のセットは、主セットから除外される前に要素と一致します。

   >[!NOTE]
   >
   >受信トランジションには、同じタイプの母集団を含める必要があります。 例えば、プライマリセットにテストプロファイルが含まれる場合、他のトランジションにもテストプロファイルが含まれている必要があります。

1. 必要に応じて、アクティビティの [トランジションを管理し](../../automating/using/activity-properties.md) 、アウトバウンド母集団のアドバンスオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、18 ～ 27才のプロファイルデータベースから、無効な電子メールアドレスを持つAdobe Campaignをフィルターするように設定された2つのクエリアクティビティを示しています。 その後、無効な電子メールアドレスを持つプロファイルは、最初のセットから除外されます。 これにより、例えば電子メールを送信できます。

![](assets/wkf_exclusion_example.png)

