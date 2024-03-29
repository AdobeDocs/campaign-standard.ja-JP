---
title: サービス購読者に対する増分処理クエリ
description: 次の例は、サービスの購読者をフィルタリングする「増分処理クエリ」アクティビティの設定方法を示しています。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 61%

---

# サービス購読者に対する増分処理クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、**Running Newsletter** サービスを購読しているプロファイルを Adobe Campaign データベース内でフィルタリングして、プロモーションコードを記載したウェルカムメールをそれらのプロファイルに送信する「**[!UICONTROL Incremental query]**」アクティビティの設定を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* A [スケジューラ](../../automating/using/scheduler.md) 「 」アクティビティ：毎週月曜日午前 6 時にワークフローを実行します。

  ![](assets/incremental_query_example2.png)

* An [増分処理クエリ](../../automating/using/incremental-query.md) 「 」アクティビティ：初回実行時には、その時点のすべての購読者をターゲットにし、その後の実行時には、同じ週の新規購読者のみをターゲットにします。

  ![](assets/incremental_query_example3.png)

* An [E メール配信](../../automating/using/email-delivery.md) アクティビティ。 ワークフローは週に 1 回実行されますが、送信されたメールとその結果を 1 ヶ月ごとに集計できます。例えば、1 週間単位ではなく、1 ヶ月全体でのレポートを生成できます。

  それには、ここで&#x200B;**[!UICONTROL Recurring email]**&#x200B;を作成し、「**[!UICONTROL By month]**」で指定した月数を単位としてメールとその結果を再グループ化します。

  E メールのコンテンツを定義し、ウェルカムプロモーションコードを挿入します。 詳しくは、 [E メールコンテンツの定義](../../designing/using/personalization.md) セクション。

そのあと、ワークフローの実行を開始します。毎週、新規購読者には、プロモーションコードが記載されたウェルカムメールが送信されます。
