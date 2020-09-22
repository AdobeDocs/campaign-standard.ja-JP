---
title: メッセージ送信時のコントロール母集団の追加
description: Adobe Campaign Standardを使用してメッセージのターゲットを定義する際に、コントロール母集団を追加する方法を説明します。
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
source-git-commit: cd38d849052e44e5a50c69d7f8184feb2227fdf4
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 6%

---


# コントロール母集団の追加 {#adding-control-group}

コントロール母集団を使用すると、キャンペーンの影響を測定するために、オーディエンスの一部にメッセージを送信しないようにできます。

これをAdobe Campaignで行うには、配信のターゲットを定義する際に <b>コントロール母集団</b> を作成します。 プロファイルは、コントロール母集団にランダムに追加されるか、フィルターされるかどうか、または条件に基づいて追加されます。

その後、メッセージを受け取ったターゲットの訪問者の行動と、ターゲット設定されていない連絡先の行動を比較できます。 送信ログに基づいて、将来のキャンペーンでコントロール母集団をターゲットすることもできます。

<!--The control group is built when the delivery is prepared.-->

## 概要 {#overview}

コントロール母集団は、主ターゲットからランダムに抽出され、及び/又は特定の母集団から選択される。 その結果、コントロール母集団を定義する主な方法は2つあります。
* **メインターゲットからプロファイルを数個抽出します** 。
* **クエリで定義された条件に基づいて** 、一部のプロファイルを除外します。

コントロール母集団を定義する際は、両方の方法を使用できます。

配信の準備手順でコントロール母集団に含まれているすべてのプロファイルが、メインターゲットから削除されます。 送信されたメッセージは受信されません。

## ターゲット母集団からの抽出 {#extraction-target-population}

コントロール母集団を定義するには、ターゲット母集団から抽出するか、ランダムに、または並べ替えに基づいて抽出するか、割合または一定数のプロファイルを選択します。

### ターゲット抽出 {#target-extraction}

まず、ターゲットからプロファイルを抽出する方法を定義します。 **ランダム** 、または **並べ替えに基づいて選択します**。

この **[!UICONTROL Target extraction]** セクションで、次のいずれかを選択します。

* **[!UICONTROL Random sampling]**:配信を準備すると、Adobe Campaignは、 [サイズ制限として設定する割合または最大数に対応するプロファイルをランダムに抽出し](#size-limit)ます。

   For example, if you then set the threshold to 10 in the **[!UICONTROL Limits]** section, the control group will be made up of 10% selected randomly from the targeted population.<!--Change screenshot to match example)-->

   ![](assets/control-group-random-sampling.png)

