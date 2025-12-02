---
title: Campaign への Adobe Experience Platform オーディエンスの取り込み
description: Adobe Experience Platform オーディエンスをCampaign Standardに取り込む方法を説明します。
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 64%

---

# Campaign への Adobe Experience Platform オーディエンスの取り込み {#destinations}

Adobe Experience Platform オーディエンスを Campaign に取り込んでワークフローで使用するには、まず Adobe Campaign を Adobe Experience Platform の&#x200B;**宛先**&#x200B;として接続し、エクスポート対象のセグメントを設定する必要があります。

宛先を設定すると、データはストレージの場所に書き出されます。データを取り込むには、Campaign Standardで専用のワークフローを構築する必要があります。

## Adobe Campaign を宛先として接続する

Adobe Experience Platform で、Adobe Campaign との接続を設定するには、エクスポートしたセグメントに対してストレージの場所を選択します。 また、この手順では、エクスポートするセグメントを選択し、そこに含める追加の XDM フィールドを指定することもできます。

詳しくは、[宛先のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=ja)を参照してください。

宛先の設定が完了すると、Adobe Experience Platform は指定したストレージの場所にタブ区切りの .txt または .csv ファイルを作成します。 この操作は、24 時間に 1 回実行されるようスケジュールされています。

次に、セグメントを Campaign に取り込むCampaign Standard ワークフローを設定できます。

## Campaign Standardでのインポートワークフローの作成

Campaign Standardを宛先として設定したら、Adobe Experience Platformによって書き出されたファイルを読み込む専用のワークフローを構築する必要があります。

これを行うには、**[!UICONTROL Transfer file]** アクティビティを追加して設定する必要があります。 このアクティビティの設定方法について詳しくは、 [こちらの節](../../automating/using/transfer-file.md)を参照してください。

![](assets/rtcdp-transfer-file.png)

その後、必要に応じてワークフローを構築できます（セグメントデータを使用してデータベースを更新する、チャネル間の配信をセグメントに送信するなど）。

例えば、以下のワークフローでは、ストレージの場所から毎日ファイルをダウンロードし、その後、セグメントデータを使用して Campaign データベースを更新します。

![](assets/rtcdp-workflow.png)

データ管理ワークフローの例については、[ ワークフローのユースケース ](../../automating/using/about-workflow-use-cases.md#management) の節を参照してください。

関連トピック ： 

* [データ管理アクティビティ](../../automating/using/about-data-management-activities.md)
* [データのインポートおよびエクスポートについて](../../automating/using/about-data-import-and-export.md)
