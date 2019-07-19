---
title: フォーク
seo-title: フォーク
description: フォーク
seo-description: フォークアクティビティを使用すると、複数のアクティビティを同時に開始するためにアウトバウンドトランジションを作成できます。
page-status-flag: 常にアクティブ化されていない
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: f8ffe7af- e18c-4599-8fd0- fcd192565323
context-tags: フォーク、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Fork{#fork}

## 説明 {#description}

![](assets/fork.png)

**[!UICONTROL Fork]** アクティビティによって、複数のアクティビティを同時に開始するためのアウトバウンドトランジションを作成できます。

## Context of use {#context-of-use}

**[!UICONTROL Fork]** アクティビティでは、同じワークフロー内で複数の異なるアクティビティを個別に実行できます。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Fork]** activity into your workflow.
1. クエリなどの他のアクティビティに接続します。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. アウトバウンドトランジションの数を指定します。名前とラベルの属性を設定することもできます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

次の例では、Adobe Campaignデータベースのプロファイルをターゲットとする2つのクエリーアクティビティ（この場合、パリ在住の女性）の共通部分を示しています。したがって、フォークアクティビティでは同時に複数のアクティビティを使用できます。オーディエンスを保存して、計算対象の母集団を記憶し、セグメントごとにターゲットコンテンツと共に2つの異なる電子メールを送信する訪問者を保存する場合。最初の電子メールは、18~40才のパリビア女性に送信され、40を超える別のターゲットとなるPariianの女性に送信されます。

![](assets/wkf_fork_example.png)

