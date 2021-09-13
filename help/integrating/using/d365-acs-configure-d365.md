---
title: Campaign 統合用の Microsoft Dynamics 365 の設定
description: Campaign統合用にMicrosoft Dynamics 365を設定する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 1%

---

# Adobe Campaign Standardとの統合のためのMicrosoft Dynamics 365の設定

Adobe Campaign Standardとのクロスチャネル通信でMicrosoft Dynamics 365統合を設定し、CRMデータをアクティブ化する方法について説明します。

## 概要

Adobe Campaign StandardとMicrosoft Dynamics 365の統合に関する一般的な説明は、[このページ](../../integrating/using/d365-acs-get-started.md)で説明しています。

統合を有効にするには、複数のアプリケーションを設定する必要がありますが、この記事では、Dynamics 365内で必要な手順について説明します。

## 前提条件

このドキュメントで事前統合の設定を実行する前に、既にプロビジョニング済みで、組織のMicrosoft Dynamics 365インスタンスに対する管理者アクセス権があることを前提としています。  この問題が発生していない場合は、Microsoftカスタマーサポートに連絡して、Dynamics 365プロビジョニングを完了する必要があります。

ステージング環境と実稼動環境の両方に統合を設定する場合は、ステージング環境と実稼動環境の両方に対して以下の手順を実行する必要があります。 以下の手順は、ステージングインスタンスと実稼動Dynamics 365インスタンスのどちらを設定するかによって多少異なります（例えば、実稼動インスタンスの場合は、`<stage or prod>`に対して「prod」を選択します）。

## アプリケーションと権限の設定

OAuthアクセストークンを使用すると、統合ツールでWeb APIを介してMicrosoft Dynamics 365インスタンスを認証し、Campaign StandardエクスペリエンスイベントをMicrosoft Dynamics 365インターフェイスのタイムラインビューに投稿できます。

主な手順については、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuthアクセストークンを生成するには、以下の手順に従います。

### 新しいアプリの登録 {#register-a-new-app}

1. 管理者ログインで、 portal.azure.comにログインします。

1. 左側のメニューの&#x200B;**[!UICONTROL Azure Active Directory]**&#x200B;をクリックします。次に、表示されるサブメニューの「**[!UICONTROL App registrations]**」をクリックします。

1. 画面上部の&#x200B;**[!UICONTROL New registration]**&#x200B;をクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. アプリ登録画面に入力します。

   * 名前：adobe campaign `<stage or prod>`
   * サポートされているアカウントの種類：**[!UICONTROL Accounts in this organizational directory only]**（デフォルト値）

新しいアプリケーションの作成について詳しくは、[この節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)を参照してください。

>[!NOTE]
>
>Microsoft Azure Directoryは、アプリに一意のアプリケーション（クライアント）IDを割り当てます。 このIDは、後でDynamics 365の設定で必要になります。また、統合ツールの設定を実行する際にも必要になります。

### クライアント秘密鍵の生成 {#generate-a-client-secret}

1. アプリの概要画面の左側にあるサブメニューで、「**[!UICONTROL Certificates and Secrets > New client secret]**」をクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 説明を入力し、期間を設定して、「**[!UICONTROL OK]**」をクリックします。

これで、クライアント秘密鍵が作成されました。 統合ツールの統合前の設定が完了するまで、値を一時的に保持します。

>[!CAUTION]
>
>この値は、統合ツールの事前統合設定を完了する必要があるので、そのままにします。 後で取得することはできません。


### 権限の設定

1. この画面またはアプリの概要画面で、左側のサブメニューの「**[!UICONTROL API permissions]**」をクリックします。  「**[!UICONTROL Add a permission]**」をクリックした後、メニューから「**[!UICONTROL Dynamics CRM]**」を選択する必要があります。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 次に、**[!UICONTROL user_impersonation]**&#x200B;のチェックボックスをオンにし、**[!UICONTROL Add permissions]**&#x200B;ボタンをクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

権限の設定について詳しくは、[この節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)を参照してください。

### アプリユーザーの作成

