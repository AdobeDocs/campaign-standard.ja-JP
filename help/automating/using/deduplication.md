---
title: 重複除外
seo-title: 重複除外
description: 重複除外
seo-description: 重複除外アクティビティを使用すると、受信アクティビティの結果の重複を削除できます。
page-status-flag: 常にアクティブ化されていない
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Deduplication{#deduplication}

## 説明 {#description}

![](assets/deduplication.png)

**[!UICONTROL Deduplication]** アクティビティでは、受信アクティビティの結果の重複を削除できます。

## Context of use {#context-of-use}

**[!UICONTROL Deduplication]** アクティビティは通常、ターゲットアクティビティの後、またはファイルのインポート後、ターゲットデータの使用を許可するアクティビティの前に使用されます。

重複除外の間、インバウンドトランジションは個別に処理されます。例えば、クエリ1の結果にプロファイル"A"があり、クエリ2の結果にも含まれている場合、重複は除外されません。

したがって、重複排除には1つの受信移行のみがあることをお勧めします。これを行うには、ユニオンアクティビティ、交差アクティビティなどのターゲット設定ニーズに対応するアクティビティを使用して、異なるクエリを組み合わせることができます。次に例を示します。

![](assets/dedup_bonnepratique.png)

## Configuration {#configuration}

重複除外アクティビティを設定するには、ラベル、メソッドおよび重複除外条件およびその結果に関連するオプションを入力する必要があります。

1. Drag and drop a **[!UICONTROL Deduplication]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   ![](assets/deduplication_1.png)

1. Select the **[!UICONTROL Resource type]** on which the deduplication has to be carried out:

   * **[!UICONTROL Database resource]** データベースに既に存在するデータで重複除外が実行されている場合。Select the **[!UICONTROL Filtering dimension]** and the **[!UICONTROL Targeting dimension]**, depending on the data that you want to deduplicate. By default, deduplication is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** ワークフローの一時データで重複除外が実行された場合:重複除外するデータ **[!UICONTROL Targeted set]** を選択します。この使用例は、ファイルを読み込んだ後、またはデータベース内のデータが拡張された（例えば、セグメントコードを含む）場合に発生します。

1. Select the **[!UICONTROL Number of unique records to keep]**. このフィールドのデフォルト値は1です。値0を指定すると、すべての複製を保持できます。

   例えば、レコードAとBがレコードYの重複と見なされ、レコードCがレコードZの複製と見なされるとします。

   * フィールドの値が1の場合:YレコードとZレコードのみが保持されます。
   * フィールドの値が0の場合:すべてのレコードが保持されます。
   * フィールドの値が2の場合:records CおよびZは保持され、A、BおよびYの2つのレコードは、偶然にわたって保持されます。また、後で選択した重複除外方法によっても保持されます。

1. Define the **[!UICONTROL Duplicate identification]** criteria by adding conditions in the list provided. 同じ値を持つフィールドまたは式を指定して、複製を識別します。電子メールアドレス、名、姓など条件の順序によって、最初に処理するように指定できます。
1. In the drop-down list, select the **[!UICONTROL Deduplication method]** to use:

   * **[!UICONTROL Choose for me]**:を指定すると、重複しないようにレコードがランダムに選択されます。
   * **[!UICONTROL Following a list of values]**:を使用すると、1つ以上のフィールドに対して値の優先度を定義できます。値を定義するには、フィールドを選択するか、式を作成して、適切なテーブルに値を追加します。To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**:これにより、選択した式の値が優先度として空でないレコードを保持できます。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**:これにより、入力した式の値が最小または最大のレコードを保持できます。

      ![](assets/deduplication_4.png)

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. アクティビティの設定を確認し、ワークフローを保存します。

## Example 1: Identifying duplicates before a delivery {#example-1--identifying-duplicates-before-a-delivery}

次の例は、電子メールを送信する前にターゲットの複製を除外できる重複排除を示しています。つまり、同じプロファイルに何度も通信を送信することは避けてください。

ワークフローは次のようになります。

![](assets/deduplication_example_workflow.png)

* A **[!UICONTROL Query]** which allows you to define the target of the email. このワークフローでは、クライアントデータベースにある18~25のすべてのプロファイルを、1年以上の間ターゲット設定します。

   ![](assets/deduplication_example_query.png)

* **[!UICONTROL Deduplication]** 前のクエリからの重複を識別できるアクティビティ。この例では、重複するレコードごとにレコードが1つしか保存されません。重複は電子メールアドレスを使用して識別されます。つまり、ターゲット設定に含める電子メールアドレスごとに1回だけ電子メール配信を送信できます。

   The deduplication method selected is **[!UICONTROL Non-empty value]**. This allows you to ensure that amongst the records kept in case of duplicates, priority is given to those in which the **First name** has been provided. これにより、電子メールコンテンツのパーソナライゼーションフィールドで名が使用されると、より整合性が高くなります。

   さらに、重複を保持し、それらの複製をリストできるように追加のトランジションが追加されました。

   ![](assets/deduplication_example_dedup.png)

* An **[!UICONTROL Email delivery]** placed after the main outbound transition of the deduplication. The configuration for email deliveries is detailed in the [Email delivery](../../automating/using/email-delivery.md) section.
* A **[!UICONTROL Save audience]** activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. このオーディエンスを再利用して、各電子メール配信から直接メンバーを除外できます。

## Example 2: Deduplicating the data from an imported file {#example-2--deduplicating-the-data-from-an-imported-file}

この例では、データをデータベースに読み込む前に読み込んだファイルの重複を除外する方法を示します。この手順により、データベースに読み込まれたデータの質が向上します。

ワークフローは次のようになります。

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a **[!UICONTROL Load file]** activity. この例では、インポートされたファイルは. csv形式で、10個のプロファイルが含まれています。

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   このファイルは、列の形式を検出して定義するサンプルファイルとしても使用できます。**[!UICONTROL Column definition]** タブから、インポートしたファイルの各列が正しく構成されていることを確認します。

   ![](assets/deduplication_example2_fileloading.png)

* **[!UICONTROL Deduplication]** アクティビティ。重複除外は、ファイルを読み込んだ後、データベースにデータを挿入する前に直接実行されます。It should therefore be based on the **[!UICONTROL Temporary resource]** from the **[!UICONTROL Load file]** activity.

   この例では、ファイルに含まれる一意の電子メールアドレスごとに1つのエントリを保存します。Duplicate identification is therefore carried out on the **email** column of the temporary resource. その場合、ファイルに2つの電子メールアドレスが表示されます。したがって、2行は重複と見なされます。

   ![](assets/deduplication_example2_dedup.png)

* An **[!UICONTROL Update data]** activity allows you to insert the data kept from the deduplication process into the database. これは、インポートされたデータがプロファイルディメンションに属するものとして識別される場合にのみ、データが更新されます。

   Here, we would like to **[!UICONTROL Insert only]** the profiles that do not already exist in the database. We are going to do this by using the file's email column and the email field from the **Profile** dimension as the reconciliation key.

   ![](assets/deduplication_example2_writer1.png)

   Specify the mappings between the file's columns from which you want to insert the data and the database fields from the **[!UICONTROL Fields to update]** tab.

   ![](assets/deduplication_example2_writer2.png)

次に、ワークフローを開始します。重複排除プロセスから保存されたレコードが、データベース内のプロファイルに追加されます。
