---
title: ワークフローの制御
description: APIを使用してワークフローを制御する方法を説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# ワークフローの制御 {#controlling-a-workflow}

ワークフローIDと必要な実行コマンドを含むPOSTリクエストを使用して、REST APIから直接ワークフローを制御できます。

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>ワークフローIDがAdobe Campaignで変更された場合、APIリクエストは機能しなくなります。

ワークフローを制御するために、次の4つの実行コマンドを使用できます。

* 開始
* 一時停止
* 再開
* 停止

実行コマンドの詳細については、Campaignのドキュメントを参照し [てください](https://helpx.adobe.com/campaign/standard/automating/using/executing-a-workflow.html)。

<br/>

***リクエストの例***

* ワークフローを開始します。

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
