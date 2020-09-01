---
title: 概要
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
source-wordcount: '181'
ht-degree: 1%

---


# 概要 {#calling-a-workflow-with-external-parameters}

Campaign Standardを使用すると、ターゲットに対するオーディエンス名、インポートするファイル名、メッセージコンテンツの一部などのパラメータを使用してワークフローを呼び出すことができます。 これにより、キャンペーンの自動化を外部システムに容易に統合できます。

次の例では、CMSから直接電子メールを送信する例を見てみましょう。 その場合は、オーディエンスを選択し、CMSにコンテンツを電子メールで送信するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを含むキャンペーンワークフローが呼び出され、配信で使用するオーディエンスとURLコンテンツを定義するワークフローで使用できます。

パラメーターを使用してワークフローを呼び出すプロセスは、次のとおりです。

1. アクティビティ内のパラメーターを宣言し **[!UICONTROL External signal]** ます。 「外部シグナルアクティビティでのパラメータの [宣言](../../automating/using/declaring-parameters-external-signal.md)」を参照してください。
1. アクティビティーまたはAPI呼び出しを設定して、パラメーターを定義し、ワークフロー **[!UICONTROL End]****[!UICONTROL External signal]** アクティビティをトリガーします。

ワークフローがトリガーされると、パラメーターはワークフローのイベント変数に取り込まれ、ワークフロー内で使用できます。 [](../../automating/using/customizing-workflow-external-parameters.md) を参照してください。

![](assets/extsignal_process.png)
