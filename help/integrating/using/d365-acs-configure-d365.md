---
title: Campaign統合用のMicrosoft Dynamics 365の設定
description: Campaign統合用にMicrosoft Dynamics 365を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
TQID: https://experienceleague.adobe.com/WpIRNQtob-mtXSfXYBklwkcObjScygqUrHWRnJOscrM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 961
ht-degree: 1%

---

# Adobe Campaign Standardとの統合用にMicrosoft Dynamics 365を設定します

Microsoft Dynamics 365との連携を設定し、Adobe Campaign Standardを使用してクロスチャネルコミュニケーションでCRM データをアクティブ化する方法について説明します。

## 概要

Adobe Campaign StandardとMicrosoft Dynamics 365の統合に関する一般的な説明については、[このページ &#x200B;](../../integrating/using/d365-acs-get-started.md)を参照してください。

統合を有効にするには、複数のアプリケーションを設定する必要がありますが、この記事では、Dynamics 365内で必要な手順に焦点を当てます。

## 前提条件

このドキュメントで統合前の設定を実行する前に、既にプロビジョニング済みで、組織のMicrosoft Dynamics 365 インスタンスへの管理者アクセス権を持っていることが前提となります。  この問題が発生しない場合は、Microsoft カスタマーサポートに連絡してDynamics 365 プロビジョニングを完了する必要があります。

ステージング環境と実稼動環境の両方に対して統合を設定する場合は、ステージング環境と実稼動環境の両方に対して次の手順を実行する必要があります。 以下のいくつかの手順は、ステージまたは実稼動Dynamics 365 インスタンスを設定する場合（例：実稼動インスタンスの場合、`<stage or prod>`に「prod」を選択）によって若干異なります

## アプリケーションと権限の設定

OAuth アクセストークンを使用すると、統合ツールはweb APIを介してMicrosoft Dynamics 365 インスタンスで認証し、Campaign Standard エクスペリエンスイベントをMicrosoft Dynamics 365 インターフェイスのタイムラインビューに投稿できます。

主な手順については、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuth アクセストークンを生成するには、次の手順に従います。

### 新しいアプリケーションを登録 {#register-a-new-app}

1. 管理者ログインで、[portal.azure.com](https://portal.azure.com){target="_blank"}にログインします。

1. 左側のメニューの&#x200B;**[!UICONTROL Azure Active Directory]**&#x200B;をクリックし、表示されるサブメニューの&#x200B;**[!UICONTROL App registrations]**&#x200B;をクリックします。

1. 画面上部の「**[!UICONTROL New registration]**」をクリックします。

1. アプリ登録画面に入力します。

   * 名前：adobe campaign `<stage or prod>`
   * サポートされているアカウントの種類：**[!UICONTROL Accounts in this organizational directory only]** （既定値）

新しいアプリケーションの作成について詳しくは、[この節](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/quickstart-register-app){target="_blank"}を参照してください。

>[!NOTE]
>
>Microsoft Azure Directoryは、アプリケーションに一意のアプリケーション（クライアント） IDを割り当てます。 このIDは、Dynamics 365の設定と、統合ツールの設定を実行する際に後で必要になります。

### クライアントシークレットを生成 {#generate-a-client-secret}

1. アプリの概要画面で、左側のサブメニューで「**[!UICONTROL Certificates and Secrets > New client secret]**」をクリックします

1. 説明を入力し、期間を設定して、**[!UICONTROL OK]**&#x200B;をクリックします。

これで、クライアントシークレットが作成されました。 統合ツールの統合前セットアップを完了するために、一時的に値を保持します。

>[!CAUTION]
>
>統合ツールの事前設定を完了するために必要になる値を保持します。 後で取得することはできません。


### 権限の設定

1. この画面またはアプリの概要画面で、左側のサブメニューの「**[!UICONTROL API permissions]**」をクリックします。  **[!UICONTROL Add a permission]**&#x200B;をクリックした後、メニューで&#x200B;**[!UICONTROL Dynamics CRM]**&#x200B;を選択する必要があります。

1. 次に、**[!UICONTROL user_impersonation]**&#x200B;のチェックボックスをオンにして、**[!UICONTROL Add permissions]** ボタンをクリックします。

権限の設定について詳しくは、[この節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}を参照してください。

### アプリユーザーの作成

この新規ユーザーは汎用ユーザーです。 APIを使用したMicrosoft Dynamics 365への変更は、このユーザーが行います。 作成するには、次の手順に従います。

1. Dynamics 365 インスタンスに移動し、管理者としてログインします。

1. 右上隅の歯車アイコンをクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。 上部バナーで、**[!UICONTROL Settings]**&#x200B;の横にあるドロップダウンをクリックし、**[!UICONTROL Security > Users]**&#x200B;をクリックします。

1. ドロップダウンメニューをクリックして、**[!UICONTROL Application Users]**&#x200B;に移動します。 「**[!UICONTROL New]**」をクリックします。

1. ユーザーアイコンの横にあるドロップダウンに「**[!UICONTROL USER:APPLICATIONUSER]**」と表示されていることを確認します。

   新しいユーザーの画面を入力します。  パラメーターの候補：

   * **[!UICONTROL User Name]** （メール）: adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; （例：adobe_api_stage@some-company.crm.dynamics.com）
   * **[!UICONTROL Application ID]**: Azure ADに登録したアプリケーションのID （必須）
   * 空白&#x200B;**[!UICONTROL Application ID URI]**&#x200B;と&#x200B;**[!UICONTROL Azure AD Object ID]**&#x200B;のままにできます
   * **[!UICONTROL Full Name]**: Adobe API `<stage or prod>`
   * **[!UICONTROL Email]**: **[!UICONTROL User Name]**&#x200B;と同じ（必要に応じて管理者の電子メール）

   アプリユーザーの作成について詳しくは、[この節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}を参照してください。

1. ユーザーアイコンをクリックし、Adobe Campaign アイコンをアップロードします。これは、新しいAdobe イベントがDynamics 365に表示されるときにタイムラインビューに表示されるアイコンです。

1. 上部のリボンの&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;をクリックして、ユーザーの役割リストを開きます。

1. 下にスクロールして、このユーザーの&#x200B;**[!UICONTROL System administrator]** アクセス権を選択します。

1. 「**[!UICONTROL OK]**」をクリックします。

### テナント IDを取得 {#get-the-tenant-id}

テナント IDを見つけるには、このページの[の手順](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)に従ってください。  統合ツールでの統合前のセットアップ時に、このIDが必要になります。

## Microsoft Dynamics 365用Campaign Standardのインストール {#install-appsource-app}

Dynamics 365 アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. [Microsoft Business Apps](https://appsource.microsoft.com/en-us/marketplace/apps)を参照し、検索バーで_Adobe Campaign Standard_を検索します。
または、この[&#x200B; リンク &#x200B;](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}に移動することもできます。
1. 手順に従って、Dynamics 365 インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365 インスタンスに移動し、管理者としてログインします。
1. 右上隅の歯車アイコンをクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。 上部バナーで、**[!UICONTROL Settings]**&#x200B;の横にあるドロップダウンをクリックし、**[!UICONTROL Process Center]**&#x200B;の下の&#x200B;**[!UICONTROL Processes]**&#x200B;をクリックします。
1. **[!UICONTROL Adobe Campaign Email Bounce]** タスクを検索してクリックします。
1. 「**[!UICONTROL Administration]**」タブで、上部のリボンから「**[!UICONTROL Actions]**」をクリックして以前に作成したAdobe API アプリケーションユーザーにオーナーを変更し、「**[!UICONTROL Assign to another User]**」オプションを選択し、ドロップダウンから「**[!UICONTROL Adobe API application user]**」を選択して割り当てます。
1. プロセスを再アクティブ化する：
1. **[!UICONTROL Adobe Campaign Email Click]** タスクに対して同じ操作を行います。

>[!NOTE]
>
>これらのプロセスを無効にする場合は、この&#x200B;**[!UICONTROL Processes]**&#x200B;画面でいつでも実行できます。

**関連トピック**

* [Microsoft Dynamics 365統合用Adobe Developerの設定](../../integrating/using/d365-acs-configure-adobe-io.md)は、統合を設定する次の手順です
* [&#x200B; セルフサービス統合アプリの基本を学ぶ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md)には、統合を開始するための手順の完全なリストが含まれています。
