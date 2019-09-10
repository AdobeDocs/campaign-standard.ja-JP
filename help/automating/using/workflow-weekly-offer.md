---
title: 「ワークフローのユースケース:週次配送の作成」
seo-title: 「ワークフローのユースケース:週次配送の作成」
description: 「ワークフローのユースケース:週次配送の作成」
seo-description: 「ワークフローのユースケース:週次配送の作成」
page-status-flag: 決して活性化されていない
uuid: 396a3de1-6fa-4385- ac9f-15fdee5a366
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: '実行活動 '
discoiquuid: 377821e6-69f8-41cc- a1ad-8a2f5d409
context-tags: ワークフロー、ユースケース、クエリ、配信、スケジューラ
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# Worflowユースケース:毎週火曜日に電子メール配信を作成する{#creating-email-every-tuesday}

毎週火曜日に電子メールをお客様のすべてのお客様に送信できます。

1. で **[!UICONTROL Marketing Activities]**、をクリック **[!UICONTROL Create]** して選択 **[!UICONTROL Workflow]**&#x200B;します。
1. ワークフロータイプ **[!UICONTROL New Workflow]** として選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. ワークフローのプロパティを入力し、をクリック **[!UICONTROL Create]**&#x200B;します。

## スケジューラ・アクティビティの作成{#creating-a-scheduler-activity}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Execution]**、をドラッグアンドドロップ **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png)します。
1. アクティビティをダブルクリックします。
1. 配信の実行を構成します。
1. で、を **[!UICONTROL Execution frequency]**&#x200B;選択 **[!UICONTROL Weekly]**&#x200B;します。
1. 搬送のaおよび **[!UICONTROL Time]****[!UICONTROL Repetition frequency]** aを選択します。
1. で、を **[!UICONTROL Days of the week]**&#x200B;選択 **[!UICONTROL Tuesday]**&#x200B;します。
1. ワークフローのパラメーター **[!UICONTROL Start]** と **[!UICONTROL Expiration]** パラメーターを指定します。
1. アクティビティを確認し、ワークフローを保存します。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>ワークフローを特定の **[!UICONTROL Time Zone]****[!UICONTROL Execution options]**&#x200B;タブで開始するには、タイムゾーンフィールドでスケジューラのタイムゾーンを設定します。

## クエリアクティビティの作成{#creating-a-query-activity}

1. **[!UICONTROL Activities]** &gt;&gt; **[!UICONTROL Targeting]**&#x200B;で、受信者を選択するには **[!UICONTROL query]** 、アクティビティをドラッグアンドドロップしてダブルクリックします。
1. **[!UICONTROL Shortcuts]** &gt;&gt; **[!UICONTROL Profile]**&#x200B;で、ドラッグアンドドロップ **[!UICONTROL Email]**&#x200B;します。
1. オペレータ **[!UICONTROL is not empty]** として選択します。
1. **[!UICONTROL Shortcuts]** &gt;&gt; **[!UICONTROL General]**&#x200B;で、プロファイルを追加し、値 **[!UICONTROL no longer contact by email]** で選択 **[!UICONTROL No]**&#x200B;します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

![](assets/wf-complement-query.png)

## 電子メール配信の作成{#creating-an-email-delivery}

1. **[!UICONTROL Activities]** &gt;で **[!UICONTROL Channels]**、をドラッグアンドドロップ **[!UICONTROL Email delivery]**&#x200B;します。
1. アクティビティをクリックし、編集 ![](assets/edit_darkgrey-24px.png) するように選択します。
1. を選択 **[!UICONTROL Recurring email]** してをクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールテンプレートを選択し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのプロパティを入力し、をクリック **[!UICONTROL Next]**&#x200B;します。
1. 電子メールのレイアウトを作成するには、をクリック **[!UICONTROL Use Email Designer]**&#x200B;します。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをカスタマイズします。
1. **[!UICONTROL Save]**&#x200B;をクリックします。

詳細については、電子メール [の設計](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)を参照してください。

**関連トピック:**

* [クエリアクティビティ](../..//automating/using/query.md)
* [スケジューラアクティビティ](../..//automating/using/scheduler.md)
* [Eメール配信](../..//automating/using/email-delivery.md)
* [Eメールチャネル](../..//channels/using/creating-an-email.md)
