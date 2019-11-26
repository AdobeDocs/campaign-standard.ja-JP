---
title: キャンペーンのオプトインとオプトアウトの管理
description: Adobe Campaignでのオプトインおよびオプトアウトの管理方法を説明します。
page-status-flag: never-activated
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# キャンペーンのオプトインとオプトアウトの管理{#managing-opt-in-and-opt-out-in-campaign}

## プロファイルのオプトインとオプトアウトの管理 {#managing-opt-in-and-opt-out-from-a-profile}

ユーザーは、プロファイルタブから直接、オペレーターによってオプトインまたはオプトアウトで **[!UICONTROL General]** きます。

このセクション **[!UICONTROL No longer contact (blacklist)]** では、選択したチェックボックスは、ユーザがオプトアウトを選択したチャネルに対応しています。 ユーザーのニーズに応じてチャネルを選択します。

![](assets/optin_landingpage_3.png)

## オプトインおよびオプトアウトランディングページの設定 {#setting-up-opt-in-and-opt-out-landing-pages}

ユーザーがオプトインまたはオプトアウトできるようにするには、ランディングページを作成して公開する必要 **[!UICONTROL Profile acquisition]** があります。 その後、必要に応じてチャネルを選択できます。 これを行うには、次の手順に従います。

また、ランディングページを設定して、ユ **[!UICONTROL BlackList]** ーザーがすべての配信をオプトアウトできるようにすることもできます。 詳しくは、「すべての配信をオプトア [ウトするためのランディングページの設定」を参照してください](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>ランディングページは、サービスの購読を有効にするためにも使用できます。 詳しくは、[このページ](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)を参照してください。

1. ランディング **[!UICONTROL Profile acquisition]** ページを作成します( [この節を参照](../../channels/using/getting-started-with-landing-pages.md))。
1. 目的の各チャネルのランディングページのコンテンツにチェックボックスを追加し、Campaignデータベースから対応するフィールドにリンクします。

   ![](assets/optin_landingpage_1.png)

1. ランディングページを保存して発行します。
1. ランディングページでは、プロファイルタブに従ってチェックボックスが既に選択され **[!UICONTROL General]** ています。 ユーザーは、必要に応じてチャネルを選択または選択解除し、フォームを送信できます。

   ![](assets/optin_landingpage_2.png)

1. フォームが送信されると、ユーザーの選 **[!UICONTROL General]** 択に従って「プロファイル」タブが更新されます。

   ![](assets/optin_landingpage_3.png)

### すべての配信からオプトアウトするためのランディングページの設定 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

すべての配信からオプトアウトする機能をユーザーに提供するには、ランディングページを作成して公開する必要 **[!UICONTROL BlackList]** があります。 For more on landing pages creation, refer to [this page](../../channels/using/getting-started-with-landing-pages.md).

ユーザーがランディングページのリンクをクリックすると、プロフ **[!UICONTROL No longer contact (by any channel)]** ァイルのオプションが自動的に選択されます。

![](assets/blacklisting_allchannels.png)

