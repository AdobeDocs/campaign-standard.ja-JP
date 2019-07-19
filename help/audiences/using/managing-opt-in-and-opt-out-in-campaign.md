---
title: キャンペーンでのオプトインおよびオプトアウトの管理
seo-title: キャンペーンでのオプトインおよびオプトアウトの管理
description: キャンペーンでのオプトインおよびオプトアウトの管理
seo-description: Adobe Campaignでオプトインおよびオプトアウトがどのように管理されるかを理解します。
page-status-flag: 常にアクティブ化されていない
uuid: aa1801ec-562b-420e-8d79- c07d066b7b1a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: understanding- opt- in- and- opt- out- processes
discoiquuid: 6b5680f2- bba9-453e- a0d5-8ca69dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Managing opt-in and opt-out in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Managing opt-in and opt-out from a profile {#managing-opt-in-and-opt-out-from-a-profile}

Users can be opted in or out by an operator directly from the profile **[!UICONTROL General]** tab.

**[!UICONTROL No longer contact (blacklist)]** セクションでは、選択したチェックボックスは、ユーザーがオプトアウトを選択したチャネルに対応しています。ユーザのニーズに応じてチャネルを選択します。

![](assets/optin_landingpage_3.png)

## Setting up opt-in and opt-out landing pages {#setting-up-opt-in-and-opt-out-landing-pages}

To give users the ability to opt in or opt out, you have to create and publish a **[!UICONTROL Profile acquisition]** landing page. その後、必要に応じてチャネルを選択できます。これを行うには、次の手順に従ってください。

**[!UICONTROL BlackList]** また、ユーザーがすべての配信からオプトアウトできるランディングページを設定することもできます。For more on this, refer to [Setting up a landing page to opt out from all deliveries](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>ランディングページは、サービスの購読を有効にするためにも使用できます。For more on this, refer to [this page](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service).

1. **[!UICONTROL Profile acquisition]** ランディングページを作成します（ [このセクション](../../channels/using/about-landing-pages.md)を参照）。
1. 各チャネルのランディングページのコンテンツにチェックボックスを追加し、キャンペーンデータベースから対応するフィールドにリンクします。

   ![](assets/optin_landingpage_1.png)

1. ランディングページを保存して公開します。
1. In the landing page, the checkboxes are already selected according to the profile **[!UICONTROL General]** tab. ユーザーは必要に応じてチャネルを選択または選択解除し、フォームを送信できます。

   ![](assets/optin_landingpage_2.png)

1. Once the form submitted, the profile **[!UICONTROL General]** tab is updated according to the user's selection.

   ![](assets/optin_landingpage_3.png)

### Setting up a landing page to opt out from all deliveries {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

To give users the ability to opt out from all deliveries, you have to create and publish a **[!UICONTROL BlackList]** landing page. For more on landing pages creation, refer to [this page](../../channels/using/about-landing-pages.md).

Once a user clicks on the landing page link, the **[!UICONTROL No longer contact (by any channel)]** option in the profile is automatically selected.

![](assets/blacklisting_allchannels.png)

