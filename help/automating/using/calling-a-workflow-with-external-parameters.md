---
solution: Campaign Standard
product: campaign
title: 概要
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---


# 概要 {#calling-a-workflow-with-external-parameters}

Campaign Standardを使用すると、ターゲットに対するオーディエンス名、インポートするファイル名、メッセージコンテンツの一部などのパラメータを使用してワークフローを呼び出すことができます。 これにより、キャンペーンの自動化を外部システムに容易に統合できます。

次の例では、CMSから直接電子メールを送信する例を見てみましょう。 その場合は、オーディエンスを選択し、CMSにコンテンツを電子メールで送信するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを含むキャンペーンワークフローが呼び出され、配信で使用するオーディエンスとURLコンテンツを定義するワークフローで使用できます。

パラメーターを使用してワークフローを呼び出すプロセスは、次のとおりです。

1. **[!UICONTROL External signal]**&#x200B;アクティビティーでパラメーターを宣言します。 [外部シグナルアクティビティでのパラメータの宣言](../../automating/using/declaring-parameters-external-signal.md)を参照してください。
1. **[!UICONTROL End]**&#x200B;アクティビティーまたはAPI呼び出しを設定して、ワークフロー&#x200B;**[!UICONTROL External signal]**&#x200B;アクティビティーのパラメーターとトリガーを定義します。 [このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照
1. ワークフローがトリガーされると、パラメーターはワークフローのイベント変数に取り込まれ、ワークフロー内で使用できます。 [このページ](../../automating/using/customizing-workflow-external-parameters.md)を参照してください。

![](assets/extsignal_process.png)
