---
title: Campaign への Adobe Experience Platform オーディエンスの取り込み
description: Adobe Experience Platform オーディエンスをCampaign Standardに取り込む方法について説明します。
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
TQID: https://experienceleague.adobe.com/LdVWEXa90p4yOKgPGG5LUOGRk3xWE8kJ8SkKM7ODBXk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: b70f632b-2cfd-43d0-9266-284281100d70id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 65%

---

# Campaign への Adobe Experience Platform オーディエンスの取り込み {#destinations}

Adobe Experience Platform オーディエンスを Campaign に取り込んでワークフローで使用するには、まず Adobe Campaign を Adobe Experience Platform の&#x200B;**宛先**&#x200B;として接続し、エクスポート対象のセグメントを設定する必要があります。

宛先が設定されると、データはストレージの場所に書き出され、Campaign Standardで専用のワークフローを構築して取り込む必要があります。

## Adobe Campaign を宛先として接続する

Adobe Experience Platform で、Adobe Campaign との接続を設定するには、エクスポートしたセグメントに対してストレージの場所を選択します。 また、この手順では、エクスポートするセグメントを選択し、そこに含める追加の XDM フィールドを指定することもできます。

詳しくは、[宛先のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=ja)を参照してください。

宛先の設定が完了すると、Adobe Experience Platform は指定したストレージの場所にタブ区切りの .txt または .csv ファイルを作成します。 この操作は、24 時間に 1 回実行されるようスケジュールされています。

セグメントをCampaignに取り込むようにCampaign Standard ワークフローを設定できるようになりました。

## Campaign Standardでのインポートワークフローの作成

Campaign Standardが宛先として設定されたら、Adobe Experience Platformによって書き出されたファイルを読み込むための専用ワークフローを構築する必要があります。

これを行うには、**[!UICONTROL Transfer file]** アクティビティを追加して設定する必要があります。 このアクティビティの設定方法について詳しくは、 [こちらの節](../../automating/using/transfer-file.md)を参照してください。

![](assets/rtcdp-transfer-file.png)

その後、必要に応じてワークフローを構築できます（セグメントデータを使用してデータベースを更新する、チャネル間の配信をセグメントに送信するなど）。

例えば、以下のワークフローでは、ストレージの場所から毎日ファイルをダウンロードし、その後、セグメントデータを使用して Campaign データベースを更新します。

![](assets/rtcdp-workflow.png)

データ管理ワークフローの例については、[ ワークフローのユースケース ](../../automating/using/about-workflow-use-cases.md#management)の節を参照してください。

関連トピック ：

* [データ管理アクティビティ](../../automating/using/about-data-management-activities.md)
* [データのインポートおよびエクスポートについて](../../automating/using/about-data-import-and-export.md)
