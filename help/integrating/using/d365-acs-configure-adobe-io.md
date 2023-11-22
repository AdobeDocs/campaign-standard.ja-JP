---
title: Microsoft Dynamics 365 統合用のAdobe Developerの設定
description: Microsoft Dynamics 365 統合用にAdobe Developerを設定する方法を説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 1%

---

# Microsoft Dynamics 365 統合用のAdobe Campaign StandardとAdobe Developerの設定

この記事では、統合アプリケーションがデータにアクセスできるようにAdobe Campaign StandardとAdobe I/Oを設定する方法について説明します。

## Adobe Campaign Standardの設定 {#campaign-standard}

### プロファイル拡張

Adobe Campaign Standardで「プロファイル拡張」を有効にしてください。   これは、プロファイルリソースのカスタムフィールドをMicrosoft Dynamics 365 から同期するために必要です。   これらを有効にする手順は次のとおりです。

1. 設定/管理/開発/公開に移動します。
1. 「公開を準備」をクリックして、公開を準備します。
1. 準備が完了したら、「Profiles &amp; Services Ext API の作成」をチェックし、「公開」をクリックします。

## Adobe I/O の設定 {#adobe-io}

Adobe I/Oを使用すると、Adobe Campaign Standardおよびその他のAdobe製品への API アクセスを有効にできます。   この記事では、Adobe Campaign StandardとMicrosoft Dynamics 365 の統合にデータを同期するためのアクセス権を付与するためのAdobe I/Oの設定方法について詳しく説明します。

### 概要

この記事の統合前の設定を実行する前に、既にプロビジョニング済みで、組織のCampaign Standardインスタンスへの管理者アクセス権を持っていることを前提としています。  この問題が発生していない場合は、Adobeカスタマーケアに連絡して、Campaign のプロビジョニングを完了する必要があります。

>[!CAUTION]
>
>以下に説明する手順は、管理者が実行する必要があります。

### 設定

新しいAdobe Developerプロジェクトを作成し、統合用に設定する必要があります。

#### 新しいプロジェクトを作成

これをおこなうには、次の手順に従います。

1. に移動します。 [Adobe Developer Console](https://console.adobe.io/home#) を選択し、画面の右上にあるドロップダウンメニューからAdobe組織 ID を選択します。

1. 次に、「 **[!UICONTROL Create new project]** under **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. の下 **[!UICONTROL Get started with your new project]**&#x200B;をクリックし、 **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Adobe Campaignを選択し、 **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. 次の画面では、認証の種類を選択するオプションが表示されます。 「OAuth サーバー間」または「サービスアカウント (JWT)」を選択できます。 サービスアカウント (JWT) 資格情報は、新しいプロジェクトでは推奨されなくなり、新しい OAuth サーバー間資格情報に置き換えられるようになりました。 このガイドで説明する手順は、OAuth サーバー間認証にのみ適用されます。

   ![](assets/adobeIO4.png)

1. 次の画面で、このプロジェクトに関連付ける製品プロファイルを選択します。 タイトルにが含まれる製品プロファイルを選択します。 Campaign インスタンスのテナント ID - [!UICONTROL Administrators]

   例：Campaign Standard- your-campaign-tenantID - Administrators

1. 「**[!UICONTROL Save configured API]**」をクリックします。

   ![](assets/adobeIO5.png)

1. 次の画面に、新しいAdobe Developerプロジェクトの詳細が表示されます。 クリック **[!UICONTROL Add to Project]** 画面の左上にあるをクリックし、「 **API** 」をドロップダウンから選択します。

   ![](assets/adobeIO6.png)

1. 次の画面で、I/O イベント API を選択し、「 **[!UICONTROL Next]**.

1. 次の画面で、 **[!UICONTROL Save the configured API]**.  プロジェクトの詳細画面に戻ります。

1. 今すぐクリック **[!UICONTROL Add to Project]** 画面の左上にあるをクリックし、「 **API** をドロップダウンから選択します。

1. 次の画面で、I/O Management API を選択し、 **[!UICONTROL Next]**.

1. 次の画面で、 **[!UICONTROL Save the configured API]**.

これで、Campaign の統合前の設定が完了しました。

**関連トピック**

* [Microsoft Dynamics 365 統合用のAdobe Developerの設定](../../integrating/using/d365-acs-configure-adobe-io.md) は、統合を設定する次の手順です。
* [統合セルフサービスアプリケーションの概要](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) には、統合を導入および実行する手順の完全なリストが含まれています。
* [Adobe Developer — サービスアカウントの統合](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API アクセスの設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365 統合](../../integrating/using/d365-acs-configure-d365.md)
* [JWT から OAuth サーバー間への認証情報の移行](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) 資格情報を JWT から OAuth サーバー間に移行する手順について説明します。
