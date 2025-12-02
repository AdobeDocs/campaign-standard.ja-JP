---
title: サブスクリプションサービス
description: サブスクリプションサービスアクティビティを使用すると、プロファイルを一括でサービスに購読登録したり、サービスから購読登録を解除したりできます。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 612b6203-1cc9-4015-a026-e5a249f3d03d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 96%

---

# 購読サービス {#subscription-services}

## 説明 {#description}

![](assets/wf_subscription.png)

「**[!UICONTROL Subscription Services]**」アクティビティを使用すると、プロファイルを一括でサービスに購読登録したり、サービスから購読登録を解除したりできます。

>[!CAUTION]
>
>サブスクリプションがワークフローのコンテキストで管理される場合、サービスプロパティで定義されている様々な確認メールは、登録済みまたは登録解除済みのプロファイルには配信されません。

## 使用コンテキスト {#context-of-use}

「**[!UICONTROL Subscription Services]**」アクティビティは、複数のプロファイルのサービスへの購読登録とサービスからの購読登録解除を Adobe Campaign で一括で行える唯一の機能です。

このアクティビティは、ターゲティングを実行した後、または識別されたデータを含んだファイルをインポートした後で使用できます。

ファイル内の専用の列で指定された場合、このアクティビティでは、アクション（購読登録または購読登録解除）とアクションの対象となるサービスも選択できます。

**関連トピック：**

* [ユースケース：ファイルからの複数の購読ステータスの更新](../../automating/using/updating-subscriptions-from-file.md)
* [ユースケース：ファイルから特定のサービスへのプロファイルの購読](../../automating/using/subscribing-profiles-from-file.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Subscription Services]**」アクティビティをドラッグ＆ドロップします。
1. クエリやインポート後の紐付けといった、他のターゲティングアクティビティの後に接続します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 次のいずれかのオプションを使用して、サブスクリプション管理の対象となる「**[!UICONTROL Service]**」を選択します。

   * **[!UICONTROL Select a specific service]**：サービスを手動で選択します。
   * **[!UICONTROL Select services from the inbound transition]**：サービスをインバウンドトランジションで指定します。例えば、管理対象のサービスを 1 行ごとに指定したファイルをインポートできます。このオプションを選択する場合は、データと&#x200B;**サービス**&#x200B;リソースの間に事前にリンクが作成されていることを確認してください（[こちらの例](#example--updating-multiple-subscription-statuses-from-a-file)を参照）。

     この場合、操作の対象になるサービスが、レコードごとに動的に選択されます。

