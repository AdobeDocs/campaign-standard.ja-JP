---
solution: Campaign Standard
product: campaign
title: ファイルから特定のサービスへのプロファイルの購読
description: この使用例では、プロファイルを含むファイルをインポートし、既存のサービスに登録する方法を示します。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ファイル{#subscribing-profiles-to-a-specific-service-after-importing-a-file}のインポート後、特定のサービスにプロファイルをサブスクライブする

次の例では、プロファイルを含んだファイルをインポートし、これらのプロファイルを既存のサービスに購読登録する方法を示します。ファイルをインポートした後で、インポートしたデータをプロファイルとして識別できるように紐付けをおこなう必要があります。ファイルに重複が含まれていないことを確認するために、データに対して「重複排除 - 重複」アクティビティが実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* [ファイル](../../automating/using/load-file.md)を読み込みアクティビティは、プロファイルファイルを読み込み、読み込まれた列の構造を定義します。

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

* [調整](../../automating/using/reconciliation.md)アクティビティは、ファイルのデータをAdobe Campaignデータベースのプロファイルディメンションに属するものとして識別します。 「**[!UICONTROL Identification]**」タブのみ設定します。プロファイルの E メールアドレスに従って、ファイルデータを識別します。

   ![](assets/subscription_activity_example3.png)

* （調整の結果の）一時リソースの&#x200B;**email**&#x200B;フィールドに基づく[重複排除 - 重複](../../automating/using/deduplication.md)は、重複を識別します。 ファイルからインポートしたデータに重複が含まれている場合、サービスへの購読登録はすべてのデータで失敗します。

   ![](assets/subscription_activity_example5.png)

* [購読サービス](../../automating/using/subscription-services.md)アクティビティを使用すると、プロファイルを登録するサービス、購読日に対応するフィールド、購読の接触チャネルを選択できます。

   ![](assets/subscription_activity_example4.png)
