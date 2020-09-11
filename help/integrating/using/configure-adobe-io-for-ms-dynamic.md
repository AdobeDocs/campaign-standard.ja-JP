---
title: Microsoft Dynamics 365 統合用の Adobe IO の設定
description: Microsoft Dynamics 365統合用のAdobeI/Oを構成する方法を説明します。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 801741bd605d11d1c9f88995286ef206dd46470f
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 3%

---


# Microsoft Dynamics 365 統合用の Adobe IO の設定

チャネル間の通信に関するCRMデータをアクティブにします。統合前のセットアップで、新しいAdobeIOプロジェクトを作成し、Microsoft Dynamics 365統合用に構成するために必要な手順を説明します。

## 概要

Adobe Campaign Standard- Microsoft Dynamics 365の統合については、 [このページで説明します](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

この記事の統合前の設定を実行する前に、既にプロビジョニングが完了しており、組織のCampaign Standardインスタンスに対する管理者アクセス権があることを前提としています。  この問題が発生しない場合は、キャンペーンのプロビジョニングを完了するために、Adobeカスタマーケアにお問い合わせいただく必要があります。

>[!CAUTION]
>
>以下に説明する手順は、管理者が実行する必要があります。

## 設定

新しいAdobeI/Oプロジェクトを作成し、統合用に設定する必要があります。

### 新しいプロジェクトの作成

これを行うには、次の手順に従います。

1. 「 [AdobeI/Oコンソール](https://console.adobe.io/home#) 」に移動し、画面の右上にあるドロップダウンメニューからAdobeIMS組織IDを選択します。

1. 次に、の **[!UICONTROL Create new project]** 下のをクリックし **[!UICONTROL Quick Start]**&#x200B;ます。

![](assets/adobeIO1.png)

1. で、 **[!UICONTROL Get started with your new project]**&#x200B;をクリックし **[!UICONTROL Add API]**&#x200B;ます。

![](assets/adobeIO2.png)

1. Adobe CampaignAPIを選択し（下にスクロールする必要がある場合があります）、「Next」をクリックします。

![](assets/adobeIO3.png)

1. 次の画面では、独自の公開鍵をアップロードするか、AdobeI/Oで鍵ペアを生成するかを選択できます。 これらの手順は、後者のオプションに従います。 AdobeI/Oでキーペアを生成する場合は、オプション1をクリックします。次に、「キーペアを生成」ボタンをクリックします。

![](assets/adobeIO4.png)

1. 次の画面で、キーペアzipファイルのダウンロード先を指定し、名前を付けて選択するよう求められます。

ダウンロードしたファイルを解凍すると、公開鍵と秘密鍵が表示されます。 AdobeI/Oは既にAdobeI/Oプロジェクトに公開鍵を適用しています。 秘密鍵は後で保持する必要があります。秘密鍵は、統合ツールの統合前の設定時に使用されます。

1. 「次へ」をクリックして続行します

![](assets/adobeIO5.png)

1. 次の画面で、このプロジェクトに関連付ける製品プロファイルを選択します。

1. タイトルに含まれる製品プロファイルを選択します。キャンペーンインスタンスのテナントID - [!UICONTROL Administrators] — 例：Campaign Standard-キャンペーン — テナントID — 管理者

1. をクリックし [!UICONTROL Save configured API]ます。

![](assets/adobeIO6.png)

1. 次の画面に、新しいAdobeI/Oプロジェクトの詳細が表示されます。

1. 画面の左上にある「プロジェクトへ追加」をクリックし、ドロップダウンから「API」を選択します。

![](assets/adobeIO7.png)

1. 次の画面で、I/OイベントAPIを選択し、[次へ]をクリックする必要があります。

1. 次の画面で、「Save configured API」をクリックします。  プロジェクトの詳細画面に戻ります。

1. 画面の左上にある「プロジェクトへ追加」をクリックし、ドロップダウンから「API」を選択します。

1. 次の画面で、I/O Management APIを選択し、[次へ]をクリックする必要があります。

1. 次の画面で、「Save configured API」をクリックします。

キャンペーンでの統合前の設定が完了しました。  Microsoft Dynamics 365の [統合前のセットアップを完了します](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

**関連トピック**

* [AdobeIO — サービスアカウント統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- APIアクセスの設定](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard- Dynamics 365統合](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)