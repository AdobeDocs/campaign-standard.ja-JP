---
title: サービス購読者に対する増分処理クエリ
description: 次の例では、サービスのサブスクライバーをフィルタリングするように増分クエリアクティビティを設定する方法を示します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
TQID: https://experienceleague.adobe.com/MHB1ETCecN9gQq51bSii-keTyFaYof0JtAyckFSCKQE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 81%

---

# サービス購読者に対する増分処理クエリ {#example--incremental-query-on-subscribers-to-a-service}

次の例は、**Running Newsletter** サービスを購読しているプロファイルを Adobe Campaign データベース内でフィルタリングして、プロモーションコードを記載したウェルカムメールをそれらのプロファイルに送信する「**[!UICONTROL Incremental query]**」アクティビティの設定を示しています。

ワークフローは、次の要素で構成されています。

![](assets/incremental_query_example1.png)

* [スケジューラー](../../automating/using/scheduler.md)アクティビティ：毎週月曜日午前 6 時にワークフローを実行します。

  ![](assets/incremental_query_example2.png)

* [増分クエリ](../../automating/using/incremental-query.md)アクティビティ：初回実行時には、その時点の全購読者をターゲットにし、それ以降の実行ではその週の新規購読者だけをターゲットにします。

  ![](assets/incremental_query_example3.png)

* [メール配信](../../automating/using/email-delivery.md)アクティビティ ワークフローは週に 1 回実行されますが、送信されたメールとその結果を 1 ヶ月ごとに集計できます。例えば、1 週間単位ではなく、1 ヶ月全体でのレポートを生成できます。

  それには、ここで&#x200B;**[!UICONTROL Recurring email]**&#x200B;を作成し、「**[!UICONTROL By month]**」で指定した月数を単位としてメールとその結果を再グループ化します。

  メールの内容を定義し、ウェルカムプロモーションコードを挿入します。 詳しくは、[電子メールコンテンツの定義](../../designing/using/personalization.md)の節を参照してください。

そのあと、ワークフローの実行を開始します。 毎週、新規購読者には、プロモーションコードが記載されたウェルカムメールが送信されます。
