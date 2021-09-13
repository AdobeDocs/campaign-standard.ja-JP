---
title: サービス購読者に対する増分処理クエリ
description: 次の例は、サービスの購読者をフィルターする増分処理クエリアクティビティの設定方法を示しています。
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
source-wordcount: '211'
ht-degree: 67%

---

# サービス購読者に対する増分処理クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、**Running Newsletter** サービスを購読しているプロファイルを Adobe Campaign データベース内でフィルタリングして、プロモーションコードを記載したようこそメールをそれらのプロファイルに送信する「**[!UICONTROL Incremental query]**」アクティビティの設定を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* 毎週月曜日午前6時にワークフローを実行する[スケジューラー](../../automating/using/scheduler.md)アクティビティ。

   ![](assets/incremental_query_example2.png)

* [増分処理クエリ](../../automating/using/incremental-query.md)アクティビティ。最初の実行時には、現在のすべての購読者をターゲットにし、その後の実行時には、その週の新しい購読者のみをターゲットにします。

   ![](assets/incremental_query_example3.png)

* [Eメール配信](../../automating/using/email-delivery.md)アクティビティ。 ワークフローは週に 1 回実行されますが、送信された E メールとその結果を 1 ヶ月ごとに集計できます。例えば、1 週間単位ではなく、1 ヶ月全体でのレポートを生成できます。

   それには、ここで&#x200B;**[!UICONTROL Recurring email]**&#x200B;を作成し、「**[!UICONTROL By month]**」で指定した月数を単位として E メールとその結果を再グループ化します。

   E メールのコンテンツ定義し、ウェルカムプロモーションコードを挿入します。詳しくは、[Eメールコンテンツの定義](../../designing/using/personalization.md)の節を参照してください。

そのあと、ワークフローの実行を開始します。毎週、新規購読者には、プロモーションコードが記載されたようこそメールが送信されます。
