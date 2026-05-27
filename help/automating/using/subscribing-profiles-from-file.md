---
title: ファイルから特定のサービスへのプロファイルの購読
description: このユースケースでは、プロファイルを含むファイルを読み込み、既存のサービスにサブスクライブする方法を示します。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 06ae4a5c-f112-4aac-b776-437ac35a8f02
TQID: https://experienceleague.adobe.com/5W-TDffLY-3PfPrNq6AsoiCripfouAusuV8-sO9EYcM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 238
ht-degree: 61%

---

# ファイルを読み込んだ後の特定のサービスへのプロファイルの登録 {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

次の例では、プロファイルを含んだファイルをインポートし、これらのプロファイルを既存のサービスに購読登録する方法を示します。 ファイルをインポートした後で、インポートしたデータをプロファイルとして識別できるように紐付けをおこなう必要があります。 ファイルに重複が含まれていないことを確認するために、データに対して「重複排除 - 重複」アクティビティが実行されます。

ワークフローは次のとおりです。

![](assets/subscription_activity_example1.png)

* [ ファイルの読み込み](../../automating/using/load-file.md) アクティビティは、プロファイルファイルを読み込み、読み込まれた列の構造を定義します。

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

* [紐付け](../../automating/using/reconciliation.md)アクティビティでは、Adobe Campaign データベースのプロファイルディメンションに属するものとして、ファイルのデータが識別されます。 「**[!UICONTROL Identification]**」タブのみ設定します。 プロファイルのメールアドレスに従って、ファイルデータを識別します。

  ![](assets/subscription_activity_example3.png)

* 一時リソースの&#x200B;**電子メール** フィールドに基づく[重複排除](../../automating/using/deduplication.md)は、（紐付けの結果として）重複を識別します。 ファイルからインポートしたデータに重複が含まれている場合、サービスへの購読登録はすべてのデータで失敗します。

  ![](assets/subscription_activity_example5.png)

* [ サブスクリプションサービス ](../../automating/using/subscription-services.md) アクティビティを使用すると、プロファイルを購読する必要があるサービス、購読日に対応するフィールド、購読の送信元を選択できます。

  ![](assets/subscription_activity_example4.png)
