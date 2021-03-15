---
solution: Campaign Standard
product: campaign
title: 分岐
description: 「分岐」アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: ワークフロー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 99%

---


# 分岐{#fork}

## 説明 {#description}

![](assets/fork.png)

「**[!UICONTROL Fork]**」アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。

## 使用状況 {#context-of-use}

「**[!UICONTROL Fork]**」アクティビティを使用すると、同じワークフロー内で複数の異なるアクティビティを個別に実行できます。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Fork]**」アクティビティをドラッグ＆ドロップします。
1. そのアクティビティを、事前に実行する他のアクティビティ（クエリなど）に接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アウトバウンドトランジションを作成、削除または複製して、アウトバウンドトランジションの数を指定します。また、名前とラベルを付けることもできます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例は、Adobe Campaign データベース内のプロファイル（この場合はパリに住む女性）をターゲットにした 2 つの「クエリ」アクティビティの積集合を示しています。したがって、「分岐」アクティビティを使用すると、複数のアクティビティを同時に使用できます。1 つは、オーディエンスを保存して、計算された母集団を記憶するためのもの、もう 1 つは、母集団をセグメント化して、セグメントごとにターゲットコンテンツを含んだ 2 つの異なる E メールを送信するためのものです。最初の E メールは 18～40 歳のパリの女性に送信され、もう 1 つは 41 歳以上のパリの女性をターゲットにします。

![](assets/wkf_fork_example.png)

