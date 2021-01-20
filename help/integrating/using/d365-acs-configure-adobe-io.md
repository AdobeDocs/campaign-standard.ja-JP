---
title: Microsoft Dynamics 365 統合用の Adobe IO の設定
description: Microsoft Dynamics 365統合用のAdobeI/Oを構成する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 3%

---


# Microsoft Dynamics 365統合のAdobe Campaign StandardとAdobe I/Oの構成

この記事では、Adobe Campaign StandardとAdobe I/Oを設定して、統合アプリケーションにデータへのアクセスを与える方法を説明します。

## Adobe Campaign Standardを構成{#campaign-standard}

### プロファイル拡張

Adobe Campaign Standardで「プロファイル拡張子」を有効にしてください。   プロファイルリソース内のカスタムフィールドをMicrosoft Dynamics 365と同期するには、これが必要です。   これらを有効にする手順は次のとおりです。

1. 設定/管理/開発/公開に移動します。
1. [パブリケーションの準備]をクリックして、パブリケーションを準備します。
1. 準備が完了したら、「プロファイルとサービスの拡張APIを作成する」を確認し、「公開」をクリックします。

## Adobe I/O の設定 {#adobe-io}

Adobe I/Oでは、Adobe Campaign Standardや他のAdobe製品へのAPIアクセスを有効にできます。   この記事では、Adobe Campaign StandardとMicrosoft Dynamics 365の統合を行ってデータを同期させるための、Adobe I/Oの設定方法について詳しく説明します。

### 概要

この記事の統合前の設定を実行する前に、既にプロビジョニングが完了しており、組織のCampaign Standardインスタンスに対する管理者アクセス権があることを前提としています。  この問題が発生しない場合は、キャンペーンのプロビジョニングを完了するために、Adobeカスタマーケアにお問い合わせいただく必要があります。

>[!CAUTION]
>
>以下に説明する手順は、管理者が実行する必要があります。

### 設定

新しいAdobeI/Oプロジェクトを作成し、統合用に設定する必要があります。

#### 新しいプロジェクトの作成

これを行うには、次の手順に従います。

1. [AdobeI/Oコンソール](https://console.adobe.io/home#)に移動し、画面の右上にあるドロップダウンメニューからAdobeIMS組織IDを選択します。

1. 次に、**[!UICONTROL Quick Start]**&#x200B;の下の&#x200B;**[!UICONTROL Create new project]**&#x200B;をクリックします。

   ![](assets/adobeIO1.png)

1. **[!UICONTROL Get started with your new project]**&#x200B;の下の&#x200B;**[!UICONTROL Add API]**&#x200B;をクリックします。

   ![](assets/adobeIO2.png)

1. Adobe CampaignAPIを選択し（下にスクロールする必要がある場合があります）、**[!UICONTROL Next]**&#x200B;をクリックします。

   ![](assets/adobeIO3.png)

1. 次の画面では、独自の公開鍵をアップロードするか、AdobeI/Oで鍵ペアを生成するかを選択できます。 これらの手順は、後者のオプションに従います。 AdobeI/Oでキーペアを生成する場合は、オプション1をクリックします。次に、「**[!UICONTROL Generate keypair]**」ボタンをクリックします。

   ![](assets/adobeIO4.png)

1. 次の画面で、キーペアzipファイルのダウンロード先を指定し、名前を付けて選択するよう求められます。

ダウンロードしたファイルを解凍すると、公開鍵と秘密鍵が表示されます。 AdobeI/Oは既にAdobeI/Oプロジェクトに公開鍵を適用しています。 秘密鍵は後で保持する必要があります。秘密鍵は、統合ツールの統合前の設定時に使用されます。

1. **[!UICONTROL Next]**&#x200B;をクリックして続行します

   ![](assets/adobeIO5.png)

1. 次の画面で、このプロジェクトに関連付ける製品プロファイルを選択します。 タイトルに含まれる製品プロファイルを選択します。キャンペーンインスタンスのテナントID - [!UICONTROL Administrators]

   例：Campaign Standard-キャンペーン — テナントID — 管理者

1. 「**[!UICONTROL Save configured API]**」をクリックします。

   ![](assets/adobeIO6.png)

1. 次の画面に、新しいAdobeI/Oプロジェクトの詳細が表示されます。 画面の左上にある&#x200B;**[!UICONTROL Add to Project]**&#x200B;をクリックし、ドロップダウンから&#x200B;**API**&#x200B;を選択します。

   ![](assets/adobeIO7.png)

1. 次の画面で、I/OイベントAPIを選択し、**[!UICONTROL Next]**&#x200B;をクリックする必要があります。

1. 次の画面で、**[!UICONTROL Save the configured API]**&#x200B;をクリックします。  プロジェクトの詳細画面に戻ります。

1. 次に、画面の左上にある&#x200B;**[!UICONTROL Add to Project]**&#x200B;をクリックし、ドロップダウンから&#x200B;**API**&#x200B;を選択します。

1. 次の画面で、I/O Management APIを選択し、**[!UICONTROL Next]**&#x200B;をクリックする必要があります。

1. 次の画面で、**[!UICONTROL Save the configured API]**&#x200B;をクリックします。

キャンペーンでの統合前の設定が完了しました。

**関連トピック**

* [Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) 統合用のAdobeI/Oを構成するには、統合のセットアップの次の手順を実行します
* [統合セルフサービスアプリケーションの](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 概要には、統合を導入および実行するための手順の完全なリストが含まれています。


* [AdobeIO — サービスアカウント統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- APIアクセスの設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365統合](../../integrating/using/d365-acs-configure-d365.md)
