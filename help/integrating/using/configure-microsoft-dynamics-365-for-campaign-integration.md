---
title: Campaign 統合用の Microsoft Dynamics 365 の設定
description: Microsoft Dynamics 365を統合用に構成する方法についてキャンペーンします。
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


# Campaign 統合用の Microsoft Dynamics 365 の設定

Microsoft Dynamics 365統合を構成し、Microsoft Standardとのクロスチャネル通信でCRMデータをアクティブにする方法を説明します。

## 概要

Adobe Campaign標準 — Microsoft Dynamics 365の統合については、このページで説 [明します](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

この統合用にプロビジョニングする必要がある3つのシステム：

1. Adobe Campaign標準 — [詳細](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales — 以下の説明
1. Unifi — 詳細 [情報](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

プロビジョニングが完了したら、管理者がこれらのシステムを設定する必要があります。

この記事では、ユーザーがAdobe Campaign標準 — Microsoft Dynamics 365統合を使用できるように、プロビジョニング後に必要なMicrosoft Dynamics 365側の手順について説明します。

## 前提条件

このドキュメントのプロビジョニング後の手順を実行する前に、既にプロビジョニングが完了しており、組織のMicrosoft Dynamics 365インスタンスに対する管理者アクセス権を持っていることを前提としています。  この問題が発生しない場合は、Dynamics 365のプロビジョニングを完了するために、Microsoftカスタマーサポートに連絡する必要があります。

## アプリケーションと権限の設定

OAuthアクセストークンを使用すると、Microsoft Dynamics 365インターフェイスのタイムライン表示にCampaign Standardエクスペリエンスイベントをポストするために、Web APIを介してMicrosoft Dynamics 365インスタンスの認証をUnifiで行うことができます。

主な手順を以下のビデオで説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuthアクセストークンを生成するには、次の手順に従います。

### 新しいアプリの登録

1. 管理者ログインで、portal.azure.comにログインします。

1. 左側のメニ **[!UICONTROL Azure Active Directory]** ューのをクリックします。次に、表示さ **[!UICONTROL App registrations]** れるサブメニューをクリックします。

1. 画面の **[!UICONTROL New registration]** 上部にあるをクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. アプリの登録画面に入力します。

   * 名前：アドビキャンペーン
   * サポートされるアカウントの種類： **[!UICONTROL Accounts in this organizational directory only]** （デフォルト値）

For more information about creating a new application, refer to [this section](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure ADは、一意のアプリケーション（クライアント）IDをアプリに割り当てます。 このIDは、後でDynamics 365の設定と、Unifi投稿のプロビジョニング手順を実行する際に必要になります。

### クライアントシークレットの生成

1. アプリの概要画面の左側のサブメニューで、 **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 説明を入力し、期間を設定して、をクリックしま **[!UICONTROL OK]**&#x200B;す。

これで、クライアントシークレットが作成されました。  Unifiプロビジョニング後の手順を完了するための値を保持します。

>[!CAUTION]
>
>この値は、Unifiプロビジョニング後の手順を完了するために必要な値のままにします。 後で取得することはできません。

クライアントシークレットの生成の詳細については、この節を参照してください。

### 権限の設定

1. この画面またはアプリの概要画面で、左側のサ **[!UICONTROL API permissions]** ブメニューのをクリックします。  をクリック **[!UICONTROL Add a permission]**&#x200B;した後、メニュー内でを選択 **[!UICONTROL Dynamics CRM]** する必要があります。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 次に、のチェックボックスをオ **[!UICONTROL user_impersonation]**&#x200B;ンにして、ボタンをクリッ **[!UICONTROL Add permissions]** クします。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

権限の設定の詳細については、この節を参照し [てください](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)。

### アプリユーザーの作成

この新しいユーザーは汎用ユーザーです。 アプリケーションで使用されます。このAPIを使用してMicrosoft Dynamics 365に変更を加えると、このユーザーが行います。 作成するには、次の手順に従います。

1. Dynamics 365インスタンスに移動し、管理者としてログインします。

1. 右上隅の歯車アイコンをクリックし、をクリックします **[!UICONTROL Advanced Settings]**。 上部のバナーで、の横のドロップダウンをクリックし、「 **[!UICONTROL Settings]**&#x200B;オン」をクリックしま **[!UICONTROL Security > Users]**&#x200B;す。

1. ドロップダウンメニューをクリックして、に移動しま **[!UICONTROL Application Users]**&#x200B;す。 クリック **[!UICONTROL New]** .

1. ユーザーアイコンの横にあるドロップダウンを確認しま **[!UICONTROL USER:APPLICATION USER]**&#x200B;す。

   新しいユーザーの画面に入力します。  パラメーターの提案：

   * **[!UICONTROL User Name]** （電子メール）:adobeapi@`<hostname>`。は、 `<hostname>` Dynamics 365インスタンスのホスト名です。
   * **[!UICONTROL Application ID]**:Azure ADに登録したアプリケーションのID（必須）
   * 空白のままにして、 **[!UICONTROL Application ID URI]** および **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:Adobe API
   * **[!UICONTROL Email]**:と同じ **[!UICONTROL User Name]** （必要に応じて管理者の電子メール）
   アプリのユーザー作成について詳しくは、この節を参照 [してください](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

1. ユーザーアイコンをクリックし、ユーザーアイコンをAdobe Campaignします。これは、Dynamics 365で新しいAdobeイベントが表示されたときに、タイムライン表示に表示されるアイコンです。

<!-- ***getfile*** adobe campaign logo-->

1. 上部のリボンのをクリックして、リスト **[!UICONTROL MANAGE ROLES]** の役割のユーザを開きます。

1. 下にスクロールして、このユー **[!UICONTROL System administrator]** ザーのアクセス権を選択します。

1. クリック **[!UICONTROL OK]** .

### テナントIDの取得

次のリンクの手順に従って、テナントIDを探します。  Unifiでのプロビジョニング後に、次のIDが必要になります。 [https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)。

## Microsoft Dynamics 365のCampaign Standardのインストール

Dynamics 365アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. 次のリンクに移動します。検索バ [ーで](https://appsource.microsoft.com/en-us/marketplace/apps) 、https://appsource.microsoft.com/en-us/marketplace/apps _365の_ Adobe Campaignを検索します。
または、このリンクに移動で [きます](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)。
1. 手順に従って、Dynamics 365インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365インスタンスに移動し、管理者としてログインします。
1. 右上隅の歯車アイコンをクリックし、をクリックします **[!UICONTROL Advanced Settings]**。 上部のバナーで、の横のドロップダウンをクリックし、 **[!UICONTROL Settings]**&#x200B;の下のをクリッ **[!UICONTROL Processes]** クしま **[!UICONTROL Process Center]**&#x200B;す。
1. 「 **[!UICONTROL Adobe Campaign Email Bounce]** タスク」を検索し、クリックします。
1. タブで、 **[!UICONTROL Administration]** 所有者を上部のリボンからをクリックして先に作成したAdobe APIアプリケーションユーザーに変更し、オプションを選択し、ドロッ **[!UICONTROL Actions]** プダウン **[!UICONTROL Assign to another User]** から割り当てる **[!UICONTROL Adobe API application user]** オプションを選択します。
1. プロセスを再アクティブ化します。
1. 同じ操作を、 **[!UICONTROL Adobe Campaign Email Click]** タスクにも

>[!NOTE]
>
>これらのプロセスをいつでも非アクティブ化したい場合は、この画面で行うことがで **[!UICONTROL Processes]** きます。

この設定が完了したら、Unifi設定を設定できます。 詳しくは、この[ページ](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)を参照してください。

**関連トピック**

* [Campaign Standard- Microsoft Dynamics 365の統合](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Microsoft Dynamics 365 統合用の Adobe IO の設定](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [キャンペーン用のUnifiの構成 — Microsoft Dynamics 365統合](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)
