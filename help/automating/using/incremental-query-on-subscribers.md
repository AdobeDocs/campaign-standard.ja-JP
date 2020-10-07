---
title: サービス購読者に対する増分処理クエリ
description: 次の例は、増分処理クエリアクティビティを設定して、サービスのサブスクライバをフィルタリングする方法を示しています。
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# サービス購読者に対する増分処理クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、**Running Newsletter** サービスを購読しているプロファイルを Adobe Campaign データベース内でフィルタリングして、プロモーションコードを記載したようこそメールをそれらのプロファイルに送信する「**[!UICONTROL Incremental query]**」アクティビティの設定を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* 電子 [メール配信](../../automating/using/email-delivery.md) アクティビティ。 ワークフローは週に 1 回実行されますが、送信された E メールとその結果を 1 ヶ月ごとに集計できます。例えば、1 週間単位ではなく、1 ヶ月全体でのレポートを生成できます。

   それには、ここで&#x200B;**[!UICONTROL Recurring email]**&#x200B;を作成し、「**[!UICONTROL By month]**」で指定した月数を単位として E メールとその結果を再グループ化します。

   E メールのコンテンツ定義し、ウェルカムプロモーションコードを挿入します。この点について詳しくは、「電子メールコンテンツの [定義](../../designing/using/personalization.md) 」の節を参照してください。

そのあと、ワークフローの実行を開始します。毎週、新規購読者には、プロモーションコードが記載されたようこそメールが送信されます。
