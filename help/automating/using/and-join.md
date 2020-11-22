---
solution: Campaign Standard
product: campaign
title: AND-join
description: 「AND-join」アクティビティを使用すると、ワークフローの複数の実行分岐を同期できます。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 100%

---


# AND-join{#and-join}

## 説明 {#description}

![](assets/and_join.png)

「**[!UICONTROL AND-join]**」アクティビティを使用すると、ワークフローの複数の実行分岐を同期できます。

## 使用状況{#context-of-use}

「**[!UICONTROL AND-join]**」アクティビティは、すべてのインバウンドトランジションが有効化された（つまり、前のアクティビティがすべて終了した）ときにのみ、アウトバウンドトランジションをトリガーします。

## 設定 {#configuration}

1. クエリなど、複数のアクティビティをワークフローにドロップして、2 つ以上の異なる実行分岐を形成します。
1. ワークフローに「**[!UICONTROL AND-join]**」アクティビティをドラッグ＆ドロップします。
1. 同期する 2 つの異なる分岐の後に結合します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アウトバウンドトランジションに保持するメインセットを選択します。セットを選択しない場合は、ランダムな母集団がアクティビティから送信されます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例は、ワークフローの 2 つの分岐が「**[!UICONTROL AND-join]**」アクティビティと結合される前の状態を示しています。ファイルの抽出は、「**[!UICONTROL AND-join]**」アクティビティの 3 つのインバウンドトランジションが有効な場合にのみ実行できます。

![](assets/wkf_and-join_example.png)

