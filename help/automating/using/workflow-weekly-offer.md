---
title: 「ワークフローの使用例：週別配信の作成」
description: 「ワークフローの使用例：週別配信の作成」
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# ワークフローの使用例：毎週火曜日に電子メール配信を作成する{#creating-email-every-tuesday}

特別オファーに関しては、毎週火曜日にすべての顧客に電子メールを送信できます。

1. で、を **[!UICONTROL Marketing Activities]**クリックし**[!UICONTROL Create]** てを選択しま **[!UICONTROL Workflow]**す。
1. ワークフロー **[!UICONTROL New Workflow]**タイプとして選択し、をクリックしま**[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**す。

## スケジューラーアクティビティの作成{#creating-a-scheduler-activity}

1. /で、 **[!UICONTROL Activities]**をドラ**[!UICONTROL Execution]**&#x200B;ッグ&amp;ドロップしま **[!UICONTROL Scheduler activity]**す。
1. アクティビティをダブルクリックします。
1. 配信の実行を設定します。
1. で、を **[!UICONTROL Execution frequency]**選択しま**[!UICONTROL Weekly]**&#x200B;す。
1. 配信の **[!UICONTROL Time]**とを選**[!UICONTROL Repetition frequency]** 択します。
1. で、を **[!UICONTROL Days of the week]**選択しま**[!UICONTROL Tuesday]**&#x200B;す。
1. ワークフロー **[!UICONTROL Start]**のパラメーター**[!UICONTROL Expiration]** とを指定します。
1. アクティビティを確認し、ワークフローを保存します。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>特定のタブでワークフローを開始する **[!UICONTROL Time Zone]**には、「タ**[!UICONTROL Execution options]**&#x200B;イムゾーン」フィールドにスケジューラーのタイムゾーンを設定します。 デフォルトでは、選択したタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンになります(「ワーク [フローの構築](../../automating/using/building-a-workflow.md)」を参照)。

## クエリーアクティビティの作成{#creating-a-query-activity}

1. /で、 **[!UICONTROL Activities]**受信者**[!UICONTROL Targeting]**&#x200B;を選択するには、アクティビティをドラッグ&amp;ドロ **[!UICONTROL query]**ップし、ダブルクリックします。
1. /で、 **[!UICONTROL Shortcuts]**ドラ**[!UICONTROL Profile]**&#x200B;ッグ&amp;ドロップしま **[!UICONTROL Email]**す。
1. 演算子 **[!UICONTROL is not empty]**として選択します。
1. /で、 **[!UICONTROL Shortcuts]**プロフ**[!UICONTROL General]**&#x200B;ァイルを追加し、値を使用 **[!UICONTROL no longer contact by email]**してを選択しま**[!UICONTROL No]**&#x200B;す。
1. クリック **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. /で、 **[!UICONTROL Activities]**をドラ**[!UICONTROL Channels]**&#x200B;ッグ&amp;ドロップしま **[!UICONTROL Email delivery]**す。
1. アクティビティをクリックし、編集する ![](assets/edit_darkgrey-24px.png) 対象を選択します。
1. を選択し、 **[!UICONTROL Recurring email]**をクリックしま**[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**す。
1. 電子メールのレイアウトを作成するには、[オン]をクリックしま **[!UICONTROL Use Email Designer]**す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをパーソナライズします。
1. クリック **[!UICONTROL Save]**.

詳しくは、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**関連トピック：**

* [クエリアクティビティ](../..//automating/using/query.md)
* [スケジューラーアクティビティ](../..//automating/using/scheduler.md)
* [E メール配信](../..//automating/using/email-delivery.md)
* [E メールチャネル](../..//channels/using/creating-an-email.md)