1. 次のいずれかのオプションを使用して、実行する「**[!UICONTROL Operation type]**」を選択します。

   * **[!UICONTROL Select a specific operation type]**：「**[!UICONTROL Subscribe]**」または「**[!UICONTROL Unsubscribe]**」するプロファイルを手動で選択します。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**：レコードごとに実行する操作を指定したインバウンドデータの列を選択します。

     この列では、操作をブール値または整数値として指定する必要があります。レコードを購読登録解除するには **0**、購読登録するには&#x200B;**1** を使用します。

     インポートしたファイルに含まれている値が上記の要件を満たさない場合でも、「[Remapping of values](../../automating/using/load-file.md#column-format)」オプションを「**[!UICONTROL Load file]**」アクティビティから選択して使用できます。

1. プロファイルのサービス購読登録日に対応する列がインバウンドデータに含まれている場合は、その列を選択します。この値は空のままでもかまいませんが、ワークフローの実行時に購読登録日は設定されません。
1. 購読登録日の接触チャネルを定義します。インバウンドデータのフィールドの 1 つに設定するか、または「**[!UICONTROL Set a constant as origin]**」オプションをオンにして任意の定数値に設定できます。この値は空のままでもかまいませんが、ワークフローの実行時に接触チャネルは設定されません。
1. 必要に応じて、アウトバウンドトランジションを生成できます。このトランジションには、インバウンドアクティビティのデータとまったく同じデータが含まれています。
1. アクティビティの設定を確認し、ワークフローを保存します。

   これでワークフローを実行する準備が整いました。ワークフローを実行したら、サービスに購読登録またはサービスから購読登録解除したプロファイルがサービスの詳細に表示されます。

## 例：ファイルのインポート後の特定のサービスへのプロファイルの購読 {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

次の例では、プロファイルを含んだファイルをインポートし、これらのプロファイルを既存のサービスに購読登録する方法を示します。ファイルをインポートした後で、インポートしたデータをプロファイルとして識別できるように紐付けをおこなう必要があります。ファイルに重複が含まれていないことを確認するために、データに対して「重複排除 - 重複」アクティビティが実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* 「**[!UICONTROL Load file]**」アクティビティでプロファイルファイルを読み込み、インポートした列の構造を定義します。

  この例では、読み込まれるファイルは .csv 形式で、次のデータが含まれています。

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

* 「**[!UICONTROL Reconciliation]**」アクティビティで、ファイルのデータを、Adobe Campaign データベースのプロファイルディメンションに属するものとして識別します。「**[!UICONTROL Identification]**」タブのみ設定します。プロファイルのメールアドレスに従って、ファイルデータを識別します。

  ![](assets/subscription_activity_example3.png)

* 「**[!UICONTROL Deduplication]**」で、（紐付けの結果生成される）一時リソースの **email** フィールドに基づいて、すべての重複を識別します。ファイルからインポートしたデータに重複が含まれている場合、サービスへの購読登録はすべてのデータで失敗します。

  ![](assets/subscription_activity_example5.png)

* 「**[!UICONTROL Subscription Services]**」アクティビティでは、プロファイルの購読登録先のサービス、購読登録日に対応するフィールド、購読登録の接触チャネルを選択できます。

  ![](assets/subscription_activity_example4.png)

## 例：ファイルからの複数の購読ステータスの更新 {#example--updating-multiple-subscription-statuses-from-a-file}

次の例では、プロファイルを含んだファイルをインポートして、プロファイルの購読登録先を、ファイルで指定されたいくつかのサービスに更新する方法を示します。ファイルをインポートした後で、インポートしたデータを、サービスにリンクされたプロファイルとして識別できるように紐付けをおこなう必要があります。ファイルに重複が含まれていないことを確認するために、データに対して「重複排除 - 重複」アクティビティが実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* 「**[!UICONTROL Load file]**」アクティビティでプロファイルファイルを読み込み、インポートした列の構造を定義します。

  この例では、読み込まれるファイルは .csv 形式で、次のデータが含まれています。

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

  この操作は、ファイル内で「sub」または「unsub」と指定されています。実行する操作を認識するために、**ブール値**&#x200B;または&#x200B;**整数**&#x200B;値が必要です。「0」が購読登録解除、「1」が購読登録です。この要件を満たすために、値の再マッピングが「operation」列の詳細で実行されます。

  ![](assets/subscription_example_remapping.png)

  「0」と「1」が既に操作の識別に使用されているファイルでは、再マッピングの必要はありません。列が&#x200B;**ブール値**&#x200B;または&#x200B;**整数**&#x200B;として処理されていることを「**[!UICONTROL Column definition]**」タブで確認してください。

* 「**[!UICONTROL Reconciliation]**」アクティビティで、ファイルのデータを、Adobe Campaign データベースのプロファイルディメンションに属するものとして識別します。「**[!UICONTROL Identification]**」タブでは、ファイルの **email** フィールドと、プロファイルリソースの **email** フィールドが照合されます。

  ![](assets/subscription_activity_example3.png)

  「**[!UICONTROL Relations]**」タブでは、サービスリソースとのリンクが作成されて、ファイルの **service** フィールドを認識できるようになります。この例では、値はサービスリソースの **name** フィールドと一致します。

  ![](assets/subscription_example_service_relation.png)

* 「**[!UICONTROL Deduplication]**」で、（紐付けの結果生成される）一時リソースの **email** フィールドに基づいて、重複を識別します。重複がある場合、サービスへの購読登録はすべてのデータで失敗するので、重複を排除することが重要です。

  ![](assets/subscription_activity_example5.png)

* 「**[!UICONTROL Subscription Services]**」で、「**[!UICONTROL Reconciliation]**」アクティビティで作成されたリンクを通じて、更新するサービスがトランジションに由来するものであることを識別します。

  「**[!UICONTROL Operation type]**」は、ファイルの **operation** フィールドに由来するものとして識別されます。ここで選択できるのは、ブール値フィールドまたは整数フィールドのみです。実行する操作を記述しているファイル列がリストに表示されない場合は、前述のように、「**[!UICONTROL Load file]**」アクティビティで列の形式が正しく設定されていることを確認してください。

  ![](assets/subscription_activity_example_from_file.png)
