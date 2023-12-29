---
title: プログラムとキャンペーン
description: Adobe Campaign では、プログラムとキャンペーンを使用すると、リンクされている様々なマーケティングアクティビティをグループ化し調整できます。プログラムとキャンペーンに関するレポートを使用すると、その影響を分析できます。
audience: start
content-type: reference
topic-tags: marketing-plans
context-tags: campaign,overview;campaignExplorer,main
feature: Campaigns
role: User
level: Beginner
exl-id: 3f4f9307-c65f-47bb-bc92-ce8b5d06557f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 97%

---

# プログラムとキャンペーン{#programs-and-campaigns}

## プラン、プログラム、キャンペーンについて {#about-plans--programs-and-campaigns}

Adobe Campaign を使用すると、メール、SMS メッセージ、プッシュ通知、ワークフロー、ランディングページなど、様々なタイプのアクティビティを作成および管理できるマーケティングキャンペーンを計画できます。これらのキャンペーンとそのコンテンツは、プログラムに集約できます。

プログラムとキャンペーンを使用すると、リンクされている様々なマーケティングアクティビティを再グループ化し表示できます。

* **プログラム**&#x200B;には、キャンペーン、ワークフロー、ランディングページに加えて、他のプログラムを含めることができます。これはタイムラインに表示され、マーケティングアクティビティの整理に役立ちます。また、国別、ブランド別、単位別などに分けることも可能です。
* **キャンペーン**&#x200B;を使用すると、選択したすべてのマーケティングアクティビティを 1 つのエンティティから集約できます。キャンペーンには、メール、SMS、プッシュ通知、ダイレクトメール、ワークフロー、ランディングページなどが含まれます。

マーケティングプランをより整理するには、プログラム／サブプログラム／キャンペーン／ワークフロー／配信の階層を使用することをお勧めします。

プログラムとキャンペーンに関するレポートを使用すると、その影響を分析できます。例えば、キャンペーンレベルで、そのキャンペーンに含まれているすべての配信の集計データに関するレポートを作成できます。

**関連トピック：**

* [タイムライン](../../start/using/timeline.md)
* [動的レポートについて](../../reporting/using/about-dynamic-reports.md)

## プログラムの作成 {#creating-a-program}

プログラムは組織の第 1 レベルです。サブプログラム、キャンペーン、ワークフロー、またはランディングページを含めることができます。

1. Adobe Campaign ホームページから&#x200B;**[!UICONTROL Programs & Campaigns]**&#x200B;カードを選択します。
1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. **[!UICONTROL Creation mode]**&#x200B;画面で、プログラムタイプを選択します。

   ![](assets/programs_and_campaigns_2.png)

   使用できるプログラムタイプは、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Program templates]**&#x200B;セクションで定義されたテンプレートに基づきます。詳しくは、[テンプレートの管理](../../start/using/marketing-activity-templates.md)の節を参照してください。

1. **[!UICONTROL Properties]**&#x200B;画面で、プログラムの名前と ID を入力します。

   ![](assets/programs_and_campaigns_3.png)

1. プログラムの開始日と終了日を選択します。これらの日付は、プログラム自体にのみ適用されます。

   親プログラム内にプログラムを作成することも可能です。これをおこなうには、既存のプログラムから親プログラムを選択します。

1. 「**[!UICONTROL Create]**」をクリックして、プログラムの作成を確定します。

プログラムが作成され、表示されます。サブプログラム、キャンペーン、ワークフロー、またはランディングページを追加するには、「**[!UICONTROL Create]**」ボタンを使用します。

>[!NOTE]
>
>マーケティングアクティビティのリストからプログラムを作成することもできます。

## キャンペーンの作成 {#creating-a-campaign}

プログラムとサブプログラムでは、キャンペーンを追加できます。キャンペーンには、メール、SMS、プッシュ通知、ワークフロー、ランディングページなどのマーケティングアクティビティを含めることができます。

1. Adobe Campaign ホームページから、**[!UICONTROL Programs & Campaigns]**&#x200B;カードを選択し、プログラムまたはサブプログラムにアクセスします。
1. 「**[!UICONTROL Create]**」ボタンをクリックし、「**[!UICONTROL Campaign]**」を選択します。
1. **[!UICONTROL Creation mode]**&#x200B;画面で、キャンペーンのタイプを選択します。

   ![](assets/programs_and_campaigns_7.png)

   使用できるキャンペーンのタイプは、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Campaign templates]**&#x200B;で定義したテンプレートに基づいています。詳しくは、[テンプレートの管理](../../start/using/marketing-activity-templates.md)の節を参照してください。

1. **[!UICONTROL Properties]**&#x200B;画面で、キャンペーンの名前と ID を入力します。
1. キャンペーンの開始日と終了日を選択します。これらの日付は、キャンペーン自体にのみ適用されます。

   ![](assets/programs_and_campaigns_8.png)

1. 「**[!UICONTROL Create]**」をクリックして、キャンペーンの作成を確定します。

キャンペーンが作成され、表示されます。「**[!UICONTROL Create]**」ボタンを使用すると、キャンペーンにマーケティングアクティビティを追加します。

>[!NOTE]
>
>使用許諾契約によっては、これらのアクティビティの一部にのみアクセスできます。

また、マーケティングアクティビティリストからキャンペーンを作成することもできます。キャンペーンのプロパティウィンドウを使用すると、マーケティングアクティビティを親プログラムまたはサブプログラムにリンクするように選択できます。

## プログラムとキャンペーンのアイコンとステータス {#programs-and-campaigns-icons-and-statuses}

リスト内のプログラムとキャンペーンのそれぞれには、実行ステータスを示す視覚的な記号と色の付いたアイコンが表示されます。このステータスは、プログラムまたはキャンペーンの有効期間に応じて異なります。

* グレー：プログラム／キャンペーンはまだ開始されていません（**[!UICONTROL Editing]** ステータス）。
* 青：プログラム／キャンペーンが進行中です（**[!UICONTROL In progress]** ステータス）。
* 緑：プログラム／キャンペーンが完了しました（**[!UICONTROL Finished]** ステータス）。デフォルトでは、現在の日付が期限の開始日として自動的に表示され、終了日は開始日（**D+186 日**）に従って計算されます。これらの日付は、プログラムまたはキャンペーンのプロパティで変更できます。

![](assets/programs_and_campaigns.png)
