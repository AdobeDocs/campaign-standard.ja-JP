---
title: オーディエンスの読み取り
seo-title: オーディエンスの読み取り
description: オーディエンスの読み取り
seo-description: オーディエンスの読み取りアクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。
page-status-flag: 常にアクティブ化されていない
uuid: 58c54e71- f4a7-4ae9-80a3-33c379ab1db9
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: 674684e5-8830-4d2f- ba97-59ed4ba7422f
context-tags: readAudience、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Read audience{#read-audience}

## 説明 {#description}

![](assets/prefill.png)

**[!UICONTROL Read audience]** このアクティビティにより、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。

## Context of use {#context-of-use}

**[!UICONTROL Read audience]** アクティビティは、既存のオーディエンスを選択するだけのケース向けに設計された、シンプルなバージョン **[!UICONTROL Query]** のアクティビティです。

## Configuration {#configuration}

1. Drop a **[!UICONTROL Read audience]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the audience you want to retrieve from the **[!UICONTROL Properties]** tab.

   You can retrieve audiences of the following types: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** and **[!UICONTROL Experience Cloud]**. For more information on audience types, refer to the [Audiences](../../audiences/using/about-audiences.md) documentation.

   **[!UICONTROL Use a dynamic audience]** このオプションを使用すると、ワークフローのイベント変数に基づいてターゲットにするオーディエンスの名前を定義できます。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

   ![](assets/readaudience_activity1.png)

1. If you want to apply additional filtering to the selected audience, add conditions via the **[!UICONTROL Source filtering]** tab of the activity.

   For more information about creating filtering conditions, refer to the [Creating queries](../../automating/using/editing-queries.md#creating-queries) documentation.

1. アクティビティの設定を確認し、ワークフローを保存します。

## Example: Reconcile a File audience with the database {#example--reconcile-a-file-audience-with-the-database}

This example shows how to use the **[!UICONTROL Read audience]** activity to reconcile an audience directly created from a file import.

ファイルの読み込みを実行すると、オーディエンスに直接コンテンツを保存できます。このオーディエンスはファイルのオーディエンスであり、そのデータはデータベースリソースにリンクされていません。

インポートワークフローは次のように設計されています。

![](assets/readaudience_activity_example3.png)

* [読み込みファイル](../../automating/using/load-file.md) アクティビティは、外部ツールから抽出されたプロファイルデータを含むファイルをアップロードします。

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

* [「保存するオーディエンス](../../automating/using/save-audience.md) 」アクティビティは、受信データをオーディエンスとして保存します。データがまだ紐付けされていない場合、オーディエンスはファイルのオーディエンスであり、そのデータはプロファイルデータとして認識されません。

紐付けワークフローは次のように設計されています。

![](assets/readaudience_activity_example2.png)

* **[!UICONTROL Read audience]** アクティビティは、インポートワークフローで作成されたファイルオーディエンスをアップロードします。オーディエンスデータは、まだAdobe Campaignデータベースと調整されません。
* [紐付け](../../automating/using/reconciliation.md) アクティビティは **[!UICONTROL Identification]** 、そのタブを介して、受信データをプロファイルとして識別します。For example by using the **email** field as reconciliation criteria.
* [更新データ](../../automating/using/update-data.md) アクティビティは、受信データを使用してデータベースのプロファイルリソースを挿入および更新します。As the data is already identified as profiles, you can select the **[!UICONTROL Directly using the targeting dimension]** option and select **[!UICONTROL Profiles]** in the **[!UICONTROL Identification]** tab of the activity. 次に、タブで更新する必要があるフィールドのリストを追加します。

## Example: Union on two refined audiences {#example--union-on-two-refined-audiences}

The workflow defined in this example shows the union of two **[!UICONTROL Read audience]** activities. このワークフローの目的は、18才から30才までの金または銀の会員に電子メールを送信することです。

特定のオーディエンスは、ゴールドおよびシルバーのメンバーを追跡するためにシステム内で既に作成されています。

ワークフローは次のように設計されています。

![](assets/readaudience_activity_example1.png)

* A first **[!UICONTROL Read audience]** activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* A second **[!UICONTROL Read audience]** activity that retrieves the Silver members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* **[!UICONTROL Union]****[!UICONTROL Read audiences]** 両方のアクティビティから1人の最終母集団に訪問者を同化させるアクティビティ。
* An **[!UICONTROL Email delivery]** activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.

