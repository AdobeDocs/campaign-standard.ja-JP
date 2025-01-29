---
title: Campaign 統合用のMicrosoft Dynamics 365 の設定
description: Campaign 統合用にMicrosoft Dynamics 365 を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: 6947d163119dd6fc5966fdc723530b02bdd4a469
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---

# Adobe Campaign Standardと統合するためのMicrosoft Dynamics 365 の設定

Microsoft Dynamics 365 統合を設定し、Adobe Campaign Standardとのクロスチャネル通信で CRM データをアクティブ化する方法について説明します。

## 概要

Adobe Campaign StandardとMicrosoft Dynamics 365 の統合に関する一般的な説明については、[ このページ ](../../integrating/using/d365-acs-get-started.md) を参照してください。

統合を有効にするには複数のアプリケーションを設定する必要がありますが、この記事では、Dynamics 365 内で必要な手順を重点的に説明します。

## 前提条件

このドキュメントの事前統合設定を実行する前に、既にプロビジョニングが完了し、組織のMicrosoft Dynamics 365 インスタンスに対する管理者アクセス権を持っていることを前提としています。  問題が発生していない場合は、Microsoft カスタマーサポートに連絡して、Dynamics 365 のプロビジョニングを完了する必要があります。

ステージング環境と実稼動環境の両方で統合を設定している場合は、ステージングと実稼動の両方の Dynamics 365 インスタンスに対して、次の手順を実行する必要があります。 以下の手順は、ステージングまたは実稼動の Dynamics 365 インスタンスを設定しているかどうかによって若干異なります（例：実稼動インスタンスの場合は、「prod」（`<stage or prod>`）を選択します）

## アプリケーションと権限の設定

OAuth アクセストークンを使用すると、統合ツールは、web API を介してMicrosoft Dynamics 365 インスタンスで認証を行い、Microsoft Dynamics 365 インターフェイスのタイムラインビューにCampaign Standardエクスペリエンスイベントを投稿できます。

主な手順の概要を次のビデオで説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuth アクセストークンを生成するには、次に示す手順に従います。

### 新しいアプリケーションの登録 {#register-a-new-app}

