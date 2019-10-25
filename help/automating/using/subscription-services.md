---
title: 購読サービス
seo-title: 購読サービス
description: 購読サービス
seo-description: 購読サービスアクティビティでは、プロファイルを一括で取得し、サービスに登録したり、サービスから登録解除したりできます。
page-status-flag: 非活性化の
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データ管理活動
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 購読サービス{#subscription-services}

## 説明 {#description}

![](assets/wf_subscription.png)

アクティビティ **[!UICONTROL Subscription Services]** では、プロファイルを一括して取得し、サービスに登録したり、サービスから登録を解除したりできます。

>[!CAUTION]
>
>ワークフローのコンテキストで管理される購読の場合、購読プロファイルまたは未登録のプロファイルは、サービスプロパティで定義された異なる確認電子メールを受け取りません。

## 使用状況 {#context-of-use}

アクティビテ **[!UICONTROL Subscription Services]** ィは、1回の操作で複数のプロファイルをサービスに登録したり、サービスから登録を解除したりできる唯一のAdobe Campaign機能です。

このアクティビティは、ターゲット設定を実行した後、または識別されたデータを含むファイルを読み込んだ後に使用できます。

専用列を使用してファイル内で指定した場合、このアクティビティでは、アクション（購読または購読解除）と、アクションを実行するサービスも選択できます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Subscription Services]** にドラッグ&amp;ドロップします。
1. インポート後のクエリや調整など、他のターゲティングアクティビティの後に接続します。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 次のいず **[!UICONTROL Service]** れかのオプションを使用して、購読を管理する対象を選択します。

   * **[!UICONTROL Select a specific service]**:サービスを手動で選択します。
   * **[!UICONTROL Select services from the inbound transition]**:サービスは、受信移行で指定されます。 例えば、各行に対して管理するサービスを指定するファイルを読み込むことができます。 このオプションを選択する場合は、この例に示すように、データと **Service** リソースの間に事前にリンクが作成されていることを [確認します](#example--updating-multiple-subscription-statuses-from-a-file)。

      次に、操作を実行するサービスが、レコードごとに動的に選択されます。

1. 次のいずれかの **[!UICONTROL Operation type]** オプションを使用して、実行するを選択します。

   * **[!UICONTROL Select a specific operation type]**:プロファイルを手動で選択し **[!UICONTROL Subscribe]** ます **[!UICONTROL Unsubscribe]** 。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**:各レコードに対して実行する操作を指定する、受信データの列を選択します。

      この列では、操作をブール値または整数で指定する必要があります。 レコー **ドの購読を解除するには** 0を、購読するには **1** を使用します。

      読み込んだファイルに含まれる値が上記の要件を満たさない場合でも、アクティビティで使用可能な「 [Remapping of values](../../automating/using/load-file.md#column-format) 」オプションを使用でき **[!UICONTROL Load file]** ます

1. 受信データに、サービスに対するプロファイルの購読日に対応する列が含まれている場合は、その列を選択します。 空のままにしてもかまいませんが、ワークフローの実行時に購読の日付が設定されていません。
1. 購読の出所を定義します。 受信データのフィールドの1つ、または選択した定数値に設定するには、このオプションをオンにし **[!UICONTROL Set a constant as origin]** ます。 空のままにしてもかまいませんが、ワークフローの実行時に原点が設定されません。
1. 必要に応じて、アウトバウンドトランジションを生成できます。 この移行には、受信アクティビティのデータとまったく同じデータが含まれます。
1. アクティビティの設定を確認し、ワークフローを保存します。

   これで、実行する準備が整いました。 実行すると、サービスを購読したプロファイルや、サービスを購読解除したプロファイルを、サービスの詳細に表示できます。

## 例：ファイルの読み込み後の特定のサービスへのプロファイルのサブスクライブ {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

次の例は、プロファイルを含むファイルをインポートし、既存のサービスに登録する方法を示しています。 ファイルをインポートした後、インポートしたデータをプロファイルとして識別できるように調整を行う必要があります。 ファイルに重複が含まれないように、データに対して重複除外アクティビティが実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* アクティビテ **[!UICONTROL Load file]** ィは、プロファイルファイルを読み込み、読み込まれた列の構造を定義します。

   この例では、読み込まれるファイルは.csv形式で、次のデータが含まれています。

   ```
   lastname;firstname;email;birthdate;subdate
   jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
   phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
   weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
   martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
   reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
   grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
   ```

   ![](assets/subscription_activity_example2.png)

* アクティビテ **[!UICONTROL Reconciliation]** ィは、ファイルのデータがAdobe Campaignデータベースのプロファイルディメンションに属していることを識別します。 タブのみが設 **[!UICONTROL Identification]** 定されます。 プロファイルの電子メールアドレスに従ってファイルデータを識別します。

   ![](assets/subscription_activity_example3.png)

* (調整 **[!UICONTROL Deduplication]** の結果として **** )一時リソースの電子メールフィールドに基づいて、重複を識別します。 ファイルからインポートしたデータに重複が含まれている場合、サービスのサブスクリプションはすべてのデータに対して失敗します。

   ![](assets/subscription_activity_example5.png)

* アクテ **[!UICONTROL Subscription Services]** ィビティを使用すると、プロファイルを登録する必要があるサービス、購読日に対応するフィールド、および購読の開始日を選択できます。

   ![](assets/subscription_activity_example4.png)

## 例：ファイルからの複数の購読ステータスの更新 {#example--updating-multiple-subscription-statuses-from-a-file}

次の例は、プロファイルを含むファイルを読み込み、そのファイルで指定された複数のサービスに対して購読を更新する方法を示しています。 ファイルをインポートした後、インポートしたデータがサービスへのリンクを持つプロファイルとして識別できるように、調整を行う必要があります。 ファイルに重複が含まれないように、データに対して重複除外アクティビティが実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* アクティビテ **[!UICONTROL Load file]** ィは、プロファイルファイルを読み込み、読み込まれた列の構造を定義します。

   この例では、読み込まれるファイルは.csv形式で、次のデータが含まれています。

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   この操作は、ファイル内で「sub」または「unsub」として指定されています。 実行する操作を **Boolean** 値または **** Integer値で認識する必要があります。「0」を設定して購読を解除し、「1」を設定して購読を解除します。 この要件を満たすために、値のリマップは「operation」列の詳細で実行されます。

   ![](assets/subscription_example_remapping.png)

   ファイルで操作を識別するために「0」と「1」が既に使用されている場合は、これらの値を再マップする必要はありません。 列が **Boolean** （ブール値）または **Integer（整数）として処理されていることを確認し****[!UICONTROL Column definition]** ます。

* アクティビテ **[!UICONTROL Reconciliation]** ィは、ファイルのデータがAdobe Campaignデータベースのプロファイルディメンションに属していることを識別します。 このタブを使 **[!UICONTROL Identification]** 用して、フ **ァイルの** 「email」フィールドとプロファイルリソースの「email **** 」フィールドが照合されます。

   ![](assets/subscription_activity_example3.png)

   このタブで **[!UICONTROL Relations]** は、サービスリソースを使用してリンクが作成され、ファイルのサ **ービス** ・フィールドを認識できます。 この例では、値はサービスリソースの **name** フィールドと一致します。

   ![](assets/subscription_example_service_relation.png)

* (調整 **[!UICONTROL Deduplication]** の結果として **** )一時リソースの電子メールフィールドに基づいて、重複を識別します。 サービスのサブスクリプションで重複が発生した場合はすべてのデータが失敗するので、重複を排除することが重要です。

   ![](assets/subscription_activity_example5.png)

* Aは、ア **[!UICONTROL Subscription Services]** クティビティで作成されたリンクを介して、移行からの移行で更新するサービスを識別 **[!UICONTROL Reconciliation]** します。

   は、フ **[!UICONTROL Operation type]** ァイルの操作フィールドから **のもの** として識別されます。 ここで選択できるのは、ブール型または整数型のフィールドのみです。 実行する操作を含むファイルの列がリストに表示されない場合は、この例で前述したように、アクティビティに列の形式が正しく設定されていることを確 **[!UICONTROL Load file]** 認してください。

   ![](assets/subscription_activity_example_from_file.png)

