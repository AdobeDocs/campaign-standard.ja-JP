---
title: 購読サービス
description: 購読サービスアクティビティを使用すると、プロファイルを一括で取得してサービスに登録したり、サービスから登録を解除したりできます。
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---


# 購読サービス {#subscription-services}

## 説明 {#description}

![](assets/wf_subscription.png)

この **[!UICONTROL Subscription Services]** アクティビティを使用すると、プロファイルを一括して取得してサービスに登録したり、サービスから登録を解除したりできます。

>[!CAUTION]
>
>購読がワークフローのコンテキストで管理される場合、登録済みまたは登録解除済みのプロファイルは、サービスプロパティで定義されている別の確認電子メールを受け取りません。

## 使用状況 {#context-of-use}

この **[!UICONTROL Subscription Services]** アクティビティは、複数のプロファイルが1回の操作でサービスに登録したり、サービスから登録解除したりできる唯一のAdobe Campaign機能です。

このアクティビティは、ターゲット設定を実行した後、または識別されたデータを含むファイルを読み込んだ後に使用できます。

専用の列を使用してファイル内で指定した場合、このアクティビティでは、アクション（購読または登録解除）およびアクションを実行するサービスも選択できます。

**関連トピック：**

* [使用例： ファイルからの複数の購読ステータスの更新](../../automating/using/updating-subscriptions-from-file.md)
* [使用例： ファイルから特定のサービスへのプロファイルのサブスクライブ](../../automating/using/subscribing-profiles-from-file.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Subscription Services]** アクティビティをドラッグ&amp;ドロップします。
1. インポート後のクエリや調整など、他のターゲットアクティビティの後に接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 次のい **[!UICONTROL Service]** ずれかのオプションを使用して、購読を管理する対象を選択します。

   * **[!UICONTROL Select a specific service]**: サービスを手動で選択します。
   * **[!UICONTROL Select services from the inbound transition]**: サービスは受信トランジションで指定されます。 例えば、各行で管理するサービスを指定するファイルを読み込むことができます。 このオプションを選択する場合は、 **次の例に示すように、データと** Service [リソースの間に事前にリンクが作成されていることを確認してください](#example--updating-multiple-subscription-statuses-from-a-file)。

      次に、操作を実行するサービスが、レコードごとに動的に選択されます。

1. 次のいずれか **[!UICONTROL Operation type]** のオプションを使用して、実行するファイルを選択します。

   * **[!UICONTROL Select a specific operation type]**: を手動で選択し **[!UICONTROL Subscribe]** ます。または、 **[!UICONTROL Unsubscribe]** プロファイルを使用します。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: 各レコードで実行する操作を指定する受信データの列を選択します。

      この列では、操作をブール値または整数値として指定する必要があります。 レコードの登録を解除するには **0** 、登録を解除するには **1** を使用します。

      読み込んだファイルに含まれる値が上記の要件を満たさない場合は、 [アクティビティの「値の](../../automating/using/load-file.md#column-format) 再マッピング **[!UICONTROL Load file]** 」オプションを使用できます。

1. 受信データに、サービスへのプロファイルの購読日に対応する列が含まれている場合は、その列を選択します。 この値は空のままにしてかまいませんが、ワークフローの実行時に購読日が設定されていません。
1. 購読の接触チャネルを定義します。 受信データのフィールドの1つ、または選択した定数値に設定するには、この **[!UICONTROL Set a constant as origin]** オプションをオンにします。 空のままにしてもかまいませんが、ワークフローの実行時に接触チャネルが設定されていません。
1. 必要に応じて、アウトバウンドトランジションを生成できます。 このトランジションには、受信アクティビティのデータとまったく同じデータが含まれます。
1. アクティビティの設定を確認し、ワークフローを保存します。

   これで、実行する準備が整いました。 実行した後は、サービスを購読または登録解除したプロファイルをサービスの詳細で表示できます。

## 例： ファイルの読み込み後に特定のサービスにプロファイルを登録する {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

次の例は、プロファイルを含むファイルをインポートし、既存のサービスに登録する方法を示します。 ファイルをインポートした後、インポートしたデータをプロファイルとして識別できるように調整を行う必要があります。 ファイルに重複が含まれていないことを確認するために、重複排除 - 重複アクティビティがデータに対して実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* アクティビティは、プロファイルファイルを読み込み、読み込まれた列の構造を定義します。 **[!UICONTROL Load file]**

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

* アクティビティは、ファイルのデータを、Adobe Campaignデータベースのプロファイルディメンションに属するものとして識別する。 **[!UICONTROL Reconciliation]** タブのみが設定さ **[!UICONTROL Identification]** れます。 プロファイルの電子メールアドレスに従ってファイルデータを識別します。

   ![](assets/subscription_activity_example3.png)

* (調整 **[!UICONTROL Deduplication]** の結果生じる)一時リソースの **** 電子メールフィールドに基づく重複はすべて識別します。 ファイルからインポートしたデータに重複が含まれている場合、サービスへの購読はすべてのデータで失敗します。

   ![](assets/subscription_activity_example5.png)

* アクティビティでは、プロファイルを登録する必要があるサービス、購読日に対応するフィールド、購読の接触チャネルを選択できます。 **[!UICONTROL Subscription Services]**

   ![](assets/subscription_activity_example4.png)

## 例： ファイルからの複数の購読ステータスの更新 {#example--updating-multiple-subscription-statuses-from-a-file}

次の例は、プロファイルを含むファイルを読み込み、その購読を、ファイルで指定されたいくつかのサービスに更新する方法を示しています。 ファイルをインポートした後、インポートしたデータがサービスへのリンクを持つプロファイルとして識別できるように調整を行う必要があります。 ファイルに重複が含まれていないことを確認するために、重複排除 - 重複アクティビティがデータに対して実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* アクティビティは、プロファイルファイルを読み込み、読み込まれた列の構造を定義します。 **[!UICONTROL Load file]**

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

   この操作は、ファイル内で「sub」または「unsub」として指定されています。 実行する操作を認識する **Boolean** 値または **Integer** 値が必要です。 「0」を登録解除し、「1」をサブスクライブに送信します。 この要件を満たすために、値の再マッピングは「operation」列の詳細で実行されます。

   ![](assets/subscription_example_remapping.png)

   ファイルで、操作の識別に「0」と「1」が既に使用されている場合は、これらの値を再マップする必要はありません。 列が **Boolean** または **Integer****[!UICONTROL Column definition]** （整数）としてタブで処理されていることを確認してください。

* アクティビティは、ファイルのデータを、Adobe Campaignデータベースのプロファイルディメンションに属するものとして識別する。 **[!UICONTROL Reconciliation]** この **[!UICONTROL Identification]** タブを使用して、ファイルの **電子メールフィールドとプロファイルリソースの** 電子メール **** フィールドとが一致します。

   ![](assets/subscription_activity_example3.png)

   このタブでは、サービスリソースを使用してリンクが作成され、ファイルの **[!UICONTROL Relations]** サービス **** ・フィールドを認識できるようになります。 この例では、値はサービスリソースの **名前** フィールドに一致します。

   ![](assets/subscription_example_service_relation.png)

* (調整 **[!UICONTROL Deduplication]** の結果生じる)一時リソースの **** 電子メールフィールドに基づく重複の識別。 サービスへの購読が重複の場合はすべてのデータで失敗するので、重複を排除することが重要です。

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** は、 **[!UICONTROL Reconciliation]** アクティビティで作成されたリンクを介して、更新するサービスがトランジションからのものであることを識別します。

   は、ファイル **[!UICONTROL Operation type]** の **操作** フィールドからの値として識別されます。 ここで選択できるのは、ブール値フィールドまたは整数フィールドのみです。 実行する操作を含むファイルの列がリストに表示されない場合は、この例で前述したように、 **[!UICONTROL Load file]** アクティビティで列の形式が正しく設定されていることを確認してください。

   ![](assets/subscription_activity_example_from_file.png)

