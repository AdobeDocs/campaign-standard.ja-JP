---
title: メッセージ内のオーディエンスの選択
description: 「E メールのオーディエンスを選択するためのステップバイステップの手順：主なターゲットの母集団とテストプロファイル」
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---


# メッセージ内のオーディエンスの選択{#selecting-an-audience-in-a-message}

Adobe Campaign を使用すると、メッセージのオーディエンス内で複数のプロファイルタイプを設定できます。

オーディエンスは、作成ウィザードを使用してメッセージを作成するときに定義できます。メッセージが作成済みの場合は、メッセージダッシュボードから定義することもできます。

>[!NOTE]
>
>ワークフロー内で作成されたオーディエンスが追加データで強化された場合、これらのデータを使用してスタンドアロン配信をパーソナライズすることはできません。ワークフローで実行される配信からのみ使用できます。

1. ダッシュボードから、開始するオーディエンスブロックに移動します。

   ![](assets/delivery_audience_definition_1.png)

   オーディエンスを定義する画面が開きます。ここには 2 つのタブがあり、メッセージを受け取るオーディエンスのタイプをそれぞれ別々に定義できます。

   * ターゲット
   * テストプロファイル
   ![](assets/delivery_audience_definition_2.png)

1. 電子メールのメイン **[!UICONTROL Target]** を定義します。これは、電子メールの通常のターゲットオーディエンスです。

   ターゲットは「**[!UICONTROL Target]**」タブで定義され、データベースで識別されたプロファイルで構成されます。

   メインターゲットは、[クエリエディター](../../automating/using/editing-queries.md#creating-queries)機能を使用して確定できます。

   このタブの「**[!UICONTROL Shortcuts]**」パレットには、識別されたプロファイルで定義された定義済みフィルターとオーディエンスのみが含まれます。「**[!UICONTROL Explorer]**」タブを使用すると、追加の設定にアクセスできます。

   したがって、既存のオーディエンスの再利用や組み合わせができ、また既存のオーディエンスにフィルターを追加することもできます。

1. E メールに使用する **[!UICONTROL Test profiles]** を定義します。テストプロファイルは、メインターゲットに E メールを送信する前に E メールのテスト用にあらかじめ送信される配達確認を受信します。

   テストプロファイルの設定の詳細については、[テストプロファイル](../../audiences/using/managing-test-profiles.md)の節を参照してください。

その後、オーディエンスブロックが更新され、該当する E メールに対してターゲットプロファイルとテスト要素が選択されたことが示されます。

![](assets/delivery_audience_definition_3.png)

