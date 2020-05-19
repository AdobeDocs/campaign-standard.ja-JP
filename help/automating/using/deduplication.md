---
title: 重複排除
description: 重複排除 - 重複アクティビティでは、受信アクティビティの結果の重複を削除できます。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 2%

---


# 重複排除{#deduplication}

## 説明 {#description}

![](assets/deduplication.png)

この **[!UICONTROL Deduplication]** アクティビティでは、受信アクティビティの結果の重複を削除できます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Deduplication]** アクティビティは、通常、ターゲット設定アクティビティに従って、またはファイルを読み込んだ後、またはターゲット設定されたデータを使用できるアクティビティの前に使用されます。

重複排除 - 重複中、受信トランジションは別々に処理されます。 例えば、プロファイル1の結果にクエリAが存在し、クエリ2の結果にもAが存在する場合、重複は除外されません。

したがって、重複排除 - 重複が受信トランジションを1つだけ持つようにお勧めします。 これを行うには、和集合アクティビティ、交差点アクティビティなど、ターゲット設定のニーズに対応したアクティビティを使用して、様々なクエリを組み合わせます。 次に例を示します。

![](assets/dedup_bonnepratique.png)

## 設定 {#configuration}

重複排除 - 重複アクティビティを設定するには、ラベル、メソッド、重複排除 - 重複条件、および結果に関連するオプションを入力する必要があります。

1. ワークフローに **[!UICONTROL Deduplication]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   ![](assets/deduplication_1.png)

1. 重複排除 - 重複 **[!UICONTROL Resource type]** を実行する対象を選択します。

   * **[!UICONTROL Database resource]** データベースに既に存在するデータに対して重複排除 - 重複が実行される場合。 重複除外するデータ **[!UICONTROL Filtering dimension]** に応じて、と **[!UICONTROL Targeting dimension]**&#x200B;を選択します。 デフォルトでは、 **プロファイルで重複排除 - 重複が実行されます**。
   * **[!UICONTROL Temporary resource]** 重複排除 - 重複がワークフローの一時データで実行される場合： 重複除外するデータ **[!UICONTROL Targeted set]** を含むデータを選択します。 この使用例は、ファイルのインポート後、またはデータベース内のデータがリンチされた(例えば、セグメントコードで)場合に発生します。

1. を選択し **[!UICONTROL Number of unique records to keep]**&#x200B;ます。 このフィールドのデフォルト値は1です。 値0を指定すると、すべての重複を保持できます。

   例えば、レコードAとBがレコードYの重複と見なされ、レコードCがレコードZの重複と見なされる場合、次のように指定します。

   * フィールドの値が1の場合： YとZのレコードのみが保持されます。
   * フィールドの値が0の場合： すべてのレコードが保持されます。
   * フィールドの値が2の場合： A、B、Yのレコードは、C、Zのレコードを記録し、偶然、又はその後選択した重複排除 - 重複法に応じて2レコード保持する。

1. 指定したリストに条件を追加して、 **[!UICONTROL Duplicate identification]** 条件を定義します。 同じ値を使用して重複を識別できるフィールドや式を指定します。 電子メールアドレス、名、姓など 条件の順序によって、最初に処理する条件を指定できます。
1. ドロップダウンリストで、使用するアイテム **[!UICONTROL Deduplication method]** を選択します。

   * **[!UICONTROL Choose for me]**: 重複に含めないレコードをランダムに選択します。
   * **[!UICONTROL Following a list of values]**: 1つ以上のフィールドに値の優先度を定義できます。 優先度の値を定義するには、フィールドを選択するか式を作成し、適切なフィールドに値を追加します。To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: これにより、選択した式の値が空でないレコードを優先度として保持できます。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: これにより、入力した式の値が最も小さいか大きいレコードを保持できます。

      ![](assets/deduplication_4.png)

