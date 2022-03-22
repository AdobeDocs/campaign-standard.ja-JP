---
title: 外部シグナルアクティビティでのパラメーターの宣言
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# 外部シグナルアクティビティでのパラメーターの宣言 {#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを指定してワークフローを呼び出す最初の手順は、パラメーターを指定してワークフローを **[!UICONTROL External signal]** アクティビティ。

1. を開きます。 **[!UICONTROL External signal]** 「 」アクティビティで、 **[!UICONTROL Parameters]** タブをクリックします。
1. 次をクリック： **[!UICONTROL Create element]** ボタンをクリックして、各パラメーターの名前とタイプを指定します。

   >[!CAUTION]
   >
   >パラメーターの名前と数が、ワークフローの呼び出し時に定義されたものと同じであることを確認します ( [このページ](../../automating/using/defining-parameters-calling-workflow.md)) をクリックします。 また、パラメーターの型は、期待される値と一致する必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターが宣言されたら、ワークフローの設定を完了し、実行します。
