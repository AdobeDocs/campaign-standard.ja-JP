---
title: オーディエンスの閲覧
description: オーディエンスを読み取りアクティビティを使用すると、追加のフィルター条件を適用して、既存のオーディエンスを取得し、それを絞り込むことができます。
page-status-flag: 非活性化の
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲティング活動
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# オーディエンスの閲覧{#read-audience}

## 説明 {#description}

![](assets/prefill.png)

アクティビティ **[!UICONTROL Read audience]** を使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。

## 使用状況 {#context-of-use}

アクテ **[!UICONTROL Read audience]** ィビティは、既存のオーディエンスの選択 **[!UICONTROL Query]** のみが必要な場合に備えて設計された、アクティビティのよりシンプルなバージョンです。

## 設定 {#configuration}

1. アクティビティをワ **[!UICONTROL Read audience]** ークフローにドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. タブから取得するオーディエンスを選択し **[!UICONTROL Properties]** ます。

   次のタイプのオーディエンスを取得できます。 **[!UICONTROL List]**、 **[!UICONTROL Query]**、 **[!UICONTROL File]** 、 **[!UICONTROL Experience Cloud]**、 オーディエンスタイプについて詳しくは、オーディエンスのドキュメントを参 [照して](../../audiences/using/about-audiences.md) ください。

   このオ **[!UICONTROL Use a dynamic audience]** プションでは、ワークフローのイベント変数に基づいてターゲット設定するオーディエンスの名前を定義できます。 詳しくは、「イベント変数を使用したアクティビティ [のカスタマイズ」の節を参照してくださ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) い。

   ![](assets/readaudience_activity1.png)

1. 選択したオーディエンスに追加のフィルターを適用する場合は、アクティビティのタブを使用し **[!UICONTROL Source filtering]** て条件を追加します。

   フィルタリング条件の作成の詳細については、『クエリの作成 [](../../automating/using/editing-queries.md#creating-queries) 』ドキュメントを参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例：ファイルオーディエンスとデータベースとの調整 {#example--reconcile-a-file-audience-with-the-database}

この例では、アクティビティを使用して、フ **[!UICONTROL Read audience]** ァイルのインポートから直接作成されたオーディエンスを調整する方法を示します。

ファイルの読み込みを実行する際に、オーディエンスにそのコンテンツを直接保存できます。 このオーディエンスはファイルオーディエンスで、そのデータはデータベースリソースにリンクされていません。

読み込みワークフローは、次のように設計されています。

![](assets/readaudience_activity_example3.png)

* ファイル [の読み込みアクティビティは](../../automating/using/load-file.md) 、外部ツールから抽出されたプロファイルデータを含むファイルをアップロードします。

   次に例を示します。

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* オーディエ [ンスを保存アクティビティは](../../automating/using/save-audience.md) 、受信データをオーディエンスとして保存します。 データはまだ調整されていないので、オーディエンスはファイルオーディエンスで、そのデータはまだプロファイルデータとして認識されません。

調整ワークフローは次のように設計されています。

![](assets/readaudience_activity_example2.png)

* アクティビティ **[!UICONTROL Read audience]** は、読み込みワークフローで作成されたファイルオーディエンスをアップロードします。 オーディエンスデータは、まだAdobe Campaignデータベースと調整されていません。
* 調整ア [クティビティは](../../automating/using/reconciliation.md) 、受信データをタブでプロファイルとして識別 **[!UICONTROL Identification]** します。 例えば、電子メールフィールドを調 **整条件として** 使用する場合などです。
* 「 [Update data](../../automating/using/update-data.md) 」アクティビティは、受信データを使用してデータベースのプロファイルリソースを挿入し、更新します。 データは既にプロファイルとして識別されているので、このオプションを **[!UICONTROL Directly using the targeting dimension]** 選択し、アクティビティ **[!UICONTROL Profiles]** のタ **[!UICONTROL Identification]** ブでを選択できます。 その後は、「分類」タブで更新する必要のあるフィールドのリストを追加するだけで済みます。

## 例：2つの洗練されたオーディエンスに対する和集合 {#example--union-on-two-refined-audiences}

この例で定義したワークフローは、2つのアクティビティの和集合を示し **[!UICONTROL Read audience]** ています。 このワークフローの目的は、18歳から30歳のゴールドメンバーまたはシルバーメンバーに電子メールを送信することです。

ゴールドメンバーとシルバーメンバーを追跡するために、システム内に特定のオーディエンスが既に作成されています。

ワークフローは次のように設計されています。

![](assets/readaudience_activity_example1.png)

* ゴールドメン **[!UICONTROL Read audience]** バーオーディエンスを取得する最初のアクティビティで、18 ～ 30年のプロファイルのみを選択して、オーディエンスを絞り込みます。
* シルバーメ **[!UICONTROL Read audience]** ンバーのオーディエンスを取得し、18 ～ 30年のプロファイルのみを選択して絞り込む2番目のアクティビティです。
* 両方の **[!UICONTROL Union]** アクティビティの訪問者を1つの最終訪 **[!UICONTROL Read audiences]** 問者に結合するアクティビティ。
* アクテ **[!UICONTROL Email delivery]** ィビティからの訪問者に電子メールを送信するアクティビティ **[!UICONTROL Union]** です。

