---
title: メッセージ内のオーディエンスの選択
description: 「電子メールのオーディエンスを選択するためのステップ・バイ・ステップ手順：メインターゲットの訪問者数とテストプロファイル」
page-status-flag: 非活性化の
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参照
topic-tags: 管理対象
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# メッセージ内のオーディエンスの選択{#selecting-an-audience-in-a-message}

Adobe Campaignでは、メッセージのオーディエンス内に複数のプロファイルタイプを設定できます。

オーディエンスは、作成ウィザードを使用してメッセージを作成する際に、または既に作成済みの場合はメッセージダッシュボードから定義できます。

>[!NOTE]
>
>オーディエンスがワークフロー内に構築され、追加データを使用して強化された場合、これらのデータを使用してスタンドアロンの配信をパーソナライズすることはできません。 ワークフローで実行された配信からのみ使用できます。

1. ダッシュボードから、開始するオーディエンスブロックに移動します。

   ![](assets/delivery_audience_definition_1.png)

   オーディエンスを定義する画面が開きます。 このタブには2つのタブがあり、メッセージを受け取るオーディエンスのタイプごとに別々に定義できます。

   * ターゲット
   * テストプロファイル
   ![](assets/delivery_audience_definition_2.png)

1. 電子メールのメイ **[!UICONTROL Target]** ンを定義します。 これは、電子メールの通常のターゲットオーディエンスです。

   ターゲットはタブで定義され、デ **[!UICONTROL Target]** ータベースから識別されたプロファイルで構成されます。

   クエリーエディター機能を使用して、メインターゲ [ットを設定](../../automating/using/editing-queries.md#creating-queries) 。

   このタブでは、パレットには事 **[!UICONTROL Shortcuts]** 前定義済みのフィルターと、識別されたプロファイルで定義されたオーディエンスのみが含まれます。 このタ **[!UICONTROL Explorer]** ブからは、追加の設定にアクセスできます。

   したがって、既存のオーディエンスを再利用したり結合したり、追加のフィルターを適用したりすることができます。

1. 電子メ **[!UICONTROL Test profiles]** ールに使用するを定義します。 テストプロファイルには、メインターゲットに電子メールを送信する前に、電子メールをテストする前に送信できる校正が含まれます。

   テストプロファイルの設定の詳細については、「テストプロファイル」の節を参 [照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md) い。

次に、オーディエンスブロックが更新され、対象の電子メールに対してターゲットプロファイルとテストプロファイルが選択されていることを示します。

![](assets/delivery_audience_definition_3.png)

