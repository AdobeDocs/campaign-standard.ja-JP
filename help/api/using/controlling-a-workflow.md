---
solution: Campaign Standard
product: campaign
title: ワークフローの制御
description: APIを使用してワークフローを制御する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: f946a7565c30a3e53b2bd6876e880100fa8a0be2
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 14%

---

# ワークフローの制御 {#controlling-a-workflow}

ワークフローIDと必要な実行コマンドを含むPOSTリクエストを使用して、REST APIから直接ワークフローを制御できます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Adobe CampaignでワークフローIDを変更すると、APIリクエストは機能しなくなります。

ワークフローを制御するための4つの実行コマンドを使用できます。

* 開始
* 一時停止
* 再開
* 停止

実行コマンドについて詳しくは、[Campaignのドキュメント](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)を参照してください。

<br/>

***リクエストのサンプル***

* ワークフローの開始.

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