* **[!UICONTROL Keep only the first records after sorting]**:このオプションを使用すると、1つ以上の並べ替え順に基づく制限を定義できます。

   例：

   * フィールドを並べ替え条件として選択し **[!UICONTROL Age]** ます。
   * 100をしきい値として **[!UICONTROL Limits]** 節に定義します( [サイズ制限を参照](#size-limit))。
   * この **[!UICONTROL Descending sort]** オプションは選択したままにします。

   その結果、このコントロール母集団は最も古い100受信者から成り立ちます。<!--Change screenshot to match example)-->

   ![](assets/control-group-keep-first-records.png)

   ほとんどまたは頻繁に購入しないプロファイルを含むコントロール母集団を定義し、その行動と連絡先の受信者の行動を比較すると興味深い結果が得られます。

>[!NOTE]
>
>こ **[!UICONTROL No extraction]** のオプションを使用しない場合に選択し **[!UICONTROL Target extraction]** ます。

<!--![](assets/control-group-no-extraction.png)-->

### サイズ制限 {#size-limit}

を選択した場合 **[!UICONTROL Random sampling]** も、 **[!UICONTROL Keep only the first records after sorting]**&#x200B;選択した場合も、メインターゲットから抽出するプロファイル数を制限する方法を設定する必要があります。 次のいずれかの操作を行います。

* 対応するフレーム **[!UICONTROL Size (as a % of the initial population)]** を選択して塗りつぶします。

   例えば、10を設定した場合、上で選択したオプションに応じて、次のいずれかがAdobe Campaignに表示されます。
   * ターゲットの母集団の10%をランダムに抽出します。
   * 並べ替え条件として **[!UICONTROL Age]** フィールドを選択した場合は、ターゲットの母集団から最も古い10%のプロファイルを抽出します。

   >[!NOTE]
   >
   >このオプションをオフにすると、最も若い10%のプロファイルが抽出され **[!UICONTROL Descending sort]** ます。

* 対応するフレーム **[!UICONTROL Maximum size]** を選択して塗りつぶします。

   例えば、100を設定した場合、Adobe Campaignは次のいずれかになります。
   * ターゲット母集団からランダムに100個のプロファイルを抽出します。
   * 並べ替え条件として **[!UICONTROL Age]** フィールドを選択した場合は、ターゲットの母集団から最も古いプロファイル100個を抽出します。

   >[!NOTE]
   >
   >このオプションをオフにすると、 **[!UICONTROL Descending sort]** 最も若いプロファイル100個が抽出されます。

## 特定の母集団の除外 {#excluding-specific-population}

コントロール母集団を定義する別の方法は、クエリを使用して、特定のターゲットを訪問者から除外することです。

手順は次のとおりです。

1. セクションで、 **[!UICONTROL Target exclusion]** をクリックし **[!UICONTROL Define target exclusion]**&#x200B;ます。

   ![](assets/control-group-define-target-exclusion.png)

1. 除外条件は、 [クエリエディターを使用して定義します](../../automating/using/editing-queries.md)。 また、以前に作成した [オーディエンス](../../audiences/using/about-audiences.md) も選択できます。

   ![](assets/control-group-target-exclusion.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

クエリの結果に一致するプロファイルは、ターゲットから除外されます。

<!--For more on using the query editor, see the [Editing queries](../../automating/using/editing-queries.md) section.-->

## 使用例：コントロール母集団を設置する {#control-group-example}

次の例に、両方の方法を使用してコントロール母集団を定義する方法を示します。メインターゲットからプロファイルを抽出し、クエリを使用して特定の母集団を除外します。

1. ワークフローの作成. ワークフローを作成する詳細な手順については、[ワークフローの作成](../../automating/using/building-a-workflow.md)の節を参照してください。
1. /で、 **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**[](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップします。 アクティビティを重複クリックし、ターゲットを定義します。 <!--For example, in **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profile]**, select **[!UICONTROL Age]** with the operator **[!UICONTROL Greater than]** and type 25 in the **[!UICONTROL Value]** field.-->

1. / **[!UICONTROL Activities]** で、メインアクティビティセグメントの後に **[!UICONTROL Channels]**&#x200B;電子メール配信 [](../../automating/using/email-delivery.md) をドラッグ&amp;ドロップし、ターゲットセグメントを編集します。
1. 配信ダッシュボードの **[!UICONTROL Audience]** ブロックをクリックします。

1. 「**[!UICONTROL Control group]**」タブを選択します。

   ![](assets/control-group-tab.png)

1. セクションから **[!UICONTROL Target extraction]** を選択し **[!UICONTROL Keep only the first records after sorting]**&#x200B;ます。
1. 年齢で並べ替え、「 **[!UICONTROL Descending]** 並べ替え」オプションはオンのままにします。

   ![](assets/control-group-sorting-column.png)

1. 最大サイズを100に設定します。 ターゲットから最も古いプロファイル100個が抽出されます。

1. 「 **[!UICONTROL Target exclusion]** 」セクションで、 [クエリエディターで選択した条件に基づいて、ターゲットから除外するプロファイルを定義します](../../automating/using/editing-queries.md)。 例えば、「Age is less than 20」とします。

   ![](assets/control-group-target-exclusion-example.png)

   20歳未満のプロファイルは除外されます。

1. [配信の準備を起動し](../../sending/using/preparing-the-send.md) 、送信を [確認します](../../sending/using/confirming-the-send.md)。

抽出されたプロファイル(最も古い100個のプロファイル)と、クエリ(20未満のプロファイル)に基づいて定義されたは、メインターゲットから取り出されます。 メッセージは受信されません。

## 結果の比較 {#delivery-logs}

配信を送ったので、コントロール母集団で何ができる？

**送信ログを抽出して** 、通信を受信しなかったコントロール母集団が有効なターゲットとどのように動作したかを比較できます。 また、配信ログを使用して別のターゲティングを **作成することもできます**。

>[!IMPORTANT]
>
>Adobe Campaignに接続するには、 [管理者の役割](../../administration/using/users-management.md#functional-administrators) 、 **[!UICONTROL All]** 組織単位 [](../../administration/using/organizational-units.md) の一部である必要があります。 特定のユーザーまたはユーザーのグループに対するアクセスを制限する場合は、配信ログにアクセスできるように、 **[!UICONTROL All]** ユニットにリンクしないでください。

### 配信ログの確認 {#checking-logs}

メッセージの送信後にターゲットから削除されたプロファイルを確認するには、をチェックし **[!UICONTROL Delivery logs]**&#x200B;ます。 配信ログとそのアクセス方法について詳しくは、 [この節を参照してください](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

* タブで、抽出されたプロファイルと除外された要素を確認でき **[!UICONTROL Sending logs]** ます。 彼らは **[!UICONTROL Ignored]** 状態があり、失敗の理由 **[!UICONTROL Control group]** がある。

   ![](assets/control-group-sending-logs.png)

* また、 **[!UICONTROL Exclusion causes]** タブをチェックして、配信に含まれていないプロファイルの数を確認することもできます。

   ![](assets/control-group-exclusion-causes.png)

### コントロール母集団ログの使用 {#using-logs}

配信が送信されたら、配信ログを使用して、メッセージを受信しなかったプロファイルをフィルターできます。 次の手順に従います。

1. ワークフローの作成. ワークフローを作成する詳細な手順については、[ワークフローの作成](../../automating/using/building-a-workflow.md)の節を参照してください。
1. /で、 **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**[](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップします。
1. タブで、とと **[!UICONTROL Properties]** して **[!UICONTROL Delivery logs]** を設定 **[!UICONTROL Resource]** し **[!UICONTROL Profile]****[!UICONTROL Targeting dimension]**&#x200B;ます。

   ![](assets/control-group-delivery-properties.png)

1. 「**[!UICONTROL Target]**」タブで、「**[!UICONTROL Delivery logs]**」をクリックします。
1. ドラッグ&amp;ドロップ **[!UICONTROL Status]** し、フィルター条件 **[!UICONTROL Ignored]** として選択します。

   ![](assets/control-group-status-ignored.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

1. 引き続き **[!UICONTROL Target]** タブで、ドラッグ&amp;ドロップ **[!UICONTROL Nature of failure]** し、フィルター条件 **[!UICONTROL Control group]** として選択します。

   ![](assets/control-group-nature-of-failure.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/control-group-delivery-target.png)

次に、「 **抽出ファイル** 」アクティビティの後に「ファイルの **転送** 」アクティビティが続く場合など、ログデータをエクスポートします。 これにより、コントロール母集団と比較して効果的なターゲットに対するキャンペーンの結果を、独自のレポートツールで分析できます。 For more on exporting logs, see [this section](../../automating/using/exporting-logs.md).

### コントロール母集団のターゲット設定 {#targeting-control-group}

メッセージを受信しなかったプロファイルに基づいてターゲティングを行う場合は、配信ログも使用できます。 次の手順に従います。

1. ワークフローの作成. ワークフローを作成する詳細な手順については、[ワークフローの作成](../../automating/using/building-a-workflow.md)の節を参照してください。
1. >で、最初の **[!UICONTROL Activities]** クエリ **[!UICONTROL Targeting]**[](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップします。
1. タブで、リ **[!UICONTROL Properties]** ソースが「および」として選択されているこ **[!UICONTROL Profile]** とを確認し **[!UICONTROL Resource]****[!UICONTROL Targeting dimension]**&#x200B;ます。

   ![](assets/control-group-delivery-properties-profile.png)

1. タブで、展開してドラッグ&amp;ドロップ **[!UICONTROL Target]** し **[!UICONTROL Delivery]****[!UICONTROL Delivery logs]**&#x200B;ます。

   ![](assets/control-group-query-delivery-logs.png)

1. ウィン **[!UICONTROL Add a rule]** ドウで、ドラッグ&amp;ドロップし **[!UICONTROL Delivery]**&#x200B;ます。

   ![](assets/control-group-rule-delivery.png)

1. フィルター条件として送信した電子メールを選択します。 「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/control-group-email-sent.png)

1. ウィンドウに戻り、ドラッグ&amp;ドロップ **[!UICONTROL Add a rule]** して、フィルター条件 **[!UICONTROL Status]****[!UICONTROL Ignored]** として選択します。 「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/control-group-status-ignored.png)

1. ドラッグ&amp;ドロップ **[!UICONTROL Nature of failure]** し、フィルター条件 **[!UICONTROL Control group]** として選択します。 「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/control-group-nature-of-failure.png)

1. 条件がすべて、 **AND** Boolean演算子で整列していることを確認します。

   ![](assets/control-group-delivery-logs-conditions.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

プロファイルがコントロール母集団の一部であったため、最初のメッセージを受信しなかったをターゲットし、別の電子メールを送信できるようになりました。

同じワークフローで、電子メールを受信したプロファイルにターゲットし、別のメッセージを送信するための別のクエリを作成することもできます。

![](assets/control-group-targeted-by-delivery.png)