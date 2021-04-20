---
solution: Campaign Standard
product: campaign
title: サービス購読者に対する増分処理クエリ
description: 次の例は、増分処理クエリアクティビティを設定して、サービスのサブスクライバをフィルタリングする方法を示しています。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 66%

---


# サービス購読者に対する増分処理クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、**Running Newsletter** サービスを購読しているプロファイルを Adobe Campaign データベース内でフィルタリングして、プロモーションコードを記載したようこそメールをそれらのプロファイルに送信する「**[!UICONTROL Incremental query]**」アクティビティの設定を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* 毎週月曜日の午前6時にスケジューラーを実行する[アクティビティ](../../automating/using/scheduler.md)ワークフロー。

   ![](assets/incremental_query_example2.png)

* [増分処理クエリ](../../automating/using/incremental-query.md)アクティビティ。最初の実行時に現在のすべてのサブスクライバをターゲットし、次の実行時にその週の新しいサブスクライバのみを実行します。

   ![](assets/incremental_query_example3.png)

* [電子メール配信](../../automating/using/email-delivery.md)アクティビティ。 ワークフローは週に 1 回実行されますが、送信された E メールとその結果を 1 ヶ月ごとに集計できます。例えば、1 週間単位ではなく、1 ヶ月全体でのレポートを生成できます。

   それには、ここで&#x200B;**[!UICONTROL Recurring email]**&#x200B;を作成し、「**[!UICONTROL By month]**」で指定した月数を単位として E メールとその結果を再グループ化します。

   E メールのコンテンツ定義し、ウェルカムプロモーションコードを挿入します。詳しくは、「[電子メールコンテンツの定義](../../designing/using/personalization.md)」の節を参照してください。

そのあと、ワークフローの実行を開始します。毎週、新規購読者には、プロモーションコードが記載されたようこそメールが送信されます。
