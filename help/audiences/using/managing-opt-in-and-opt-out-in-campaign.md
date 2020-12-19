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
source-wordcount: '0'
ht-degree: 0%

---


# Campaign のオプトインとオプトアウトの管理{#managing-opt-in-and-opt-out-in-campaign}

## プロファイルからのオプトインおよびオプトアウトの管理{#managing-opt-in-and-opt-out-from-a-profile}

プロファイル&#x200B;**[!UICONTROL General]**&#x200B;タブから、演算子を使用して直接ユーザーをオプトインまたはオプトアウトできます。

**[!UICONTROL No longer contact (on denylist)]**&#x200B;セクションでは、選択したチェックボックスは、ユーザーが選択したチャネルに対応しオプトアウトています。 ユーザーのニーズに応じてチャネルを選択します。

![](assets/optin_landingpage_3.png)

## オプトインおよびオプトアウトランディングページの設定{#setting-up-opt-in-and-opt-out-landing-pages}

ユーザーに対してオプトイン、または実行する権限を与えるには、**[!UICONTROL Profile acquisition]**&#x200B;ランディングページを作成して発行する必要があります。 その後、必要に応じてチャネルを選択できます。 それには、次の手順に従います。

また、すべての配信からのアクセスを可能にする&#x200B;**[!UICONTROL Denylist]**&#x200B;ランディングページを設定すオプトアウトることもできます。 詳しくは、[すべての配信の](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)に対するランディングページオプトアウトの設定を参照してください。

>[!NOTE]
>
>ランディングページは、サービスの購読を有効にするためにも使用できます。 詳しくは、[このページ](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)を参照してください。

1. **[!UICONTROL Profile acquisition]**&#x200B;ランディングページを作成します（[このセクション](../../channels/using/getting-started-with-landing-pages.md)を参照）。
1. 必要な各ランディングページのキャンペーンコンテンツ内のチェックボックス追加を選択し、チャネルデータベースの対応するフィールドにリンクします。

   ![](assets/optin_landingpage_1.png)

1. ランディングページを保存して公開します。
1. ランディングページでは、「プロファイル&#x200B;**[!UICONTROL General]**」タブに従って、チェックボックスが既に選択されています。 ユーザーは、必要に応じてチャネルを選択または選択解除し、フォームを送信できます。

   ![](assets/optin_landingpage_2.png)

1. フォームが送信されると、プロファイル&#x200B;**[!UICONTROL General]**&#x200B;タブはユーザーの選択に従って更新されます。

   ![](assets/optin_landingpage_3.png)

### すべての配信オプトアウトから{#setting-up-a-landing-page-to-opt-out-from-all-deliveries}へのランディングページの設定

すべての配信からユーザーに対してオプトアウト機能を提供するには、**[!UICONTROL Denylist]**&#x200B;ランディングページを作成して発行する必要があります。 ランディングページの作成について詳しくは、[このページ](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

ユーザーがランディングページリンクをクリックすると、プロファイルの&#x200B;**[!UICONTROL No longer contact (by any channel)]**&#x200B;オプションが自動的に選択されます。

![](assets/blocklisting_allchannels.png)

