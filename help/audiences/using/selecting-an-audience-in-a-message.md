---
title: メッセージ内のオーディエンスの選択
seo-title: メッセージ内のオーディエンスの選択
description: メッセージ内のオーディエンスの選択
seo-description: 「電子メールのオーディエンスを選択する手順」:メインターゲット母集団とテストプロファイル
page-status-flag: 常にアクティブ化されていない
uuid: 7d8f8446- f2e0-49c1-83f6-9667b29bc228
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: 管理-オーディエンス
discoiquuid: 158da6ff-8899-4e7b- b925-8a42c3de46a1
context-tags: DeliveryCreation，ウィザード;配信、オーディエンス、戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c9e33f51ab497b8bd111dfc307670f2fde5d804f

---


# Selecting an audience in a message{#selecting-an-audience-in-a-message}

Adobe Campaignでは、メッセージのオーディエンス内に複数のプロファイルタイプを設定できます。

オーディエンスは、作成ウィザードまたはメッセージの作成済みのメッセージダッシュボードからメッセージを作成するときに定義できます。

>[!NOTE]
>
>オーディエンスがワークフローに組み込まれ、追加データを使用して充実している場合、これらのデータを使用してスタンドアロンの配信をパーソナライズすることはできません。ワークフローで実行された配信からのみ使用できます。

1. ダッシュボードから、開始するオーディエンスブロックに移動します。

   ![](assets/delivery_audience_definition_1.png)

   オーディエンスを定義する画面が開きます。メッセージを受信するオーディエンスのタイプを個別に定義できる2つのタブがあります。

   * Target
   * テストプロファイル
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. これは、電子メールの通常のターゲットオーディエンスです。

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   [クエリエディター](../../automating/using/editing-queries.md#creating-queries) 機能を使用してメインターゲットを確立できます。

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. **[!UICONTROL Explorer]** このタブでは、追加の設定にアクセスできます。

   そのため、既存のオーディエンスを再利用したり結合したり、その他のフィルターを適用したりできます。

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. テストプロファイルは、電子メールをテストしてからメインターゲットに送信する前に送信できる配達確認を受け取ります。

   For more information on configuring test profiles, refer to the [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md) section.

その後、オーディエンスブロックが更新され、対象となる電子メールに対してターゲットプロファイルとテストプロファイルが選択されていることがわかります。

![](assets/delivery_audience_definition_3.png)

