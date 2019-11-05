---
title: セグメント化
description: セグメント化アクティビティを使用すると、ワークフローの前の方に配置されたアクティビティによって計算された訪問者から1つまたは複数のセグメントを作成できます。
page-status-flag: 非活性化の
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲティング活動
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# セグメント化{#segmentation}

## 説明 {#description}

![](assets/segmentation.png)

アクティビティ **[!UICONTROL Segmentation]** を使用すると、ワークフローの前の方に配置されたアクティビティによって計算された訪問者から、1つまたは複数のセグメントを作成できます。 アクティビティの最後に、1つのトランジションまたは異なるトランジションで処理できます。

>[!NOTE]
>
>デフォルトでは、インバウンド母集団のメンバーは1つのセグメントにのみ属することができます。 フィルターは、アクティビティ内のセグメントの順序に従って適用されます。

## 使用状況 {#context-of-use}

アクテ **[!UICONTROL Segmentation]** ィビティは、通常、ターゲティングアクティビティ（クエリ、交差、ユニオン、除外など）の後に配置されます。を使用して、セグメントの形成基準となる標準母集団を定義します。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Segmentation]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. セグメン **[!UICONTROL Resource type]** トを実行する対象を選択します。

   * **[!UICONTROL Database resource]** データベースに既に存在するデータに対してセグメント化が実行される場合。 セグメント **[!UICONTROL Filtering dimension]** 化するデータに応じて、を選択します。 デフォルトでは、プロファイルでセグメント化が実行さ **れます**。
   * **[!UICONTROL Temporary resource]** ワークフローの一時データでセグメント化が実行される場合：セグメント化 **[!UICONTROL Targeted set]** するデータを含むデータを選択します。 この使用例は、ファイルのインポート後、またはデータベース内のデータがリンチされた場合に発生する可能性があります。

1. 使用するアウトバウンド移行の種類を選択します。

   * **[!UICONTROL Generate one transition per segment]**:アクティビティの最後に、設定済みの各セグメントに対して1つのアウトバウンド遷移が追加されます。
   * **[!UICONTROL Generate all segments in one transition]**:設定済みのセグメントはすべて、1つのアウトバウンドトランジションに再グループ化されます。 摺り付けラベルを指定 各セグメントのメンバーは、割り当てられたセグメントコードを保持します。

