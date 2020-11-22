---
solution: Campaign Standard
product: campaign
title: Campaign のオプトインとオプトアウトの管理
description: オプトインおよびオプトアウトのAdobe Campaign管理方法を理解します。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# Campaign のオプトインとオプトアウトの管理{#managing-opt-in-and-opt-out-in-campaign}

## プロファイルからのオプトインおよびオプトアウトの管理 {#managing-opt-in-and-opt-out-from-a-profile}

プロファイルは、「ユーザー」 **[!UICONTROL General]** タブから演算子で直接オプトインまたはオプトアウトできます。

このセクションでは、選択したチェックボックスは、ユーザが選択したチャネルに対応しオプトアウトています。 **[!UICONTROL No longer contact (on denylist)]** ユーザーのニーズに応じてチャネルを選択します。

![](assets/optin_landingpage_3.png)

## オプトインおよびオプトアウトランディングページの設定 {#setting-up-opt-in-and-opt-out-landing-pages}

ユーザーに対してオプトイン、または権限を与えるには、 **[!UICONTROL Profile acquisition]** ランディングページを作成して公開する必要があります。 その後、必要に応じてチャネルを選択できます。 それには、次の手順に従います。

また、すべての配信からのアクセスを許可する **[!UICONTROL Denylist]** ランディングページを設定すオプトアウトることもできます。 詳しくは、「すべての配信からのランディングページの [設定」を参照してくだオプトアウトさい](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>ランディングページは、サービスの購読を有効にするためにも使用できます。 詳しくは、[このページ](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)を参照してください。

1. **[!UICONTROL Profile acquisition]** ランディングページを作成します( [この節を参照](../../channels/using/getting-started-with-landing-pages.md))。
1. 必要な各ランディングページのキャンペーンコンテンツ内のチェックボックス追加を選択し、チャネルデータベースの対応するフィールドにリンクします。

   ![](assets/optin_landingpage_1.png)

1. ランディングページを保存して公開します。
1. ランディングページでは、[プロファイル] **[!UICONTROL General]** タブに従ってチェックボックスが既に選択されています。 ユーザーは、必要に応じてチャネルを選択または選択解除し、フォームを送信できます。

   ![](assets/optin_landingpage_2.png)

1. フォームが送信されると、ユーザーの選択に従って「プロファイル」 **[!UICONTROL General]** タブが更新されます。

   ![](assets/optin_landingpage_3.png)

### すべての配信からにオプトアウトランディングページを設定する {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

すべての配信からアクセスできオプトアウトるようにするには、 **[!UICONTROL Denylist]** ランディングページを作成して公開する必要があります。 For more on landing pages creation, refer to [this page](../../channels/using/getting-started-with-landing-pages.md).

ランディングページのリンクをクリックすると、プロファイルの **[!UICONTROL No longer contact (by any channel)]** オプションが自動的に選択されます。

![](assets/blocklisting_allchannels.png)

