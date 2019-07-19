---
title: 除外
seo-title: 除外
description: 除外
seo-description: 除外アクティビティを使用すると、特定の条件に従って1つの母集団から要素を除外できます。
page-status-flag: 常にアクティブ化されていない
uuid: b79e7f73-37a0-4ec3- ac5a-5449dc1b1f22
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: d5312fcd-43ad-428e- bde9-90f062e9358c
context-tags: exclusion， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Exclusion{#exclusion}

## 説明 {#description}

![](assets/exclusion.png)

**[!UICONTROL Exclusion]** アクティビティでは、特定の条件に従って、ある母集団からの要素を除外できます。

## Context of use {#context-of-use}

**[!UICONTROL Exclusion]** アクティビティは、受信移行母集団に対して追加のフィルターを実行するために使用されます。

メインセットは、インバウンドトランジション間で定義されます。他のインバウンドトランジションのメンバーは、プライマリセットから除外されます。除外アクティビティのアウトバウンドトランジションには、他のインバウンドトランジションで発生しなかったプライマリセットのメンバーのみが含まれます。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Exclusion]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Primary set]** from the inbound transitions. これは、要素が除外されるセットです。もう1つは、プライマリセットから除外される前に要素に一致する要素です。

   >[!NOTE]
   >
   >インバウンドトランジションには、同じタイプの母集団を含める必要があります。例えば、プライマリセットにテストプロファイルが含まれる場合、他のトランジションにもテストプロファイルを含める必要があります。

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

次の例は、18才から27才までのAdobe Campaignデータベースからプロファイルをフィルターするように設定された2つのクエリーアクティビティを示しています。無効な電子メールアドレスを持つプロファイルは、最初のセットから除外されます。これにより、電子メールを送信できます。

![](assets/wkf_exclusion_example.png)

