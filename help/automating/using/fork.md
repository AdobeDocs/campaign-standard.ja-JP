---
title: 分岐
description: 「分岐」アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
TQID: https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 213
ht-degree: 98%

---

# 分岐{#fork}

## 説明 {#description}

![](assets/fork.png)

「**[!UICONTROL Fork]**」アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。

## Context of use {#context-of-use}

「**[!UICONTROL Fork]**」アクティビティを使用すると、同じワークフロー内で複数の異なるアクティビティを個別に実行できます。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Fork]**」アクティビティをドラッグ＆ドロップします。
1. そのアクティビティを、事前に実行する他のアクティビティ（クエリなど）に接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アウトバウンドトランジションを作成、削除または複製して、アウトバウンドトランジションの数を指定します。 また、名前とラベルを付けることもできます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例は、Adobe Campaign データベース内のプロファイル（この場合はパリに住む女性）をターゲットにした 2 つの「クエリ」アクティビティの積集合を示しています。 したがって、「分岐」アクティビティを使用すると、複数のアクティビティを同時に使用できます。1 つは、オーディエンスを保存して、計算された母集団を記憶するためのもの、もう 1 つは、母集団をセグメント化して、セグメントごとにターゲットコンテンツを含んだ 2 つの異なるメールを送信するためのものです。 最初のメールは 18～40 歳のパリの女性に送信され、もう 1 つは 41 歳以上のパリの女性をターゲットにします。

![](assets/wkf_fork_example.png)
