---
title: セグメント化
description: セグメント化アクティビティを使用すると、ワークフローの前のページに配置されたアクティビティによって計算された訪問者から、1つまたは複数のセグメントを作成できます。
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 740de9fe4666bf12fc97cfa434414668d9394504
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 0%

---


# セグメント化{#segmentation}

## 説明 {#description}

![](assets/segmentation.png)

この **[!UICONTROL Segmentation]** アクティビティでは、ワークフローの前のバージョンに配置されたアクティビティによって計算された訪問者から、1つまたは複数のセグメントを作成できます。 アクティビティの最後に、1つのトランジションまたは異なるトランジションで処理できます。

>[!NOTE]
>
>デフォルトでは、インバウンド母集団のメンバーは1つのセグメントにのみ属することができます。 フィルターは、アクティビティ内のセグメントの順序に従って適用されます。

## 使用状況 {#context-of-use}

通常、 **[!UICONTROL Segmentation]** アクティビティは、アクティビティ(クエリ、交差点、和集合、除外など)をターゲット化した後に配置されます。 を使用して、セグメントの形成基準となる標準母集団を定義する必要があります。

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Segmentation]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. タブで、セグメ **[!UICONTROL General]** ント化を実行 **[!UICONTROL Resource type]** する必要がある対象を選択します。

   * **[!UICONTROL Database resource]** データベースに既に存在するデータに対してセグメント化が実行される場合。 セグメント化するデータ **[!UICONTROL Filtering dimension]** に応じて、を選択します。 デフォルトでは、 **プロファイルでセグメントが実行されます**。
   * **[!UICONTROL Temporary resource]** ワークフローの一時データでセグメント化が実行される場合： セグメント化するデータ **[!UICONTROL Targeted set]** を含むを選択します。 この使用例は、ファイルのインポート後、またはデータベース内のデータがリンチされた場合に発生する可能性があります。

1. 使用するアウトバウンドトランジションの種類を選択します。

   * **[!UICONTROL Generate one transition per segment]**: アクティビティの最後に、設定済みのセグメントごとに1つのアウトバウンドトランジションが追加されます。
   * **[!UICONTROL Generate all segments in one transition]**: 設定済みのすべてのセグメントは、1つのアウトバウンドトランジションに再グループ化されます。 トランジションのラベルを指定します。 各セグメントのメンバーは、割り当てられたセグメントコードを保持します。

