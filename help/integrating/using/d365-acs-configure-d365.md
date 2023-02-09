---
title: Campaign 統合用の Microsoft Dynamics 365 の設定
description: Campaign 統合用のMicrosoft Dynamics 365 の設定方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 2%

---

# Adobe Campaign Standardとの統合のためのMicrosoft Dynamics 365 の設定

Adobe Campaign Standardとのクロスチャネル通信で、Microsoft Dynamics 365 統合を設定し、CRM データをアクティブ化する方法について説明します。

## 概要

Microsoft Dynamics 365 とのAdobe Campaign Standard統合の一般的な説明については、 [このページ](../../integrating/using/d365-acs-get-started.md).

統合を有効にするには複数のアプリケーションを設定する必要がありますが、この記事では、Dynamics 365 内で必要な手順について説明します。

## 前提条件

このドキュメントで事前統合の設定を実行する前に、既にプロビジョニング済みで、組織のMicrosoft Dynamics 365 インスタンスへの管理者アクセス権を持っていることを前提としています。  この問題が発生していない場合は、Microsoftカスタマーサポートに連絡して、Dynamics 365 プロビジョニングを完了する必要があります。

ステージング環境と実稼動環境の両方に統合を設定する場合は、ステージング環境と実稼動環境の両方に対して、以下の手順を実行する必要があります。 以下の手順は、ステージまたは実稼働の Dynamics 365 インスタンスを設定する場合 ( 例えば、実稼働インスタンスの場合は、「prod」を選択して `<stage or prod>`)

## アプリケーションと権限の設定

OAuth アクセストークンを使用すると、統合ツールで Web API を介してMicrosoft Dynamics 365 インスタンスを認証し、Campaign StandardエクスペリエンスイベントをMicrosoft Dynamics 365 インターフェイスのタイムラインビューに投稿できます。

主な手順の概要を次のビデオで説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuth アクセストークンを生成するには、次の手順に従います。

### 新しいアプリケーションを登録 {#register-a-new-app}

1. 管理者ログインで、にログインします。 [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. クリック **[!UICONTROL Azure Active Directory]** 左側のメニューに次に、 **[!UICONTROL App registrations]** をクリックします。

1. クリック **[!UICONTROL New registration]** をクリックします。

1. アプリの登録画面に入力します。

   * 名前：adobe campaign `<stage or prod>`
   * サポートされるアカウントのタイプ： **[!UICONTROL Accounts in this organizational directory only]** （デフォルト値）

新しいアプリケーションの作成について詳しくは、 [この節](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory は、アプリに一意のアプリケーション（クライアント） ID を割り当てます。 この ID は、後で Dynamics 365 の設定で必要になります。また、統合ツールの設定を実行する際にも必要になります。

### クライアント秘密鍵を生成 {#generate-a-client-secret}

1. アプリの概要画面で、左側のサブメニューの「 」をクリックします。 **[!UICONTROL Certificates and Secrets > New client secret]**

1. 説明を入力し、期間を設定して、 **[!UICONTROL OK]**.

これで、クライアント秘密鍵が作成されました。 統合ツールの統合前の設定が完了するまで、値を一時的に保持します。

>[!CAUTION]
>
>この値は、統合ツールの事前統合設定を完了するために必要になるため、そのままにします。 後で取得することはできません。


### 権限の設定

1. この画面またはアプリの概要画面で、 **[!UICONTROL API permissions]** を選択します。  クリック後 **[!UICONTROL Add a permission]**&#x200B;を選択する場合は、 **[!UICONTROL Dynamics CRM]** 」と入力します。

1. 次に、 **[!UICONTROL user_impersonation]**&#x200B;をクリックし、 **[!UICONTROL Add permissions]** 」ボタンをクリックします。

権限の設定について詳しくは、 [この節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### アプリユーザーの作成

この新しいユーザーは汎用のユーザーです。 アプリケーションで使用されます。API を使用したMicrosoft Dynamics 365 の変更は、このユーザーがおこないます。 作成するには、次の手順に従います。

1. Dynamics 365 インスタンスに移動し、管理者としてログインします。

1. 右上隅の歯車アイコンをクリックし、 **[!UICONTROL Advanced Settings]**. 上部のバナーで、の横にあるドロップダウンをクリックします。 **[!UICONTROL Settings]**&#x200B;をクリックし、 **[!UICONTROL Security > Users]**.

1. ドロップダウンメニューをクリックして、次に移動します。 **[!UICONTROL Application Users]**. 「**[!UICONTROL New]**」をクリックします。

1. ユーザーアイコンの横にあるドロップダウンが、次のように表示されていることを確認します。 **[!UICONTROL USER:APPLICATION USER]**.

   新しいユーザーの画面に入力します。  パラメーターの候補：

   * **[!UICONTROL User Name]** （電子メール）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; ( 例： adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:Azure AD に登録したアプリケーションの ID （必須）
   * 空白のままにしておけます **[!UICONTROL Application ID URI]** および **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**:同じ **[!UICONTROL User Name]** （必要に応じて管理者の電子メールを送信）

   アプリのユーザー作成について詳しくは、 [この節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. ユーザーアイコンをクリックし、 Adobe Campaignアイコンをアップロードします。これは、Dynamics 365 で新しいイベントが表示されたときに、Adobeビューに表示されるアイコンです。

1. 「 **[!UICONTROL MANAGE ROLES]** をクリックします。

1. 下にスクロールして、「 」を選択します。 **[!UICONTROL System administrator]** このユーザーのへのアクセス権。

1. 「**[!UICONTROL OK]**」をクリックします。

### テナント ID を取得する {#get-the-tenant-id}

手順に従います。 [このページ](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) テナント ID を見つけるために使用します。  統合ツールでの統合前の設定時に、この ID が必要になります。

## Microsoft Dynamics 365 のインストールCampaign Standard {#install-appsource-app}

Dynamics 365 アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. 次のリンクに移動します。 [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) およびを検索します。 _Adobe Campaign for Dynamics 365_ をクリックします。
または、次の場所に移動することもできます： [リンク](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}.
1. 指示に従って、Dynamics 365 インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365 インスタンスに移動し、管理者としてサインインします。
1. 右上隅の歯車アイコンをクリックし、 **[!UICONTROL Advanced Settings]**. 上部のバナーで、の横にあるドロップダウンをクリックします。 **[!UICONTROL Settings]**&#x200B;をクリックし、 **[!UICONTROL Processes]** under **[!UICONTROL Process Center]**.
1. を検索 **[!UICONTROL Adobe Campaign Email Bounce]** タスクをクリックしてクリックします。
1. の **[!UICONTROL Administration]** 」タブで、「 **[!UICONTROL Actions]** 上部のリボンから、「 」を選択します。 **[!UICONTROL Assign to another User]** オプション、選択 **[!UICONTROL Adobe API application user]** 割り当てるドロップダウンから。
1. プロセスを再アクティブ化します。
1. 同様に、 **[!UICONTROL Adobe Campaign Email Click]** タスク。

>[!NOTE]
>
>これらのプロセスをいつでも非アクティブにしたい場合は、 **[!UICONTROL Processes]** 画面

**関連トピック**

* [Microsoft Dynamics 365 統合用のAdobe Developerの設定](../../integrating/using/d365-acs-configure-adobe-io.md) は、統合を設定する次の手順です。
* [セルフサービス統合アプリの概要](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) には、統合を導入および実行する手順の完全なリストが含まれています。
