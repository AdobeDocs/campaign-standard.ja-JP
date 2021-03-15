---
solution: Campaign Standard
product: campaign
title: Campaign 統合用の Microsoft Dynamics 365 の設定
description: Microsoft Dynamics 365 forキャンペーン統合を構成する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM統合
role: Data Architect
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 1%

---


# Adobe Campaign Standardとの統合用にMicrosoft Dynamics 365を構成する

Microsoft Dynamics 365統合を構成し、Adobe Campaign Standardとのチャネル間通信でCRMデータをアクティブにする方法を説明します。

## 概要

Microsoft Dynamics 365とのAdobe Campaign Standard統合の一般的な説明は、[このページ](../../integrating/using/d365-acs-get-started.md)で説明されています。

統合を有効にするには複数のアプリケーションを構成する必要がありますが、この記事では、Dynamics 365内で必要な手順に焦点を当てます。

## 前提条件

このドキュメントで統合前のセットアップを実行する前に、既にプロビジョニングが完了しており、組織のMicrosoft Dynamics 365インスタンスに対する管理者アクセス権があることを前提としています。  この問題が発生しない場合は、Dynamics 365のプロビジョニングを完了するには、Microsoftカスタマーサポートに連絡する必要があります。

ステージングと実稼働の両方の環境に対して統合を設定する場合は、ステージングと実稼働の両方のDynamics 365インスタンスに対して、次の手順を実行する必要があります。 以下の手順は、ステージまたは実稼働のDynamics 365インスタンスを設定する場合に少し異なります（例：実稼働インスタンスの場合は、`<stage or prod>`に対して「prod」を選択します）

## アプリケーションと権限の設定

OAuthアクセストークンを使用すると、Campaign StandardエクスペリエンスのイベントをMicrosoft Dynamics 365インターフェイスのタイムライン表示にポストするために、統合ツールがWeb APIを介してMicrosoft Dynamics 365インスタンスを認証できます。

主な手順を次のビデオで説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuthアクセストークンを生成するには、次の手順に従います。

### 新しいアプリケーションを登録{#register-a-new-app}

1. 管理者ログインで、portal.azure.comにログインします。

1. 左側のメニューで&#x200B;**[!UICONTROL Azure Active Directory]**&#x200B;をクリックします。次に、表示されるサブメニューの&#x200B;**[!UICONTROL App registrations]**&#x200B;をクリックします。

1. 画面上部の&#x200B;**[!UICONTROL New registration]**&#x200B;をクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. アプリの登録画面に次の情報を入力します。

   * 名前：アドビキャンペーン`<stage or prod>`
   * サポートされるアカウントの種類：**[!UICONTROL Accounts in this organizational directory only]**（デフォルト値）

新しいアプリケーションの作成について詳しくは、[このセクション](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)を参照してください。

>[!NOTE]
>
>Microsoft Azure Directoryは、一意のアプリケーション（クライアント） IDをアプリに割り当てます。 このIDは、後でDynamics 365の設定で必要になります。また、統合ツールの設定を実行する場合にも必要になります。

### クライアントシークレットの生成{#generate-a-client-secret}

1. アプリの概要画面の左側のサブメニューで、「**[!UICONTROL Certificates and Secrets > New client secret]**」をクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 説明を入力し、長さを設定して、**[!UICONTROL OK]**&#x200B;をクリックします。

これで、クライアントシークレットが作成されます。 統合ツールの統合前の設定を完了するために、値を一時的に保持します。

>[!CAUTION]
>
>統合ツールの統合前の設定を完了するために必要な場合は、この値をそのままにしてください。 後で取得することはできません。


### 権限の設定

1. この画面またはアプリの概要画面で、左側のサブメニューの&#x200B;**[!UICONTROL API permissions]**&#x200B;をクリックします。  「**[!UICONTROL Add a permission]**」をクリックした後、メニューで「**[!UICONTROL Dynamics CRM]**」を選択する必要があります。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 次に、**[!UICONTROL user_impersonation]**&#x200B;のチェックボックスをオンにし、**[!UICONTROL Add permissions]**&#x200B;ボタンをクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

