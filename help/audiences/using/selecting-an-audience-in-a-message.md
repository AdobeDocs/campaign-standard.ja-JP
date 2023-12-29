---
title: メッセージ内のオーディエンスの選択
description: 「メールのオーディエンスを選択するためのステップバイステップの手順：主なターゲットの母集団とテストプロファイル」
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
feature: Audiences
role: User
level: Intermediate
exl-id: 239959ad-6386-42bf-a86a-5694cdaecd83
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 70%

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

   ターゲットが **[!UICONTROL Target]** 」タブに表示され、データベースで識別されたプロファイルで構成されます。 メインターゲットは、[クエリエディター](../../automating/using/editing-queries.md#creating-queries)機能を使用して確定できます。

   このタブの「**[!UICONTROL Shortcuts]**」パレットには、識別されたプロファイルで定義された定義済みフィルターとオーディエンスのみが含まれます。「**[!UICONTROL Explorer]**」タブを使用すると、追加の設定にアクセスできます。

   したがって、既存のオーディエンスの再利用や組み合わせができ、また既存のオーディエンスにフィルターを追加することもできます。

   >[!NOTE]
   >
   >オーディエンスをターゲティングする場合、オーディエンスの定義は参照されませんが、 **コピー済み** をクエリに追加します。 クエリでターゲット設定した後にオーディエンスに変更を加えた場合は、新しい定義を考慮するようにクエリを再度設定する必要があります。

1. メールに使用する **[!UICONTROL Test profiles]** を定義します。テストプロファイルは、メインターゲットにメールを送信する前にメールのテスト用にあらかじめ送信される配達確認を受信します。

   テストプロファイルの設定の詳細については、[テストプロファイル](../../audiences/using/managing-test-profiles.md)の節を参照してください。

1. 必要に応じて、対応するタブを使用してコントロール母集団を定義できます。 これにより、一部のプロファイルをターゲットから取り消して、メッセージを受信しないようにできます。 詳しくは、 [コントロール母集団の追加](../../sending/using/control-group.md).

1. また、代用アドレスを使用して、プロファイルが受け取るメッセージの正確な内容を取得できます。  詳しくは、[ターゲットプロファイルを使用した電子メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)を参照してください。

その後、オーディエンスブロックが更新され、該当するメールに対してターゲットプロファイルとテストプロファイルが選択されたことが示されます。

![](assets/delivery_audience_definition_3.png)
