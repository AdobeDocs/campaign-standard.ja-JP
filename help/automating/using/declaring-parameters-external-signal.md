---
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 5%

---


# 外部シグナルアクティビティでのパラメータの宣言 {#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを使用してワークフローを呼び出す最初の手順は、アクティビティでワークフローを宣言することで **[!UICONTROL External signal]** す。

1. アクティビティを開き、 **[!UICONTROL External signal]** タブを選択し **[!UICONTROL Parameters]** ます。
1. ボタンをクリックし **[!UICONTROL Create element]** て、各パラメーターの名前とタイプを指定します。

   >[!CAUTION]
   >
   >名前とパラメーター数が、ワークフローの呼び出し時に定義された名前と数と一致していることを確認します(を参照 [](../../automating/using/defining-parameters-calling-workflow.md))。 また、パラメーターの型は、期待される値と一致する必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターが宣言されたら、ワークフローの設定を終了し、実行します。