1. 必要に応じて、アクティビティの [トランジションを管理し](../../automating/using/activity-properties.md) 、アウトバウンド母集団のアドバンスオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例1: 配信前の重複の識別 {#example-1--identifying-duplicates-before-a-delivery}

次の例は、電子メールを送信する前にターゲットの重複を除外する重複排除 - 重複を示しています。 つまり、同じプロファイルに対して複数回通信を送信するのを避けることができます。

ワークフローは次の要素で構成されます。

![](assets/deduplication_example_workflow.png)

* 電子メ **[!UICONTROL Query]** ールのターゲットを定義できる。 このワークフローでは、18歳から25歳のプロファイルのうち、1年以上クライアントデータベースに属しているすべてのターゲットがされます。

   ![](assets/deduplication_example_query.png)

* 前の **[!UICONTROL Deduplication]** アクティビティから来た重複を識別できるクエリ。 この例では、各重複に保存されるレコードは1つだけです。 重複は電子メールアドレスを使用して識別されます。 つまり、ターゲティングに存在する電子メールアドレスごとに1回だけ電子メール配信を送信できます。

   選択した重複排除 - 重複方法はで **[!UICONTROL Non-empty value]**&#x200B;す。 これにより、重複の場合に記録されるレコードの中で、 **名が指定されているレコードを優先します** 。 これにより、電子メールコンテンツのパーソナライゼーションフィールドで名が使用される場合に、一貫性が向上します。

   また、重複を保持し、リストを行うためのトランジションも追加されます。

   ![](assets/deduplication_example_dedup.png)

* 重複排除 - 重複のメインの送信トランジションの後に **[!UICONTROL Email delivery]** 配置される。 電子メール配信の設定について詳しくは、「 [電子メール配信](../../automating/using/email-delivery.md) 」の節を参照してください。
* 重複を **[!UICONTROL Save audience]** 重複 **** オーディエンスに保存するために、重複排除 - 重複の追加トランジションの後に配置されるアクティビティ。 このオーディエンスは、各電子メール配信からそのメンバーを直接除外するために再利用できます。

## 例2: 読み込んだファイルからのデータの重複を除外する {#example-2--deduplicating-the-data-from-an-imported-file}

この例では、データをデータベースにロードする前にインポートしたファイルからデータの重複除外を行う方法を示します。 この手順により、データベースに読み込まれるデータの品質が向上します。

ワークフローは次の要素で構成されます。

![](assets/deduplication_example2_workflow.png)

* プロファイルのリストを含むファイルは、 **[!UICONTROL Load file]** アクティビティを使用して読み込まれます。 この例では、インポートされるファイルは.csv形式で、10プロファイルが含まれています。

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

   このファイルは、列の形式を検出および定義するためのサンプルファイルとしても使用できます。 タブから、読み込んだファイルの各列が正しく設定されていることを確認し **[!UICONTROL Column definition]** ます。

   ![](assets/deduplication_example2_fileloading.png)

* アクティビティ **[!UICONTROL Deduplication]** 。 重複排除 - 重複は、ファイルのインポート後、およびデータベースにデータを挿入する前に、直接実行されます。 したがって、この値は **[!UICONTROL Temporary resource]****[!UICONTROL Load file]** アクティビティの値に基づく必要があります。

   この例では、ファイルに含まれる一意の電子メールアドレスごとに1つのエントリを保持します。 したがって、重複識別は、一時リソースの **email** 列で行われます。 ただし、2つの電子メールアドレスがファイル内に2回出現します。 したがって、2行が重複と見なされます。

   ![](assets/deduplication_example2_dedup.png)

* アクティビティを使用すると、重複排除 - 重複プロセスから保持されたデータをに挿入できます。 **[!UICONTROL Update data]** インポートされたデータがプロファイルディメンションに属していると識別されるのは、データが更新された場合のみです。

   ここでは、データベースにまだ存在し **[!UICONTROL Insert only]** ないプロファイルを使用します。 これを行うには、ファイルの電子メール列と **プロファイル** ディメンションの電子メールフィールドを紐付けキーとして使用します。

   ![](assets/deduplication_example2_writer1.png)

   データの挿入元となるファイルの列と、 **[!UICONTROL Fields to update]** タブのデータベースフィールドとの間のマッピングを指定します。

   ![](assets/deduplication_example2_writer2.png)

次に、ワークフローを開始します。 次に、重複排除 - 重複プロセスから保存されたレコードがデータベース内のプロファイルに追加されます。
