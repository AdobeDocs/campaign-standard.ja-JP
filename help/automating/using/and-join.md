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
TQID: 'https://experienceleague.adobe.com/ydaYzPE9SwLuC-d4nVSaFgLLp-R0Kuceq7hUI89aN1Y'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '181'
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
