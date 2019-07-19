---
title: プログラムとキャンペーン
seo-title: プログラムとキャンペーン
description: プログラムとキャンペーン
seo-description: Adobe Campaign、プログラムおよびキャンペーンでは、様々なマーケティングアクティビティをグループ化して管理できます。プログラムおよびキャンペーンに関するレポートを使用すると、その影響を分析できます。
page-status-flag: 常にアクティブ化されていない
uuid: fe2812a8-196f-4aba- a739- fbbfffd754cb
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: 参照
topic-tags: マーケティングプラン
discoiquuid: 21b84028- d1a7-4ad6-891a-862a94565514
context-tags: campaign， overview;CampaignExplorer、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Programs and campaigns{#programs-and-campaigns}

## About plans, programs and campaigns {#about-plans--programs-and-campaigns}

Adobe Campaignでは、様々なタイプのアクティビティを作成および管理できるマーケティングキャンペーンを計画できます。電子メール、SMSメッセージ、プッシュ通知、ワークフロー、ランディングページこれらのキャンペーンとそのコンテンツをプログラムに収集できます。

プログラムとキャンペーンを使用すると、再グループ化して、それらにリンクされている様々なマーケティングアクティビティを表示できます。

* **プログラム** には、キャンペーン、ワークフロー、ランディングページなど他のプログラムを含めることができます。これはタイムラインに表示され、マーケティング活動の整理に役立ちます。国別、ブランド別、ブランド別、その他別に分けることができます。
* **キャンペーン** を使用すると、1つのエンティティで選択したすべてのマーケティングアクティビティを収集できます。キャンペーンには、電子メール、SMS、プッシュ通知、ダイレクトメール、ワークフロー、ランディングページなどがあります。

マーケティングプランをより適切に整理するには、次の階層をお勧めします。プログラム/サブプログラム/キャンペーン/ワークフロー/配信

プログラムおよびキャンペーンに関するレポートを使用すると、その影響を分析できます。例えば、キャンペーンレベルでレポートを作成して、そのキャンペーンに含まれるすべての配信に関するデータを集計できます。

**関連トピック:**

* [タイムライン](../../start/using/timeline.md)
* [動的レポートについて](../../reporting/using/about-dynamic-reports.md)

## Creating a program {#creating-a-program}

プログラムは、最初のレベルの組織です。サブプログラム、キャンペーン、ワークフローまたはランディングページを含めることができます。

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card.
1. Click on the **[!UICONTROL Create]** button.
1. **[!UICONTROL Creation mode]** 画面で、プログラムタイプを選択します。

   ![](assets/programs_and_campaigns_2.png)

   The program types available are based on templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Program templates]** section. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. **[!UICONTROL Properties]** 画面で、プログラムの名前とIDを入力します。

   ![](assets/programs_and_campaigns_3.png)

1. プログラムの開始日と終了日を選択します。これらの日付はプログラム自体のみに適用されます。

   親プログラム内でプログラムを作成できます。これを行うには、既存のプログラムから親プログラムを選択します。

1. Click on **[!UICONTROL Create]** to confirm the creation of the program.

プログラムが作成され、表示されます。**[!UICONTROL Create]** サブプログラム、キャンペーン、ワークフローまたはランディングページを追加するには、このボタンを使用します。

>[!NOTE]
>
>マーケティングアクティビティのリストからプログラムを作成することもできます。

## Creating a campaign {#creating-a-campaign}

プログラムおよびサブプログラムでは、キャンペーンを追加できます。キャンペーンには、電子メール、SMS、プッシュ通知、ワークフロー、ランディングページなどのマーケティング活動を含めることができます。

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card and access a program or sub-program.
1. Click on the **[!UICONTROL Create]** button and select **[!UICONTROL Campaign]**.
1. **[!UICONTROL Creation mode]** 画面で、キャンペーンタイプを選択します。

   ![](assets/programs_and_campaigns_7.png)

   The campaign types available are based on templates defined in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Campaign templates]**. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. **[!UICONTROL Properties]** 画面で、キャンペーンの名前とIDを入力します。
1. キャンペーンの開始日と終了日を選択します。これらの日付はキャンペーン自体のみに適用されます。

   ![](assets/programs_and_campaigns_8.png)

1. Click on **[!UICONTROL Create]** to confirm the creation of the campaign.

キャンペーンが作成され、表示されます。Use the **[!UICONTROL Create]** button to add marketing activities to your campaign.

>[!NOTE]
>
>使用許諾契約によっては、これらのアクティビティの一部のみにアクセスできます。

マーケティングアクティビティリストからキャンペーンを作成することもできます。キャンペーンのプロパティウィンドウを使用して、マーケティングアクティビティを親プログラムまたはサブプログラムにリンクできます。

## Programs and campaigns icons and statuses {#programs-and-campaigns-icons-and-statuses}

リスト内の各キャンペーンと各キャンペーンには視覚的な記号があり、色が実行ステータスを示すアイコンが表示されます。このステータスは、プログラムまたはキャンペーンの有効期間によって異なります。

* Gray: the program/campaign has not yet started - **[!UICONTROL Editing]** status.
* Blue: the program/campaign is in progress - **[!UICONTROL In progress]** status.
* Green: the program/campaign has finished - **[!UICONTROL Finished]** status. By default, the current date is automatically shown as the validity start date and the end date is calculated according to the start date (**D+186 days**). これらの日付は、プログラムまたはキャンペーンのプロパティで変更できます。

![](assets/programs_and_campaigns.png)