この新しいユーザーは汎用のユーザーです。 アプリケーションで使用されます。APIを使用したMicrosoft Dynamics 365の変更は、このユーザーがおこないます。 作成するには、次の手順に従います。

1. Dynamics 365インスタンスに移動し、管理者としてログインします。

1. 右上隅のギアアイコンをクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。 上部のバナーで、**[!UICONTROL Settings]**&#x200B;の横にあるドロップダウンをクリックし、「**[!UICONTROL Security > Users]**」をクリックします。

1. ドロップダウンメニューをクリックして、**[!UICONTROL Application Users]**&#x200B;に移動します。 「**[!UICONTROL New]**」をクリックします。

1. ユーザーアイコンの横にあるドロップダウンが&#x200B;**[!UICONTROL USER:APPLICATION USER]**&#x200B;と表示されていることを確認します。

   新しいユーザーの画面に入力します。  パラメーターの候補：

   * **[!UICONTROL User Name]** （電子メール）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`」(例：adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:Azure ADに登録したアプリケーションのID（必須）
   * 空白の&#x200B;**[!UICONTROL Application ID URI]**&#x200B;と&#x200B;**[!UICONTROL Azure AD Object ID]**&#x200B;を残すことができます
   * **[!UICONTROL Full Name]**:AdobeAPI  `<stage or prod>`
   * **[!UICONTROL Email]**:と同 **[!UICONTROL User Name]** じ（必要に応じて管理者の電子メール）

   アプリユーザーの作成について詳しくは、[この節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)を参照してください。

1. ユーザーアイコンをクリックし、 Adobe Campaignアイコンをアップロードします。これは、Dynamics 365に新しいAdobeイベントが表示されたときにタイムラインビューに表示されるアイコンです。

1. 上部のリボンの&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;をクリックして、ユーザーの役割のリストを開きます。

1. 下にスクロールし、このユーザーの&#x200B;**[!UICONTROL System administrator]**&#x200B;アクセス権を選択します。

1. 「**[!UICONTROL OK]**」をクリックします。

### テナントIDの取得 {#get-the-tenant-id}

このページ](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)の手順[に従って、テナントIDを見つけます。  このIDは、統合ツールで統合前の設定をおこなう際に必要になります。

## Microsoft Dynamics 365用Campaign Standardのインストール {#install-appsource-app}

Dynamics 365アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. 次のリンクに移動します。[https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps)を検索し、検索バーで&#x200B;_Adobe Campaign for Dynamics 365_を検索します。
または、この[リンク](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)に移動することもできます。
1. 手順に従って、Dynamics 365インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365インスタンスに移動し、管理者としてログインします。
1. 右上隅のギアアイコンをクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。 上部のバナーで、**[!UICONTROL Settings]**&#x200B;の横にあるドロップダウンをクリックし、**[!UICONTROL Process Center]**&#x200B;の下の&#x200B;**[!UICONTROL Processes]**&#x200B;をクリックします。
1. **[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;タスクを検索してクリックします。
1. 「**[!UICONTROL Administration]**」タブで、上部のリボンの「**[!UICONTROL Actions]**」をクリックして前に作成したAdobeAPIアプリケーションユーザーに所有者を変更し、「**[!UICONTROL Assign to another User]**」オプションを選択して、割り当てるドロップダウンから「**[!UICONTROL Adobe API application user]**」を選択します。
1. プロセスを再アクティブ化します。
1. **[!UICONTROL Adobe Campaign Email Click]**&#x200B;タスクに対しても同じ操作を行います。

>[!NOTE]
>
>これらのプロセスをいつでも非アクティブにしたい場合は、この&#x200B;**[!UICONTROL Processes]**&#x200B;画面で実行できます。

**関連トピック**

* [AdobeI/OをMicrosoft Dynamics 365統合用に設](../../integrating/using/d365-acs-configure-adobe-io.md) 定する手順は、統合を設定する次の手順です
* [セルフサービス統合の概要に](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) は、統合を導入するための手順の完全なリストが含まれています。