1. ![](assets/add_darkgrey-24px.png) または **[!UICONTROL Add an element]** ボタンを使用して、次の標準プロパティを指定し追加てセグメントを作成します。

   * **[!UICONTROL Do not activate the transition if the population is empty]**: セグメントは、データが取得された場合にのみ有効になります。
   * **[!UICONTROL Filter initial population (query)]**: このセグメントの母集団をフィルターできます。
   * **[!UICONTROL Limit segment population]**: セグメントのサイズを制限できます。
   * **[!UICONTROL Filter and limit segment population]**: セグメント母集団をフィルターしてサイズを制限できます。
   * **[!UICONTROL Label]**: セグメントラベル。
   * **[!UICONTROL Segment code]**: コードをセグメントの母集団に割り当てます。このセグメントコードは、標準の式変数とイベント変数を使用してパーソナライズできます(イベント変数を使用したアクティビティの [カスタマイズを参照](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。
   * **[!UICONTROL Exclude segment from population]**: 指定したセグメントをアクティビティのアウトバウンド訪問者から除外できます。 このオプションは、この **[!UICONTROL Generate all segments in the same transition]** オプションが選択されている場合にのみ使用できます。
   ![](assets/wkf_segment_new_segment.png)

1. セグメントの詳細表示を開き、後者の設定オプションにアクセスします。 これを行うには、アクティビティのセグメントリストの関連するボックスをオンにして、を選択し ![](assets/wkf_segment_parameters_24px.png)ます。
1. 初期母集団をフィルターするオプションがオンになっている場合は、 **[!UICONTROL Filter]** タブを開き、セグメントの母集団を指定します。 フィルターは、手順4で選択したフィルタリングディメンションに基づきます。 母集団のフィルタリングの詳細については、「 [クエリの編集](../../automating/using/editing-queries.md) 」の節を参照してください。

   一時的なリソースに対してセグメント化が実行された場合、このタブでは母集団の数とプレビューは使用できません。

1. セグメントサイズを制限するオプションがオンになっている場合は、 **[!UICONTROL Limitation]** タブを開きます。

   最初に、使用す **[!UICONTROL Type of limit]** る

   * **[!UICONTROL Random sampling]**: 必要に応じて、 **[!UICONTROL Filter]** タブの設定を考慮して、セグメントの母集団がランダムに選択されます。
   * **[!UICONTROL Ordered sampling]**: セグメントの母集団は、順序に従って選択されます。 その結果、考慮する列と適用する並べ替えの種類を指定する必要があります。 例えば、 **Age** ( **[!UICONTROL Descending sort]** 年齢)フィールドを並べ替え列として選択し、制限値を100に設定した場合、最も年長の上位100人のプロファイルのみが保持されます。
   次に、セグメントのサイズ **[!UICONTROL Limit]** を指定します。

   * **[!UICONTROL Size (as a % of the initial population)]**: アクティビティの初期母集団に対する割合を使用して、セグメントのサイズを指定します。
   * **[!UICONTROL Maximum size]**: セグメント母集団の最大メンバー数を指定します。
   * **[!UICONTROL By data grouping]**: インバウンド母集団の特定のフィールドの値に従って、セグメント母集団を制限できます。 グループ化するフィールドを選択し、使用する値を指定します。
   * **[!UICONTROL By data grouping (as a %)]**: 割合を使用して、特定の受信母集団フィールドの値に従ってセグメント母集団を制限できます。 グループ化を適用するフィールドを選択し、使用する値を指定します。

      >[!NOTE]
      >
      >値ごとに異なる制限を使用できます。 例えば、フィールドのグループを指定して、メンバーを含む母集団を10人に制限し、メンバーを含む母集団を30人に制限することが **[!UICONTROL Gender]****[!UICONTROL Male]****[!UICONTROL Female]** できます。 複数のデータグループ化フィールドを使用する場合は、すべてのグループのサイズを同じにする必要があります。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. セグメントの設定を確認します。
1. 手順6 ～ 10追加を繰り返して、必要な数のセグメントを作成します。
1. 必要に応じて、 **[!UICONTROL Advanced options]** タブのパラメーターを編集します。

   * 受信訪問者のメンバーを同時に複数のセグメントに属させる場合は、この **[!UICONTROL Enable overlapping of outbound populations]** オプションを選択します。 アクティビティのアウトバウンド母集団がインバウンド母集団を超える可能性があります。
   * 受信母集団に保持するセグメントコードが既に割り当てられている場合は、この **[!UICONTROL Concatenate the code of each segment]** オプションを選択します。 アクティビティで指定されたセグメントコードが、最初のセグメントコードに追加されます。
   * 残りの訪問者を活用する場合は、この **[!UICONTROL Generate complement]** オプションを選択します。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、データベースプロファイルを年齢グループに従って分類する例です。 このワークフローの目的は、各年齢層に対して特定の電子メールを送信することです。 このワークフローがテストキャンペーンの一部であることを考慮すると、制限があり、同時に表示するオーディエンスを使用するために、各セグメントには最大100個のプロファイルしか含めることができません。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* ワークフローの実行日を指定する **[!UICONTROL Scheduler]** アクティビティです。 Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* 誕生日と電子メールアドレスが入力された人のターゲットプロファイルへの **[!UICONTROL Query]** アクティビティです。 Refer to the [Query](../../automating/using/query.md) section.
* 異なるアウトバウンドトランジションに分割された3つのセグメントを作成する **[!UICONTROL Segmentation]** アクティビティ: 18-25歳、26-32歳、32歳以上のプロファイル。 セグメントは、次のパラメーターに従って定義します。

   ![](assets/wkf_segment_example_3.png)

   * セグメントの年齢グループを定義する年齢に関するフィルター

      ![](assets/wkf_segment_new_segment.png)

   * 制限値100にリンクされた **[!UICONTROL Random sampling]** 種類 **[!UICONTROL Maximum size]** 制限

      ![](assets/wkf_segment_example_1.png)

* セグメントごとの **[!UICONTROL Email delivery]** アクティビティ。 Refer to the [Email delivery](../../automating/using/email-delivery.md) section.

