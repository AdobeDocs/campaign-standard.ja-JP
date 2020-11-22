---
solution: Campaign Standard
product: campaign
title: Campaign 統合用の Microsoft Dynamics 365 の設定
description: Microsoft Dynamics 365 forキャンペーン統合を構成する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 2%

---


# Campaign 統合用の Microsoft Dynamics 365 の設定

Microsoft Dynamics 365統合を構成し、Adobe Campaign Standardとのチャネル間通信でCRMデータをアクティブにする方法を説明します。

## 概要

Adobe Campaign Standard- Microsoft Dynamics 365の統合については、 [このページで説明します](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

この統合用にプロビジョニングする必要がある3つのシステム：

1. Adobe Campaign Standard- [詳細情報](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales — 以下の説明
1. 統合ツール —Adobeコンサルティングチームが所有

プロビジョニングが完了したら、管理者がこれらのシステムを設定する必要があります。

この記事では、統合前のセットアップ中に、お客様がAdobe Campaign Standard- Microsoft Dynamics 365統合を使用できるようにするために必要なMicrosoft Dynamics 365側の手順について説明します。

>[!NOTE]
>
>セルフサービスツールのUIが今年中に入手できるまで、オンボーディングチームが統合の設定を支援します。

## 前提条件

このドキュメントで統合前のセットアップを実行する前に、既にプロビジョニングが完了しており、組織のMicrosoft Dynamics 365インスタンスに対する管理者アクセス権があることを前提としています。  この問題が発生しない場合は、Dynamics 365のプロビジョニングを完了するには、Microsoftカスタマーサポートに連絡する必要があります。

ステージングと実稼働の両方の環境に対して統合を設定する場合は、ステージングと実稼働の両方のDynamics 365インスタンスに対して、次の手順を実行する必要があります。 以下の手順は、ステージまたは実稼働のDynamics 365インスタンスを設定する場合に少し異なります(例：実稼働インスタンスの場合は、「prod」を選択してください `<stage or prod>`)

## アプリケーションと権限の設定

OAuthアクセストークンを使用すると、Campaign StandardエクスペリエンスのイベントをMicrosoft Dynamics 365インターフェイスのタイムライン表示にポストするために、統合ツールがWeb APIを介してMicrosoft Dynamics 365インスタンスを認証できます。

主な手順を次のビデオで説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27637)

OAuthアクセストークンを生成するには、次の手順に従います。

### 新しいアプリケーションの登録

1. 管理者ログインで、portal.azure.comにログインします。

1. 左側のメニュー **[!UICONTROL Azure Active Directory]** のをクリックします。次に、表示さ **[!UICONTROL App registrations]** れるサブメニューをクリックします。

1. 画面 **[!UICONTROL New registration]** の上部にあるをクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. アプリの登録画面に次の情報を入力します。

   * 名前：adobeキャンペーン `<stage or prod>`
   * サポートされるアカウントの種類： **[!UICONTROL Accounts in this organizational directory only]** （デフォルト値）

新しいアプリケーションの作成の詳細については、 [この節を参照してください](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。

>[!NOTE]
>
>Azure ADは、一意のアプリケーション&#39; （クライアント） IDをアプリに割り当てます。 このIDは、後でDynamics 365の設定で必要になります。また、統合ツールの統合前の設定を実行する場合にも必要になります。

### クライアントシークレットの生成

1. アプリの概要画面の左側のサブメニューで、「 **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 説明を入力し、期間を設定して、をクリックし **[!UICONTROL OK]**&#x200B;ます。

これで、クライアントシークレットが作成されます。 統合ツールの統合前の設定を完了するために、値を一時的に保持します。

>[!CAUTION]
>
>統合ツールの統合前の設定を完了するために必要な場合は、この値をそのままにしてください。 後で取得することはできません。


### 権限の設定

1. この画面またはアプリの概要画面で、左側のサブメニュー **[!UICONTROL API permissions]** の「on」をクリックします。  クリック後 **[!UICONTROL Add a permission]**、メニューからを選択す **[!UICONTROL Dynamics CRM]** る必要があります。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 次に、のチェックボックスをオン **[!UICONTROL user_impersonation]**&#x200B;にして、 **[!UICONTROL Add permissions]** ボタンをクリックします。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

権限の設定の詳細については、 [この節を参照してください](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)。

### アプリユーザーの作成

この新しいユーザーは汎用ユーザーです。 これは、次のアプリケーションで使用されます。APIを使用してMicrosoft Dynamics 365に変更を加えると、このユーザーが行います。 作成するには、次の手順に従います。

1. Dynamics 365インスタンスに移動し、管理者としてログインします。

1. 右上隅の歯車アイコンをクリックし、「オン」をクリックし **[!UICONTROL Advanced Settings]**&#x200B;ます。 上部のバナーで、の横のドロップダウンをクリックし、「オン」 **[!UICONTROL Settings]**&#x200B;をクリックし **[!UICONTROL Security > Users]**&#x200B;ます。

1. ドロップダウンメニューをクリックして、に移動し **[!UICONTROL Application Users]**&#x200B;ます。 「**[!UICONTROL New]**」をクリックします。

1. 「ユーザーアイコン」の横のドロップダウンを確認し **[!UICONTROL USER:APPLICATION USER]**&#x200B;ます。

   新しいユーザーの画面に入力します。  パラメーターの提案：

   * **[!UICONTROL User Name]** （電子メール）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例：adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:Azure ADに登録したアプリケーションのID （必須）
   * 空白のままにしてお **[!UICONTROL Application ID URI]** き、 **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**:と同じ **[!UICONTROL User Name]** （必要に応じて管理者の電子メール）

   アプリのユーザー作成について詳しくは、 [この節を参照してください](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

1. ユーザーアイコンをクリックし、Adobe Campaignアイコンをアップロードします。これは、Dynamics 365で新しいAdobeイベントが表示された場合に、タイムライン表示に表示されるアイコンです。

<!-- ***getfile*** adobe campaign logo-->

1. 上部のリボンのをクリックして、ユーザの役割リスト **[!UICONTROL MANAGE ROLES]** を開きます。

1. 下にスクロールし、このユーザーの **[!UICONTROL System administrator]** アクセス権を選択します。

1. 「**[!UICONTROL OK]**」をクリックします。

### テナントIDの取得

このページ [の手順に従って、テナントIDを検索します](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) 。  統合ツールの統合前の設定時に、このIDが必要になります。

## Microsoft Dynamics 365用Campaign Standardのインストール

Dynamics 365アプリをCampaign Standard環境に統合するには、次の手順に従います。

1. 次のリンクに移動します。 [検索バーで、https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) and search for _Dynamics 365_ .
または、この [リンクに移動できます](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)。
1. 手順に従って、Dynamics 365インスタンス用のアプリをインストールします。
1. インストールが完了したら、Dynamics 365インスタンスに移動し、管理者としてサインインします。
1. 右上隅の歯車アイコンをクリックし、「オン」をクリックし **[!UICONTROL Advanced Settings]**&#x200B;ます。 上部のバナーで、の横のドロップダウンをクリックし、 **[!UICONTROL Settings]**&#x200B;の下のをクリックし **[!UICONTROL Processes]** ま **[!UICONTROL Process Center]**&#x200B;す。
1. 「 **[!UICONTROL Adobe Campaign Email Bounce]** タスク」を検索し、クリックします。
1. タブで、所有者を、上部のリボンからをクリックして前に作成したAdobeAPIアプリケーションユーザーに変更 **[!UICONTROL Administration]** し、 **[!UICONTROL Actions]** オプションを選択して、ドロップダウン **[!UICONTROL Assign to another User]****[!UICONTROL Adobe API application user]** から割り当てるオプションを選択します。
1. プロセスを再アクティブ化します。
1. タスクに対しても同じことを行い **[!UICONTROL Adobe Campaign Email Click]** ます。

>[!NOTE]
>
>これらのプロセスを非アクティブ化する場合は、この **[!UICONTROL Processes]** 画面で行うことができます。

**関連トピック**

* [Campaign Standard- Microsoft Dynamics 365統合](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Microsoft Dynamics 365 統合用の Adobe IO の設定](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