1. またはボタンを使用してセグメントを ![](assets/add_darkgrey-24px.png) 追加し、 **[!UICONTROL Add an element]** 次の標準プロパティを指定します。

   * **[!UICONTROL Do not activate the transition if the population is empty]**:セグメントは、データが取得された場合にのみ有効になります。
   * **[!UICONTROL Filter initial population (query)]**:このセグメントの母集団をフィルターできます。
   * **[!UICONTROL Limit segment population]**:セグメントサイズを制限できます。
   * **[!UICONTROL Filter and limit segment population]**:セグメント母集団をフィルターし、サイズを制限できます。
   * **[!UICONTROL Label]**:セグメントラベル。
   * **[!UICONTROL Segment code]**:コードをセグメント母集団に割り当てます。セグメントコードは、標準の式とイベント変数を使用してパーソナライズできます(イベント変数を使用したア [クティビティのカスタマイズ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。
   * **[!UICONTROL Exclude segment from population]**:アクティビティのアウトバウンド母集団から指定したセグメントを除外できます。 このオプションは、このオプションが選択されている場合に **[!UICONTROL Generate all segments in the same transition]** のみ使用できます。
   ![](assets/wkf_segment_new_segment.png)

1. セグメントの詳細ビューを開き、後者の設定オプションにアクセスします。 これを行うには、アクティビティのセグメントリストで該当するボックスを選択し、を選択しま ![](assets/wkf_segment_parameters_24px.png)す。
1. 初期訪問者をフィルターするオプションがオンになっている場合は、タブを開 **[!UICONTROL Filter]** いて、セグメントの訪問者を指定します。 フィルターは、手順4で選択したフィルターディメンションに基づいています。 母集団フィル [タリングの詳細については](../../automating/using/editing-queries.md) 、「クエリーの編集」の節を参照してください。

   一時的なリソースに対してセグメント化を実行した場合、このタブでは母集団の数とプレビューは使用できません。

1. セグメントサイズを制限するオプションがオンになっている場合は、タブを開 **[!UICONTROL Limitation]** きます。

   まず、使用す **[!UICONTROL Type of limit]** るを選択します。

   * **[!UICONTROL Random sampling]**:必要に応じて、タブの設定を考慮して、セグメントの母集団がラン **[!UICONTROL Filter]** ダムに選択されます。
   * **[!UICONTROL Ordered sampling]**:セグメントの母集団は順序に従って選択されます。 その結果、考慮する列と適用する並べ替えの種類を指定する必要があります。 例えば、「 **Age****[!UICONTROL Descending sort]** 」フィールドを並べ替え列として選択し、制限値を100に設定した場合、最も古い人の上位100人のプロファイルのみが保持されます。
   次に、セグメントのサ **[!UICONTROL Limit]** イズを指定します。

   * **[!UICONTROL Size (as a % of the initial population)]**:アクティビティの初期母集団に対する割合を使用して、セグメントのサイズを指定します。
   * **[!UICONTROL Maximum size]**:セグメント母集団の最大メンバー数を指定します。
   * **[!UICONTROL By data grouping]**:インバウンド母集団の特定のフィールドの値に従って、セグメント母集団を制限できます。 グループ化するフィールドを選択し、使用する値を指定します。
   * **[!UICONTROL By data grouping (as a %)]**:割合を使用して、特定のインバウンド母集団フィールドの値に従ってセグメント母集団を制限できます。 グループ化を適用するフィールドを選択し、使用する値を指定します。

      >[!NOTE]
      >
      >各値に異なる制限を使用できます。 例えば、フィールドのグループを指定し、メン **[!UICONTROL Gender]** バーを持つ母集団を10人に、メ **[!UICONTROL Male]** ンバーを持つ母集団を30人に **[!UICONTROL Female]** 制限できます。 複数のデータグループ化フィールドを使用する場合は、すべてのグループ化のサイズが同じである必要があります。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. セグメントの設定を確認します。
1. この手順の手順6 ～ 10を繰り返して、必要なだけセグメントを追加します。
1. 必要に応じて、タブのパラメーターを編集 **[!UICONTROL Advanced options]** します。

   * インバウンド **[!UICONTROL Enable overlapping of outbound populations]** 母集団のメンバーを同時に複数のセグメントに属させる場合は、このオプションを選択します。 アクティビティのアウトバウンド母集団がインバウンド母集団を超える可能性があります。
   * 受入母集団 **[!UICONTROL Concatenate the code of each segment]** に、保持するセグメントコードが既に割り当てられている場合は、このオプションを選択します。 アクティビティで指定されたセグメントコードが、最初のセグメントコードに追加されます。
   * 残りの人口 **[!UICONTROL Generate complement]** を活用する場合は、このオプションを選択します。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、年齢グループに従ったデータベースプロファイルのセグメント化を示しています。 このワークフローの目的は、各年齢層に対して特定の電子メールを送信することです。 このワークフローがテストキャンペーンの一部であることを考慮すると、各セグメントには最大100個のプロファイルしか含めることができず、これらのプロファイルはランダムに選択され、同時に制限され、代表的なオーディエンスを使用できます。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* ワーク **[!UICONTROL Scheduler]** フローの実行日を指定するアクティビティ。 Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* 誕生日 **[!UICONTROL Query]** と電子メールアドレスが入力された人のプロファイルをターゲットにするアクティビティ。 「クエリー」の節を参 [照してください](../../automating/using/query.md) 。
* 異なるア **[!UICONTROL Segmentation]** ウトバウンド遷移に分割された3つのセグメントを作成するアクティビティ：18～25歳、26～32歳、32歳以上のプロフィール。 セグメントは、次のパラメーターに従って定義されます。

   ![](assets/wkf_segment_example_3.png)

   * セグメントの年齢グループを定義する年齢に関するフィルター

      ![](assets/wkf_segment_new_segment.png)

   * 制限 **[!UICONTROL Random sampling]** 値100にリンクされたタ **[!UICONTROL Maximum size]** イプ制限

      ![](assets/wkf_segment_example_1.png)

* セグメント **[!UICONTROL Email delivery]** ごとのアクティビティ。 「電子メール配信 [」を参照](../../automating/using/email-delivery.md) 。

