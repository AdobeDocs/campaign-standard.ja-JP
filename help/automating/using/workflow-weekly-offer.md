---
title: 週次配信の作成
description: この使用例では、週別配信の作成方法を示します。
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---


# 毎週火曜日に電子メール配信を作成する{#creating-email-every-tuesday}

特別オファー向けの電子メールは毎週火曜日にすべての顧客に送信できます。

1. で、 **[!UICONTROL Marketing Activities]**&#x200B;をクリック **[!UICONTROL Create]** してを選択し **[!UICONTROL Workflow]**&#x200B;ます。
1. ワークフローのタイプ **[!UICONTROL New Workflow]** として選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. ワークフローのプロパティを入力し、をクリックし **[!UICONTROL Create]**&#x200B;ます。

## スケジューラーアクティビティの作成{#creating-a-scheduler-activity}

1. /で、 **[!UICONTROL Activities]** スケジューラー **[!UICONTROL Execution]**[](../../automating/using/scheduler.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを重複クリックします。
1. 配信の実行を設定します。
1. で、 **[!UICONTROL Execution frequency]**&#x200B;を選択し **[!UICONTROL Weekly]**&#x200B;ます。
1. 配信 **[!UICONTROL Time]** のおよびを選択 **[!UICONTROL Repetition frequency]** します。
1. で、 **[!UICONTROL Days of the week]**&#x200B;を選択し **[!UICONTROL Tuesday]**&#x200B;ます。
1. ワークフロー **[!UICONTROL Start]** のパラメーターと **[!UICONTROL Expiration]** を指定します。
1. アクティビティを確認し、ワークフローを保存します。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>特定のタイムゾーンでワークフローを開始するに **[!UICONTROL Time Zone]**&#x200B;は、「タイムゾーン」**[!UICONTROL Execution options]**&#x200B;タブで、スケジューラーのタイムゾーンを「タイムゾーン」フィールドに設定します。 デフォルトでは、選択したタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンになります(「ワークフローの [構築](../../automating/using/building-a-workflow.md)」を参照)。

## Creating a Query activity{#creating-a-query-activity}

1. / **[!UICONTROL Activities]** で、受信者を選択するには、 **[!UICONTROL Targeting]**&#x200B;クエリ [](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップし、重複でクリックします。
1. / **[!UICONTROL Shortcuts]** に **[!UICONTROL Profile]**&#x200B;ドラッグ&amp;ドロップ **[!UICONTROL Email]**&#x200B;します。
1. 演算子 **[!UICONTROL is not empty]** として選択します。
1. >で、プロファイル **[!UICONTROL Shortcuts]** を追加し、値 **[!UICONTROL General]**&#x200B;を使用してを選択し **[!UICONTROL no longer contact by email]****[!UICONTROL No]**&#x200B;ます。
1. クリック **[!UICONTROL Confirm]** .

![](assets/wf-complement-query.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. >で、 **[!UICONTROL Activities]** 電子メール配信 **[!UICONTROL Channels]**[](../../automating/using/email-delivery.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティをクリックし、「編集」 ![](assets/edit_darkgrey-24px.png) を選択します。
1. を選択 **[!UICONTROL Recurring email]** し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールテンプレートを選択し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのプロパティを入力し、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. 電子メールのレイアウトを作成するには、[オン]をクリックし **[!UICONTROL Use Email Designer]**&#x200B;ます。
1. 要素を挿入するか、既存のテンプレートを選択します。
1. フィールドとリンクを使用して電子メールをパーソナライズします。
1. クリック **[!UICONTROL Save]** .

詳しくは、「電子メールの [設計](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」を参照してください。

**関連トピック：**

* [E メールチャネル](../../channels/using/creating-an-email.md)
