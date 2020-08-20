---
title: コントロール母集団の作成
description: この使用例は、コントロール母集団の作成方法を示します。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 73a91344ada17d6eb0da0335e08ea27a1019b4fb
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 14%

---


# コントロール母集団の作成 {#building-control-group}

配信の影響を測定するには、特定のプロファイルを受け取らないように、ターゲットから一部のメッセージを除外します。 このコントロール母集団は、メッセージを受け取ったターゲット母集団の行動と比較するために使用できます。

これをAdobe Campaign Standardで行うには、次のアクティビティを含むワークフローを構築します。
* 特定の母集団をターゲットする [クエリ](../../automating/using/query.md) アクティビティ。
* ランダムなコントロール母集団をこの母集団から分離する [セグメント化](../../automating/using/segmentation.md) アクティビティ。
* メ [インターゲットにメッセージを送信する電子メール配信](../../automating/using/email-delivery.md) アクティビティ。
* ターゲットから除外されたプロファイル(ランダムなコントロール母集団)を更新する [Update data](../../automating/using/update-data.md) アクティビティ。

![](assets/wkf_control-group.png)

## プロファイルリソースの拡張 {#extending-profile}

まず、コントロール母集団に対応する新しいフィールドを使用して、 **[!UICONTROL Profile]** リソースを拡張する必要があります。 ワークフローが実行されると、このフィールドで、ターゲットから除外されたプロファイルがチェックされます。

1. / **[!UICONTROL Administration]** /から **[!UICONTROL Development]** をクリックし **[!UICONTROL Custom Resources]****[!UICONTROL Create]**&#x200B;ます。
1. まだ拡張していない場合は、を選択 **[!UICONTROL Extend an existing resource]** し、 **[!UICONTROL Profile]** リソースを選択します。
1. タブで、コントロール母集団用の新しいフィールドを追加し、その **[!UICONTROL Data structure]** フィールド **[!UICONTROL Boolean]** を選択し **[!UICONTROL Type]** ます。

   ![](assets/wkf_control-group-profile-field.png)

1. タブから **[!UICONTROL Screen definition]** 、 **[!UICONTROL Detail screen configuration]** セクションを展開し、作成したフィールドを選択して、各プロファイルに表示されるようにします。

   ![](assets/wkf_control-group-profile-field-screen.png)

