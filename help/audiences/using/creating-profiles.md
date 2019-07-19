---
title: プロファイルの作成
seo-title: プロファイルの作成
description: プロファイルの作成
seo-description: API、インポート機能、オンライン獲得、自動または手動の更新を使用して、プロファイルを作成し、連絡先にデータを収集する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: a5f5a58a- e798-400f-8648-05dc843d5557
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: 管理プロファイル
discoiquuid: 4ab8a984- f898-4fff- ad8c- ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f883986392f6b739832093e0473591aa39dfcbfe

---


# Creating profiles{#creating-profiles}

Adobe Campaignでは、デフォルトでプロファイルが使用され、メッセージのメインターゲットを定義します。

キャンペーンでプロファイルを作成または更新するには、次のことができます。

* [ワークフローを介したファイルからのプロファイルリストの読み込み](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Collect data online, via [landing pages](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html)
* Create bulk via [REST API](http://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)
* Synchronize profiles from [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* 以下の説明に従って、グラフィカルインターフェイス画面を使用してデータを入力します

例えば、ユーザーインターフェイスに新しいプロファイルを直接作成するには、次の手順に従います。

1. From the Adobe Campaign home page, click the **Customer Profiles** card or the **Profiles** tab to access the list of profiles.

   ![](assets/profile_creation_1.png)

1. Then click **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. プロファイルデータを入力します。

   ![](assets/profile_creation1.png)

   * The contact information, such as first name, last name, gender, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)) helps better personalize deliveries.
   * The profile's **[!UICONTROL Time zone]** is used to send deliveries at the profile's time zone. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * **[!UICONTROL Channels]** このカテゴリには、電子メールアドレス、携帯電話番号、オプトアウト情報が含まれており、プロファイルに到達可能なチャネルを把握できます。
   * **[!UICONTROL No longer contact]** カテゴリがチャネルのサブスクライブ解除となると、カテゴリはすぐに更新されます。
   * **[!UICONTROL Address]** カテゴリには、このプロファイルにダイレクトメールを送信する **[!UICONTROL Address specified]** オプションと共に入力する必要 [がある住所が](../../channels/using/about-direct-mail.md) 含まれています。**[!UICONTROL Address specified]** このオプションを選択しない場合、このプロファイルはすべてのダイレクトメール配信から除外されます。
   * **[!UICONTROL Access authorization]** カテゴリは、プロファイルの組織単位（権限 [](../../administration/using/about-access-management.md)を管理するため）を示します。[「分割プロファイル](../../administration/using/organizational-units.md#partitioning-profiles)」も参照してください。
   * **[!UICONTROL Traceability]** カテゴリは、プロファイルを作成または変更したユーザーに関する情報で自動的に更新されます。

1. Click **[!UICONTROL Create]** to save the profile.

これで、プロファイルがリストに表示されます。

>[!NOTE]
>
>Adobe Campaign Standard APIを使用してプロファイルの作成も可能です。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#creating-profiles) .

プロファイルは、組織単位によっても分割できます。To add the organizational fields to your profiles, refer to the [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles) section.

>[!NOTE]
>
>多言語メッセージ送信時に言語を選択するには、優先言語フィールドを使用します。For more information about the multilingual messages [refer to this page](../../channels/using/creating-a-multilingual-email.md).

**関連トピック:**

* [ランディングページ](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html) ステップバイステップガイドの作成
* [プロファイルの読み込み](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

