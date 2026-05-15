---
title: Campaign のオプトインとオプトアウトの管理
description: Adobe Campaignでオプトインとオプトアウトを管理する方法について説明します。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
TQID: https://experienceleague.adobe.com/RLzfw7dzg3MhpYR7scuOTBdmsIHr5aKHllFjb-RkM-I
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 9%

---

# Campaign のオプトインとオプトアウトの管理{#managing-opt-in-and-opt-out-in-campaign}

## プロファイルからのオプトインとオプトアウトの管理 {#managing-opt-in-and-opt-out-from-a-profile}

ユーザーは、プロファイル **[!UICONTROL General]** タブから直接、オペレーターによってオプトインまたはオプトアウトできます。

**[!UICONTROL No longer contact (on denylist)]** セクションでは、選択したチェックボックスは、ユーザーがオプトアウトを選択したチャネルに対応します。 ユーザーのニーズに応じてチャネルを選択します。

![](assets/optin_landingpage_3.png)

## オプトインおよびオプトアウトのランディングページを設定する {#setting-up-opt-in-and-opt-out-landing-pages}

ユーザーがオプトインまたはオプトアウトできるようにするには、**[!UICONTROL Profile acquisition]** ランディングページを作成して公開する必要があります。 その後、ニーズに応じてチャネルを選択することができます。 それには、次の手順に従います。

また、ユーザーがすべての配信からオプトアウトできるようにする&#x200B;**[!UICONTROL Denylist]** ランディングページを設定することもできます。 詳しくは、[すべての配信からオプトアウトするためのランディングページの設定](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)を参照してください。

>[!NOTE]
>
>ランディングページは、サービスのサブスクリプションを有効にするためにも使用できます。 詳しくは、[このページ](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)を参照してください。

1. **[!UICONTROL Profile acquisition]** ランディングページを作成します（[このセクション ](../../channels/using/getting-started-with-landing-pages.md)を参照）。
1. 目的の各チャネルのランディングページコンテンツにチェックボックスを追加し、Campaign データベースの対応するフィールドにリンクします。

   ![](assets/optin_landingpage_1.png)

1. ランディングページを保存して公開します。
1. ランディングページでは、プロファイル **[!UICONTROL General]** タブに従ってチェックボックスが既に選択されています。 利用者は、ニーズに応じてチャネルを選択または選択解除し、フォームを送信できます。

   ![](assets/optin_landingpage_2.png)

1. フォームが送信されると、ユーザーの選択に従ってプロファイル **[!UICONTROL General]** タブが更新されます。

   ![](assets/optin_landingpage_3.png)

### すべての配信からオプトアウトするためのランディングページの設定 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

ユーザーがすべての配信からオプトアウトできるようにするには、**[!UICONTROL Denylist]** ランディングページを作成して公開する必要があります。 ランディングページの作成について詳しくは、[このページ ](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

ユーザーがランディングページのリンクをクリックすると、プロファイルの&#x200B;**[!UICONTROL No longer contact (by any channel)]** オプションが自動的に選択されます。

![](assets/blocklisting_allchannels.png)
