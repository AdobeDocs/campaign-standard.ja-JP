---
title: 紐付け
description: 調整アクティビティでは、識別できないデータを既存のリソースにリンクできます。
page-status-flag: 非活性化の
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データ管理活動
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: 調整，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 紐付け{#reconciliation}

## 説明 {#description}

![](assets/reconciliation.png)

このアクテ **[!UICONTROL Reconciliation]** ィビティを使用すると、識別できないデータを既存のリソースにリンクできます。

## 使用状況 {#context-of-use}

アクティビティ **[!UICONTROL Reconciliation]** は基本的にデータ管理の目的で使用され、次の2つの異なる使用例を意味します。

* リレーションの追加：タブを使 **[!UICONTROL Links]** 用して、受信データと他の複数のAdobe Campaignデータベースディメンションとの間にリンクを追加できます。

   例えば、購入データを含むファイルには、購入した製品と購入者を識別する情報を含めることもできます。 したがって、(購入以外の ****)次の2つの追加ディメンションがファイルデータに関係します。「 **Products** and **Profiles** 」ディメンション。 次に、これらと **Purchases** （購入）ディメンションの間にリレーションを作成する必要があります（次の例を参照）。

   関係を定義する際、リンクディメンションの外部キーを参照するために、インバウンドデータに列が追加されます。

   >[!NOTE]
   >
   >この操作は、リンクされたディメンションのデータが既にデータベースに存在することを意味します。 例えば、購入した製品を示す購入ファイルをインポートする場合、その製品とクライアントがデータベースに既に存在している必要があります。

* データID:タブを使 **[!UICONTROL Identification]** 用すると、受信データをAdobe Campaignデータベース内の既存のディメンションの列に単純にリンクできます。 アクティビティの後、データは定義済みのディメンションに属していると識別されます。

   例えば、オーディエンスの保存、データベースの更新などを実行できます。

例えば、非標準 **[!UICONTROL Reconciliation]** のデータをデータベースにインポートする目的で、データのロードアクティビティの後にアクティビティを配置できます。

## 設定 {#configuration}

1. Adobe Campaignから直接ターゲットディメ **[!UICONTROL Reconciliation]** ンションを持たない訪問者を含むトランジションに従って、アクティビティをワークフローにドラッグ&amp;ドロップします。 詳しくは、ディメンションとリソースのターゲ [ット設定を参照してください](../../automating/using/query.md#targeting-dimensions-and-resources)。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 受信データと他のデータベースディメンションの間のリンクを定義する場合は、タブに移動し **[!UICONTROL Links]** ます。

   必要なだけリレーションを追加します。 各リレーションに対して、最初にリンクされたディメンションを選択し、次にリンクの詳細で、対応するフィールドを指定します。

1. 受信データを識別するだけの場合は、タブに移動し、ボックス **[!UICONTROL Identification]** をオンにし **[!UICONTROL Identify the document from the working data]** ます。

   インバウンドデータを調整するターゲットディメンションを選択します。

   調整条件を追加して、インバウンド移行レコードを選択したターゲットディメンションレコードにリンクします。 複数の条件を指定する場合、すべてのデータ間のリンクが機能するために、すべての条件を検証する必要があります。

   モードを選択 **[!UICONTROL Processing unidentified source lines]** します。

   * **[!UICONTROL Ignore them]**:識別可能なデータのみが、アクティビティのアウトバウンド移行に保持されます。
   * **[!UICONTROL Keep in the outbound population]**:インバウンドトランジションのすべてのデータは、アクティビティのアウトバウンドトランジションに保持されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例1:関係の定義 {#example-1--relation-definition}

次の例は、ファイル内の購入データを使用してデータベースを更新するワークフローを示しています。 購入データには、クライアントの電子メールや製品コードなど、他のディメンションからの要素を参照するデータが含まれます。

>[!NOTE]
>
>この例で **使用される** Transactions **and** Products（トランザクション）リソースは、デフォルトではAdobe Campaignデータベースに存在しません。 そのため、これらの変数は事前に [Custom resources関数を使用して作成されています](../../developing/using/data-model-concepts.md) 。 インポートしたファイル内の電子メールアドレスに対応するプロファイルと製品は、事前にデータベースにロードされていました。

ワークフローは、次のアクティビティで構成されます。

![](assets/reconciliation_example1.png)

* 読み込 **[!UICONTROL Load file]** むファイルのデータを読み込んで検出するアクティビティ。 インポートされたファイルには、次のデータが含まれます。

   * トランザクション日
   * クライアントの電子メールアドレス
   * 購入した製品のコード
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* 購入デ **[!UICONTROL Reconciliation]** ータを製品だけでなくデータベースプロファイルに連結するアクティビティ。 したがって、ファイルデータとプロファイルテーブルと製品テーブルとの間の関係を定義する必要があります。 この設定は、アクティビティのタブで実行され **[!UICONTROL Relations]** ます。

   * プロファイルとの **関係**:ファイルの **client列は** 、 **Profilesディメンションの** email **フィールドにリンクさ** れます。
   * 製品との関 **係**:ファイルの **product列は** 、 **ProfilesディメンションのproductCode** フィールドにリン **** クされます。
   列は、リンクされたディメンションの外部キーを参照するために、インバウンドデータに追加されます。

   ![](assets/reconciliation_example3.png)

* アクティビテ **[!UICONTROL Update data]** ィを使用すると、インポートしたデータを使用して更新するデータベースフィールドを定義できます。 データは、前のアクティビティの **Transactions** （トランザクション）ディメンションに属していると既に識別されているので、次のIDオプションを使用 **[!UICONTROL Directly using the targeting dimension]** できます。

   更新するフィールドを自動的に検出するオプションを使用すると、前のアクティビティで設定したリンク（プロファイルと製品）がのリストに追加されま **[!UICONTROL Fields to update]**&#x200B;す。 また、トランザクション日に対応するフィールドがこのリストに正しく追加されていることを確認する必要があります。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## 例2:識別 {#example-2--identification}

次の例は、新しいクライアントを含む読み込んだファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。 これは、次のアクティビティで構成されます。

![](assets/identification_example2.png)

* 読み込 **[!UICONTROL Load file]** むファイルのデータを読み込んで検出するアクティビティ。 インポートされたファイルには、次のデータが含まれます。

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* 読み込ま **[!UICONTROL Reconciliation]** れたファイルの各列をプロファイルディメンション列にリンクするアクティビティ。 識別できないファイルレコード（データが見つからない、互換性のないデータタイプなど）が無視され、最終オーディエンスデータの整合性が維持されます。

   ![](assets/identification_example1.png)

* プロファ **[!UICONTROL Save audience]** イルのオーディエンスを保存するアクティビティ。

   ![](assets/identification_example3.png)