1. 管理者ログインで [portal.azure.com](https://portal.azure.com){target="_blank"} にログインします。

1. 左側のメニューで **[!UICONTROL Azure Active Directory]** をクリックしてから、表示されるサブメニューの **[!UICONTROL App registrations]** をクリックします。

1. 画面上部の「**[!UICONTROL New registration]**」をクリックします。

1. アプリ登録画面に入力します。

   * 名前：adobe campaign `<stage or prod>`
   * サポートされるアカウントタイプ：**[!UICONTROL Accounts in this organizational directory only]** （デフォルト値）

新しいアプリケーションの作成について詳しくは、[ この節 ](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/quickstart-register-app){target="_blank"} を参照してください。

>[!NOTE]
>
>Microsoft Azure Directory は、一意のアプリケーション（クライアント） ID をアプリに割り当てます。 この ID は、後で Dynamics 365 を設定する際や、統合ツールの設定を実行する際に必要になります。

### クライアント秘密鍵の生成 {#generate-a-client-secret}

1. アプリの概要画面の左側にあるサブメニューで、「**[!UICONTROL Certificates and Secrets > New client secret]**」をクリックします

1. 説明を入力し、期間を設定して、「**[!UICONTROL OK]**」をクリックします。

これで、クライアントシークレットが作成されました。 統合ツールの事前統合設定が完了するまで、一時的に値を保持します。

>[!CAUTION]
>
>統合ツールの事前統合設定を完了するために必要なので、この値を保持します。 その後は取得できません。


### 権限の設定

1. この画面またはアプリの概要画面で、左側のサブメニューの **[!UICONTROL API permissions]** をクリックします。  **[!UICONTROL Add a permission]** をクリックした後、メニューで **[!UICONTROL Dynamics CRM]** を選択する必要があります。

1. 次に、**[!UICONTROL user_impersonation]** のチェックボックスをオンにして、「**[!UICONTROL Add permissions]**」ボタンをクリックします。

権限の設定について詳しくは、[ この節 ](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"} を参照してください。

### アプリユーザーの作成

この新しいユーザーは汎用のユーザーです。 この API はアプリケーションによって使用されます。API を使用したMicrosoft Dynamics 365 の変更は、このユーザーが行います。 作成するには、次の手順に従います。

1. Dynamics 365 インスタンスに移動し、管理者としてログインします。

1. 右上隅の歯車アイコンをクリックし、「**[!UICONTROL Advanced Settings]**」をクリックします。 上部のバナーで、「**[!UICONTROL Settings]**」の横のドロップダウンをクリックし、「**[!UICONTROL Security > Users]**」をクリックします。

1. ドロップダウンメニューで「**[!UICONTROL Application Users]**」を選択します。 「**[!UICONTROL New]**」をクリックします。

1. ユーザーアイコンの横にあるドロップダウンに「**[!UICONTROL USER:APPLICATION USER]**」と表示されていることを確認します。

   新しいユーザーの画面に入力します。  パラメーターの提案：

   * **[!UICONTROL User Name]** （電子メール）: adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;（例：adobe_api_stage@some-company.crm.dynamics.com）
   * **[!UICONTROL Application ID]**: Azure AD に登録したアプリケーションの ID （必須）
   * **[!UICONTROL Application ID URI]** と **[!UICONTROL Azure AD Object ID]** は空白のままにできます
   * **[!UICONTROL Full Name]**:AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**: **[!UICONTROL User Name]** （または必要に応じて管理者の電子メール）と同じ

   アプリユーザーの作成について詳しくは、[ この節 ](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"} を参照してください。

1. ユーザーアイコンをクリックし、Adobe Campaign アイコンをアップロードします。これは、Dynamics 365 に新しいAdobeイベントが表示される際にタイムラインビューに表示されるアイコンです。

1. 上部のリボンで「**[!UICONTROL MANAGE ROLES]**」をクリックして、ユーザーロールリストを開きます。

1. 下にスクロールして、このユーザーの **[!UICONTROL System administrator]** アクセスを選択します。

1. 「**[!UICONTROL OK]**」をクリックします。

### テナント ID を取得 {#get-the-tenant-id}

手順 [ このページ ](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) に従って、テナント ID を見つけます。  この ID は、統合ツールの事前統合設定時に必要になります。

## Microsoft Dynamics 365 のCampaign Standardのインストール {#install-appsource-app}

Dynamics 365 アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. [Microsoft ビジネスアプリ ](https://appsource.microsoft.com/en-us/marketplace/apps) を参照し、検索バーで_Adobe Campaign Standard_を検索します。
または、この [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"} に移動することもできます。
1. 手順に従って、Dynamics 365 インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365 インスタンスに移動し、管理者としてログインします。
1. 右上隅の歯車アイコンをクリックし、「**[!UICONTROL Advanced Settings]**」をクリックします。 上部のバナーで、「**[!UICONTROL Settings]**」の横のドロップダウンをクリックし、「**[!UICONTROL Process Center]**」の下の「**[!UICONTROL Processes]**」をクリックします。
1. タスク **[!UICONTROL Adobe Campaign Email Bounce]** 検索してクリックします。
1. 「**[!UICONTROL Administration]**」タブで、上部のリボンから「**[!UICONTROL Actions]**」をクリックしてオーナーを、以前に作成したAdobeAPI アプリケーションユーザーに変更し、「**[!UICONTROL Assign to another User]**」オプションを選択して、割り当てるドロップダウンから「**[!UICONTROL Adobe API application user]**」を選択します。
1. プロセスを再アクティブ化します。
1. **[!UICONTROL Adobe Campaign Email Click]** のタスクに対して同じ操作を行います。

>[!NOTE]
>
>これらのプロセスをいつでも非アクティブ化したい場合は、この **[!UICONTROL Processes]** の画面で行うことができます。

**関連トピック**

* [Microsoft Dynamics 365 統合用のAdobe Developerの設定 ](../../integrating/using/d365-acs-configure-adobe-io.md) は、統合を設定する次の手順です
* [ セルフサービス統合アプリの基本を学ぶ ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) には、統合を起動および実行する手順の完全なリストが含まれています。