権限の設定について詳しくは、[このセクション](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)を参照してください。

### アプリユーザーの作成

この新しいユーザーは汎用ユーザーです。 これは、次のアプリケーションで使用されます。APIを使用してMicrosoft Dynamics 365に変更を加えると、このユーザーが行います。 作成するには、次の手順に従います。

1. Dynamics 365インスタンスに移動し、管理者としてログインします。

1. 右上隅の歯車アイコンをクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。 上部のバナーで、**[!UICONTROL Settings]**&#x200B;の横のドロップダウンをクリックし、**[!UICONTROL Security > Users]**&#x200B;をクリックします。

1. ドロップダウンメニューをクリックして&#x200B;**[!UICONTROL Application Users]**&#x200B;に移動します。 「**[!UICONTROL New]**」をクリックします。

1. ユーザーアイコンの横のドロップダウン「**[!UICONTROL USER:APPLICATION USER]**」と表示されていることを確認します。

   新しいユーザーの画面に入力します。  パラメーターの提案：

   * **[!UICONTROL User Name]** （電子メール）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例：adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:Azure ADに登録したアプリケーションのID （必須）
   * **[!UICONTROL Application ID URI]**&#x200B;と&#x200B;**[!UICONTROL Azure AD Object ID]**&#x200B;は空欄でかまいません
   * **[!UICONTROL Full Name]**:AdobeAPI  `<stage or prod>`
   * **[!UICONTROL Email]**:同じ **[!UICONTROL User Name]** （必要に応じて管理者の電子メール）

   アプリのユーザー作成について詳しくは、[このセクション](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)を参照してください。

1. ユーザーアイコンをクリックし、Adobe Campaignアイコンをアップロードします。これは、Dynamics 365で新しいAdobeイベントが表示された場合に、タイムライン表示に表示されるアイコンです。

1. 上部のリボンの&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;をクリックして、ユーザーの役割リストを開きます。

1. 下にスクロールし、このユーザーの&#x200B;**[!UICONTROL System administrator]**&#x200B;アクセスを選択します。

1. 「**[!UICONTROL OK]**」をクリックします。

### テナントIDを取得{#get-the-tenant-id}

このページ](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)の指示[に従って、テナントIDを探します。  統合ツールの統合前の設定時に、このIDが必要になります。

## Microsoft Dynamics 365のCampaign Standardのインストール{#install-appsource-app}

Dynamics 365アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. 次のリンクに移動します。[https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps)を検索し、検索バーで&#x200B;_Dynamics 365のAdobe Campaign_を検索します。
または、この[リンク](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)に移動します。
1. 手順に従って、Dynamics 365インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365インスタンスに移動し、管理者としてサインインします。
1. 右上隅の歯車アイコンをクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。 上部のバナーで、**[!UICONTROL Settings]**&#x200B;の横のドロップダウンをクリックし、**[!UICONTROL Process Center]**&#x200B;の下の&#x200B;**[!UICONTROL Processes]**&#x200B;をクリックします。
1. **[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;タスクを探してクリックします。
1. 「**[!UICONTROL Administration]**」タブで、所有者を上部のAdobeから「**[!UICONTROL Actions]**」をクリックして前に作成したリボンAPIアプリケーションユーザーに変更し、「**[!UICONTROL Assign to another User]**」オプションを選択して、割り当てるドロップダウンから「**[!UICONTROL Adobe API application user]**」を選択します。
1. プロセスを再アクティブ化します。
1. **[!UICONTROL Adobe Campaign Email Click]**&#x200B;タスクも同じようにします。

>[!NOTE]
>
>これらのプロセスをいつでも非アクティブにしたい場合は、この&#x200B;**[!UICONTROL Processes]**&#x200B;画面で行うことができます。

**関連トピック**

* [Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) 統合用のAdobeI/Oを構成するには、統合のセットアップの次の手順を実行します
* [セルフサービス統合](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) アプリケーションを使用し始める前に、統合を導入および導入するための手順をリストしています。
