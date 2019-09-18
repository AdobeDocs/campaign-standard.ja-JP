---
title: '"ワークフローの使用例：週次配送の作成'
seo-title: '"ワークフローの使用例：週次配送の作成'
description: '"ワークフローの使用例：週次配送の作成'
seo-description: '"ワークフローの使用例：週次配送の作成'
page-status-flag: 未活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: '実行活動 '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: ワークフロー，ユースケース，クエリ，配信，スケジューラ
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# ワークフローの使用例：毎週火曜日に電子メール配信を作成する{#creating-email-every-tuesday}

毎週火曜日に、特別キャンペーンのお客様全員にEメールを送信できます。

1. で、をク **[!UICONTROL Marketing Activities]**&#x200B;リックして **[!UICONTROL Create]** を選択しま **[!UICONTROL Workflow]**&#x200B;す。
1. ワークフロー **[!UICONTROL New Workflow]** の種類としてを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**&#x200B;す。

## スケジューラ·アクティビティの作成{#creating-a-scheduler-activity}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Execution]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Scheduler activity]**&#x200B;す。
1. アクティビティをダブルクリックします。
1. 配信の実行を構成します。
1. でを選 **[!UICONTROL Execution frequency]**&#x200B;択します **[!UICONTROL Weekly]**。
1. 搬送のと **[!UICONTROL Time]** を選 **[!UICONTROL Repetition frequency]** 択します。
1. でを選 **[!UICONTROL Days of the week]**&#x200B;択します **[!UICONTROL Tuesday]**。
1. ワークフローの **[!UICONTROL Start]** とパラメ **[!UICONTROL Expiration]** ータを指定します。
1. アクティビティを確認し、ワークフローを保存します。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>特定の場所でワークフローを開始するに **[!UICONTROL Time Zone]**&#x200B;は、タブで、[タ&#x200B;**[!UICONTROL Execution options]**&#x200B;イムゾーン]フィールドにスケジューラのタイムゾーンを設定します。

## クエリアクティビティの作成{#creating-a-query-activity}

1. &gt;で、受 **[!UICONTROL Activities]** 信者を **[!UICONTROL Targeting]**&#x200B;選択するには、アクティビティをドラッグアンドドロップし **[!UICONTROL query]** てダブルクリックします。
1. &gt;で、ド **[!UICONTROL Shortcuts]** ラッ **[!UICONTROL Profile]**&#x200B;グアンドドロップしま **[!UICONTROL Email]**&#x200B;す。
1. 演算子 **[!UICONTROL is not empty]** として選択します。
1. &gt;で、プ **[!UICONTROL Shortcuts]** ロフ **[!UICONTROL General]**&#x200B;ァイルを追加し、値で **[!UICONTROL no longer contact by email]** を選択します **[!UICONTROL No]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 電子メール配信の作成{#creating-an-email-delivery}

1. &gt;で、 **[!UICONTROL Activities]** をド **[!UICONTROL Channels]**&#x200B;ラッグ&amp;ドロップしま **[!UICONTROL Email delivery]**&#x200B;す。
1. アクティビティをクリックし、編集するア ![](assets/edit_darkgrey-24px.png) クティビティを選択します。
1. を選択し、 **[!UICONTROL Recurring email]** をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. 電子メールのレイアウトを作成するには、をクリックしま **[!UICONTROL Use Email Designer]**&#x200B;す。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをカスタマイズします。
1. Click **[!UICONTROL Save]**.

詳細については、「電子メールのデザ [イン」を参照してください](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**関連トピック：**

* [クエリアクティビティ](../..//automating/using/query.md)
* [スケジューラの動作](../..//automating/using/scheduler.md)
* [電子メール配信](../..//automating/using/email-delivery.md)
* [電子メールチャネル](../..//channels/using/creating-an-email.md)