1. 変更を保存します。
1. データベース構造を更新して、 **[!UICONTROL Profile]** 拡張リソースを発行します。 See [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

カスタムリソースの拡張について詳しくは、「リソースを追加する [主な手順](../../developing/using/key-steps-to-add-a-resource.md)」を参照してください。

## ワークフローの作成 {#creating-a-workflow}

1. 「**[!UICONTROL Marketing Activities]**」で、「**[!UICONTROL Create]**」をクリックして「**[!UICONTROL Workflow]**」を選択します。
1. ワークフローのタイプとして「**[!UICONTROL New Workflow]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. ワークフローのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

ワークフローを作成する詳細な手順については、[ワークフローの作成](../../automating/using/building-a-workflow.md)の節を参照してください。

## クエリアクティビティの作成{#create-a-query-activity}

1. /で、 **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**[](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを重複クリックして、ターゲットを定義します。
1. 例えば、で、ドラッグ&amp;ドロップ **[!UICONTROL Shortcuts]**&#x200B;し **[!UICONTROL Profile]**&#x200B;て、演算子 **[!UICONTROL Age]** を使用してを選択し、 **[!UICONTROL Greater than]****[!UICONTROL Value]** フィールドに「25」と入力します。
1. 「**[!UICONTROL Confirm]**」をクリックします。

## Segmentation アクティビティの作成{#creating-a-segmentation-activity}

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. タブで、編集するセグメントを選択し **[!UICONTROL Segments]** ます。
1. そのセグメントの **[!UICONTROL Configuration]** タブで、オプ **[!UICONTROL Limit the population of this segment]** ションを選択します。

   ![](assets/wkf_control-segment-configuration.png)

1. タブで、このオ **[!UICONTROL Limitation]** プションが選択されていることを確認し **[!UICONTROL Random sampling]** ます。

   ![](assets/wkf_control-segment-limitation.png)

1. 初期母集団の割合を定義します（例： 10%、クリック） **[!UICONTROL Confirm]**。 コントロール母集団は、ランダムに選択されたターゲット母集団の10%で構成されます。
1. タブで、 **[!UICONTROL Advanced options]** オプションを選択し、「」と「」 **[!UICONTROL Generate complement]** フィールドに入力し **[!UICONTROL Transition label]****[!UICONTROL Segment code]** ます。

   ![](assets/wkf_control-segment-advanced.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

## Creating an Email activity {#creating-an-email-activity}

1. >で、メ **[!UICONTROL Activities]** インアクティビティセグメントの後に **[!UICONTROL Channels]**&#x200B;電子メール配信 [](../../automating/using/email-delivery.md) ターゲットをドラッグ&amp;ドロップします。
1. Click the activity and select ![](assets/edit_darkgrey-24px.png) to edit it.
1. 「**[!UICONTROL Single send email]**」を選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールテンプレートを選択し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのプロパティを入力し、「**[!UICONTROL Next]**」をクリックします。
1. E メールのレイアウトを作成するには、「**[!UICONTROL Use the Email Designer]**」をクリックします。
1. コンテンツを編集して保存します。
1. メッセージダッシュボードの **[!UICONTROL Schedule]** セクションで、 **[!UICONTROL Request confirmation before sending messages]** オプションの選択を解除します。

## 更新データアクティビティの作成 {#creating-update-data-activity}

1. コントロール母集団セグメントの後に「 [データを更新](../../automating/using/update-data.md) 」アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. タブで、ドロッ **[!UICONTROL General]** プダウンリスト **[!UICONTROL Update]** から **[!UICONTROL Operation type]** 選択します。
1. In the **[!UICONTROL Identification]** tab, select the **[!UICONTROL Directly using the targeting dimension]** option.
1. 更新するディメンションとして以前に拡張した **[!UICONTROL Profile]** リソースを選択します。

   ![](assets/wkf_control-update-identification.png)

1. 「 **[!UICONTROL Fields to update]** 」タブで、リソースに追加したコントロール母集団フィールドを「」として選択し、条件として「true」 **[!UICONTROL Profile]****[!UICONTROL Destination]** と入力します。

   ![](assets/wkf_control-update-fields-to-update.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

## ワークフローの実行{#running-the-workflow}

をクリック **[!UICONTROL Start]** して、ワークフローを実行します。

ワークフローが実行されると、コントロール母集団の母集団が除外され、残りのメインターゲットにメッセージが送信されます。

リ **[!UICONTROL Profile]** ソースは次のように更新されます。コントロール母集団内にプロファイルがあった場合は、対応するフィールドがチェックされます。

![](assets/wkf_control-group-profile-checked.png)

メッセージから除外され、受信しなかった小さなグループと比較して、メッセージの受信者の反応を比較できるようになりました。

## 同じコントロール母集団の再利用 {#reusing-same-control-group}

上の例では、グローバルコントロール母集団を作成できます。これは、配信とは独立してプロファイル属性として保存されているためです。 実際、 **[!UICONTROL Profile]** リソース拡張の一部として作成された新しい「コントロール母集団」フィールドは、上記のワークフローが実行された後に更新されます。

したがって、次に同じコントロール母集団を使用する場合は、ランダムセグメント化を行う代わりに、新しい「コントロール母集団」フィールドでセグメント化を行うことができます。

手順は次のとおりです。
1. アクティビティの作成時に、 **[!UICONTROL Segmentation]** タブで編集するセグメントを選択し **[!UICONTROL Segments]** ます。
1. そのセグメントの **[!UICONTROL Configuration]** タブで、この **[!UICONTROL Limit the population of this segment]** オプションが選択されていないことを確認します。
1. タブで、メ **[!UICONTROL Filtering]** インワークスペース **[!UICONTROL Profiles (attributes)]** にドラッグ&amp;ドロップします。

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. ウィンドウで、「コントロール母集団」（リソースに追加したフィールド）を選択し、フィルター条件 **[!UICONTROL Add a rule - Profiles (attributes)]****[!UICONTROL Profile]****[!UICONTROL Yes]** として選択します。

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)
