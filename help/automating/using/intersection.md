---
title: 積集合
description: 「積集合」アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2a6a851c-df91-472b-a8a4-0b3876d51c1d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 98%

---

# 積集合{#intersection}

## 説明 {#description}

![](assets/intersection.png)

「**[!UICONTROL Intersection]**」アクティビティでは、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。

## 使用コンテキスト {#context-of-use}

「**[!UICONTROL Intersection]**」アクティビティは、通常、インバウンドトランジションからの母集団に対して追加のフィルタリングをおこなうのに使用されます。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Intersection]**」アクティビティをドラッグ＆ドロップします。
1. そのアクティビティを、事前に実行する他のアクティビティ（クエリなど）に接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 「**[!UICONTROL Reconciliation type]**」として、以下のいずれかを選択します。

   * **[!UICONTROL Keys only]**：デフォルトモード。アクティビティは、異なるインバウンドトランジションの要素が同じキーを持つ場合、1 つの要素のみを保持します。
   * **[!UICONTROL All shared columns]**：データは、インバウンドトランジションと共通の列に基づいて紐付けされます。したがって、比較の基準となるプライマリセットを選択する必要があります。このオプションは、インバウンド母集団のターゲティングディメンションが異なる場合に使用できます。
   * **[!UICONTROL A selection of columns]**：このオプションを選択し、データの紐付けが適用される列のリストを定義します。まずプライマリセット（ソースデータを含んだセット）を選択し、次に結合に使用するフィールドを指定する必要があります。

1. すべてのインバウンドトランジションにある追加データのみを保持する場合は、「**[!UICONTROL Use common additional data only]**」チェックボックスをオンにします。
1. 必要に応じて、アクティビティの[トランジション](../../automating/using/activity-properties.md)を管理して、アウトバウンド母集団の詳細設定オプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

次の例は、2 つの「クエリ」アクティビティ間の積集合を示しています。ここでは、Adobe Campaign データベースを調べて、18～27 歳のプロファイルと、メールアドレスがそれぞれ指定されたプロファイルを取得するために使用されています。

![](assets/wkf_intersection_example.png)
