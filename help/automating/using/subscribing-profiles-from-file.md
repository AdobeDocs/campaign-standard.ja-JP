---
title: ファイルから特定のサービスへのプロファイルのサブスクライブ
description: この使用例では、プロファイルを含むファイルをインポートし、既存のサービスに登録する方法を示します。
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---


# ファイルの読み込み後に特定のサービスにプロファイルを登録する {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

次の例は、プロファイルを含むファイルをインポートし、既存のサービスに登録する方法を示します。 ファイルをインポートした後、インポートしたデータをプロファイルとして識別できるように調整を行う必要があります。 ファイルに重複が含まれていないことを確認するために、重複排除 - 重複アクティビティがデータに対して実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* ファイルの [ロード](../../automating/using/load-file.md) アクティビティは、プロファイルファイルをロードし、インポートされた列の構造を定義します。

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

* 「 [調整](../../automating/using/reconciliation.md) 」アクティビティは、ファイルのデータをAdobe Campaignデータベースのプロファイルディメンションに属するものとして識別します。 タブのみが設定さ **[!UICONTROL Identification]** れます。 プロファイルの電子メールアドレスに従ってファイルデータを識別します。

   ![](assets/subscription_activity_example3.png)

* （調整の結果生じる）一時的なリソースの [電子メール](../../automating/using/deduplication.md) フィールドに基づく **** 重複排除 - 重複は、重複を識別します。 ファイルからインポートしたデータに重複が含まれている場合、サービスへの購読はすべてのデータで失敗します。

   ![](assets/subscription_activity_example5.png)

* 「 [購読サービス](../../automating/using/subscription-services.md) 」アクティビティを使用すると、プロファイルを登録する必要があるサービス、購読日に対応するフィールド、購読の接触チャネルを選択できます。

   ![](assets/subscription_activity_example4.png)
