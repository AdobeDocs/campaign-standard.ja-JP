---
title: サービスの購読者の増分処理クエリ
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# サービスの購読者の増分処理クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、 **[!UICONTROL Incremental query]** 実行中のニュースレターサービスをサブスクライブしているAdobe Campaignデータベースのプロファイルをフィルターし、プロモーションコードを含むお知らせメールを送信する **** アクティビティの設定を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* 毎週月曜日の午前6時にワークフローを実行する [スケジューラー](../../automating/using/scheduler.md) アクティビティ。

   ![](assets/incremental_query_example2.png)

* 最初の実行時に現在のすべてのサブスクライバをターゲットし、次の実行時にその週の新しいサブスクライバのみを実行する [増分処理クエリ](../../automating/using/incremental-query.md) アクティビティ。

   ![](assets/incremental_query_example3.png)

* 電子 [メール配信](../../automating/using/email-delivery.md) アクティビティ。 ワークフローは週に1回実行されますが、1か月に1回送信される電子メールと結果を集計できます。例えば、1週間だけでなく、1か月全体のレポートを生成する場合などです。

   これを行うには、電子メールと結果を再グループ化する **[!UICONTROL Recurring email]** ここを選択し **[!UICONTROL By month]**&#x200B;ます。

   電子メールの内容を定義し、ウェルカムプロモーションコードを挿入します。 この点について詳しくは、「電子メールコンテンツの [定義](../../designing/using/personalization.md) 」の節を参照してください。

次に、ワークフローの実行を開始します。 新しい購読者は毎週、プロモーションコードが記載されたご案内の電子メールを受信します。
