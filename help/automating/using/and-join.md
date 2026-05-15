---
title: AND 結合
description: 「AND-join」アクティビティを使用すると、ワークフローの複数の実行分岐を同期できます。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b03c6df3-0104-4900-9468-46824d62e0a6
TQID: https://experienceleague.adobe.com/ydaYzPE9SwLuC-d4nVSaFgLLp-R0Kuceq7hUI89aN1Y
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 98%

---

# AND 結合{#and-join}

## 説明 {#description}

![](assets/and_join.png)

「**[!UICONTROL AND-join]**」アクティビティを使用すると、ワークフローの複数の実行分岐を同期できます。

## Context of use {#context-of-use}

「**[!UICONTROL AND-join]**」アクティビティは、すべてのインバウンドトランジションが有効化された（つまり、前のアクティビティがすべて終了した）ときにのみ、アウトバウンドトランジションをトリガーします。

## 設定 {#configuration}

1. クエリなど、複数のアクティビティをワークフローにドロップして、2 つ以上の異なる実行分岐を形成します。
1. ワークフローに「**[!UICONTROL AND-join]**」アクティビティをドラッグ＆ドロップします。
1. 同期する 2 つの異なる分岐の後に結合します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アウトバウンドトランジションに保持するメインセットを選択します。 セットを選択しない場合は、ランダムな母集団がアクティビティから送信されます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例は、ワークフローの 2 つの分岐が「**[!UICONTROL AND-join]**」アクティビティと結合される前の状態を示しています。 ファイルの抽出は、「**[!UICONTROL AND-join]**」アクティビティの 3 つのインバウンドトランジションが有効な場合にのみ実行できます。

![](assets/wkf_and-join_example.png)
