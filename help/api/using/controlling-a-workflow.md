---
solution: Campaign Standard
product: campaign
title: ワークフローの制御
description: APIを使用してワークフローを制御する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%

---


# ワークフローの制御 {#controlling-a-workflow}

ワークフローIDと必要な実行コマンドを含むPOST要求を介して、REST APIから直接ワークフローを制御できます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>ワークフローIDがAdobe Campaignで変更された場合、APIリクエストは動作しなくなります。

ワークフローの制御には、次の4つの実行コマンドを使用できます。

* 開始
* 一時停止
* 再開
* 停止

実行コマンドの詳細については、 [キャンペーンのマニュアルを参照してください](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)。

<br/>

***リクエストのサンプル***

* ワークフローの開始

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* ワークフローを停止します。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
