---
title: 概要
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# 概要 {#calling-a-workflow-with-external-parameters}

Campaign Standardを使用すると、パラメーター（ターゲットにするオーディエンス名、インポートするファイル名、メッセージコンテンツの一部など）を指定してワークフローを呼び出すことができます。 これにより、Campaign の自動化を外部システムと簡単に統合できます。

次の例では、CMS から直接 E メールを送信します。 その場合は、オーディエンスと E メールのコンテンツを選択して CMS に送信するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを指定してキャンペーンワークフローが呼び出され、ワークフロー内で使用して、配信で使用するオーディエンスと URL コンテンツを定義できます。

パラメーターを指定してワークフローを呼び出すプロセスは次のとおりです。

1. でパラメーターを宣言 **[!UICONTROL External signal]** アクティビティ。 詳しくは、 [外部シグナルアクティビティでのパラメーターの宣言](../../automating/using/declaring-parameters-external-signal.md).
1. の設定 **[!UICONTROL End]** アクティビティまたは API 呼び出しを使用して、ワークフローのパラメーターとトリガーを定義します。 **[!UICONTROL External signal]** アクティビティ。 詳しくは、 [このページ](../../automating/using/defining-parameters-calling-workflow.md)
1. ワークフローがトリガーされると、パラメーターがワークフローのイベント変数に取り込まれ、ワークフロー内で使用できます。 [このページ](../../automating/using/customizing-workflow-external-parameters.md)を参照してください。

![](assets/extsignal_process.png)
