---
title: Microsoft Dynamics 365 統合用の Adobe IO の設定
description: Microsoft Dynamics 365統合用のAdobe IOの設定方法を説明します。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e05dafb087c43a13c60d6bb2f54d0e44455ea8d

---


# Microsoft Dynamics 365 統合用の Adobe IO の設定

クロスチャネル通信でのCRMデータのアクティブ化：microsoft Dynamics 365用の新しい統合を作成するために、プロビジョニング後に必要な手順を説明します。

## 概要

Adobe Campaign標準 — Microsoft Dynamics 365の統合については、このページで説 [明します](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

この記事のプロビジョニング後の手順を実行する前に、既にプロビジョニング済みで、組織のCampaign Standardインスタンスに対する管理者アクセス権を持っていることを前提としています。  この問題が発生しない場合は、アドビカスタマーケアに連絡して、アドビのプロビジョニングを完了する必要があります。キャンペーンのプロビジョニング

>[!CAUTION]
>
>以下に説明する手順は、管理者が実行する必要があります。

## 設定

APIアクセスを設定し、Unifi用の新しい統合を設定する必要があります。

設定はAdobe IOで行われます。次のビデオに示すように、Unifi用の新しい統合を作成する必要があります。

>[!VIDEO](https://video.tv.adobe.com/v/27308)

### 新しい統合の作成

これを行うには、次の手順に従います。

1. 「 [Adobe IMS Console](https://console.adobe.io/home#) 」に移動し、左上のドロップダウンメニューからAdobe IMS組織IDを選択します（下記を参照）。

右上のをク **[!UICONTROL New Integration]** リックします。

>[!NOTE]
>
>これが組織の最初の統合である場合、のボタンがページの中 **[!UICONTROL New Integration]** 央にある可能性があります。

1. を選択し、 **[!UICONTROL Access an API]** をクリックしま **[!UICONTROL Continue]**&#x200B;す。

1. セクション __ から「 **[!UICONTROL Experience Cloud]** Adobe Campaign」を選択し、をクリックしま **[!UICONTROL Continue]**&#x200B;す。

1. 証明書とキーを生成します。

**MacOSおよびLinuxプラットフォームの場合**

ターミナルアプリケーションを開き、次のコマンドを実行します。

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Windowsプラットフォームの場合**

* 公開証明書を生成するには、opensslクライアントをダウンロードします(例： [Openssl Windowsクライアント](https://bintray.com/vszakats/generic/download_file?file_path=openssl-1.1.1-win64-mingw.zip))。

* zipファイルからフォルダを抽出します。

* コマンドラインプロンプトを開き、次のコマンドを実行します。

以下 `<containing folder path>` を抽出したフォルダーのパスに置き換えます(例：C:\Users\labuser\Downloads\openssl-1.1.1-win64-mingw\openssl-1.1.1-win64-mingw)。

```
set OPENSSL_CONF=<containing folder path>/openssl.cnf
 
cd <containing folder path>/
 
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**すべてのプラットフォーム**

プロンプトに従って、証明書の要求を完了します。

```
Generating a 2048 bit RSA private key
 
.................+++
 
.......................................+++
 
writing new private key to 'private.key'
 
-----
 
You are about to be asked to enter information that will be incorporated
 
into your certificate request.
 
What you are about to enter is what is called a Distinguished Name or a DN.
 
There are quite a few fields but you can leave some blank
 
For some fields there will be a default value,
 
If you enter '.', the field will be left blank.
 
-----
```

情報を入力すると、次の2つのファイルが生成されます。 **[!UICONTROL certificate_pub.crt]** と **[!UICONTROL private.key]**

* **[!UICONTROL certificate_pub.crt]** は365日で有効期限が切れます。 上記のopensslコマンドで日数の値を変更することで有効期限を変更できますが、証明書を定期的に回転するのがセキュリティ上の利点です。

* **[!UICONTROL certificate_pub.crt]** が次の画面で使用され、Adobe I/Oコンソールの統合が完了します。

>[!NOTE]
>
> **[!UICONTROL private.key]** は、後でUnifiのプロビジョニング後の手順で使用されます。

1. Adobe I/Oコンソールに戻り、統合の名前と説明を入力します。

1. アップロード **[!UICONTROL certificate_pub.crt]**

1. タイトルに含まれるプロファイルを選択します。

   * 組織インスタンスのキャンペーンID
   * **[!UICONTROL Administrators]**

例： Campaign Standard-キャンペーン組織ID — 管理者

をクリックしま **[!UICONTROL Create Integration]**&#x200B;す。

![](assets/do-not-localize/MSdynACSIntegration-4B.png)

### 統合の詳細の設定

1. 選択 **[!UICONTROL Continue to Integration Details]**

統合の詳細を確認します。  Unifiのプロビジョニング後の手順を実行する場合は、再度参照する必要があります。

![](assets/do-not-localize/MSdynACSIntegration-5.png)

1. タブをクリックし、 **[!UICONTROL Services]** サービスを追 **[!UICONTROL I/O Events]** 加し **[!UICONTROL I/O Management API]** ます。  サービスを追加するには、ラジオボタンをクリックし、次に **[!UICONTROL Add service]**。  これは、各サービスに対して個別に行います。

完了したら、次の図のようにサービスの上部が表示されます。 JWTとアクセストークンの生成時に、a-onセクションを完了する必要はありません。

![](assets/do-not-localize/MSdynACSIntegration-6.png)

現在は、キャンペーンでの後処理が完了しています。  Microsoft Dynamics 365のプロビ [ジョニング後の手順を実行します](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

**関連トピック**

* [Adobe IO — サービスアカウント統合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- APIアクセスの設定](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard- Dynamics 365統合](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
