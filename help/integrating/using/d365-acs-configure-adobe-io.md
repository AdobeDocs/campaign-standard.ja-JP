---
title: Microsoft Dynamics 365 統合用のAdobe Developerの設定
description: Microsoft Dynamics 365 統合用のAdobe Developerを設定する方法について説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Microsoft Dynamics 365 統合用のAdobe Campaign StandardとAdobe Developerの設定

この記事では、Adobe Campaign StandardとAdobe I/Oを設定して、統合アプリケーションにデータへのアクセスを許可する方法について説明します。

## Adobe Campaign Standardの設定 {#campaign-standard}

### プロファイル拡張

Adobe Campaign Standardで「プロファイル拡張機能」を有効にしてください。   これは、プロファイルリソースのカスタムフィールドをMicrosoft Dynamics 365 から同期するために必要です。   有効にする手順は次のとおりです。

1. 設定/管理/開発/公開に移動します。
1. 「パブリケーションの準備」をクリックして、パブリケーションを準備します。
1. 準備が完了したら、「Profiles &amp; Services Ext API を作成」をチェックし、「Publish」をクリックします。

## Adobe I/Oの設定 {#adobe-io}

Adobe I/Oを使用すると、Adobe Campaign Standardや他のAdobe製品への API アクセスを有効にできます。   この記事では、Adobe Campaign StandardをMicrosoft Dynamics 365 と統合してデータをAdobe I/Oするためのアクセス権を付与するために同期を設定する方法について詳しく説明します。

### 概要

この記事では、事前統合設定を実行する前に、既にプロビジョニングされており、組織のCampaign Standardインスタンスへの管理者アクセス権を持っていることを前提としています。  まだ実行されていない場合は、Adobeカスタマーケアに連絡して Campaign のプロビジョニングを完了してください。

>[!CAUTION]
>
>以下に説明する手順は、管理者が実行する必要があります。

### 設定

新しいAdobe Developer プロジェクトを作成し、統合用に設定する必要があります。

#### 新規プロジェクトの作成

それには、次の手順に従います。

1. [Adobe Developer Console](https://console.adobe.io/home#) に移動し、画面右上のドロップダウンメニューからAdobe組織 ID を選択します。

1. 次に、「**[!UICONTROL Quick Start]**」の下の「**[!UICONTROL Create new project]**」をクリックします。

   ![](assets/adobeIO1.png)

1. [**[!UICONTROL Get started with your new project]**] で、[**[!UICONTROL Add API]**] をクリックします。

   ![](assets/adobeIO2.png)

1. Adobe Campaignを選択し、「**[!UICONTROL Next]**」をクリックします。

   ![](assets/adobeIO3.png)

1. 次の画面で、認証のタイプを選択するオプションがあります。 OAuth サーバー間またはサービスアカウント（JWT）のいずれかを選択できます。 サービスアカウント（JWT）資格情報は、新しいプロジェクトでは推奨されなくなり、新しい OAuth サーバー間資格情報に置き換わるために非推奨になることに注意してください。 このガイドで説明する手順は、OAuth サーバー間認証にのみ適用されます。

   ![](assets/adobeIO4.png)

1. 次の画面で、このプロジェクトに関連付ける製品プロファイルを選択します。 次のタイトルで、を含む製品プロファイルを選択します。Campaign インスタンスのテナント ID - [!UICONTROL Administrators]

   例：Campaign Standard- your-campaign-tenantID - Administrators

1. 「**[!UICONTROL Save configured API]**」をクリックします。

   ![](assets/adobeIO5.png)

1. 次の画面では、新しいAdobe Developer プロジェクトの詳細が表示されます。 画面の左上にある **[!UICONTROL Add to Project]** をクリックし、ドロップダウンから **API** を選択します。

   ![](assets/adobeIO6.png)

1. 次の画面で、I/O Events API を選択し、「**[!UICONTROL Next]**」をクリックする必要があります。

1. 次の画面で、「**[!UICONTROL Save the configured API]**」をクリックします。  プロジェクトの詳細画面に戻ります。

1. 前と同じように、画面の左上にある **[!UICONTROL Add to Project]** をクリックし、ドロップダウンから「**API**」を選択します。

1. 次の画面で、「I/O Management API」を選択し、「**[!UICONTROL Next]**」をクリックする必要があります。

1. 次の画面で、「**[!UICONTROL Save the configured API]**」をクリックします。

これで、Campaign の統合前設定が完了しました。

**関連トピック**

* [Microsoft Dynamics 365 統合用のAdobe Developerの設定 ](../../integrating/using/d365-acs-configure-adobe-io.md) は、統合を設定する次の手順です
* [ 統合セルフサービスアプリケーションの概要 ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) には、統合を実行する手順の完全なリストが含まれています。
* [Adobe Developer - サービス アカウントの統合 ](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API アクセスの設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365 統合](../../integrating/using/d365-acs-configure-d365.md)
* [JWT から OAuth サーバー間への資格情報の移行 ](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) には、JWT から OAuth サーバー間に資格情報を移行する手順が含まれています。
