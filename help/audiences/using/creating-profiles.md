---
title: プロファイルの作成
description: API、インポート機能、オンライン獲得、自動更新、または手動更新を使用して、プロファイルを作成し、連絡先のデータを収集する方法について説明します。
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# プロファイルの作成{#creating-profiles}

Adobe Campaignでは、プロファイルはデフォルトでメッセージのメインターゲットを定義するために使用されます。

Campaignでプロファイルを作成または更新するには、次の操作を行います。

* ワークフローを使用したファイルからのプロファイルリストの読み [込み](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* ランディングページを使用してオンラインで [データを収集](../../channels/using/getting-started-with-landing-pages.md)
* [REST APIを使用した一括作成](../../api/using/about-campaign-standard-apis.md)
* [Microsoft Dynamicsからのプロファイルの同期](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* 以下に説明するように、グラフィカルインターフェイス画面を使用してデータを入力します

例えば、ユーザーインターフェイスに直接新しいプロファイルを作成するには、次の手順に従います。

1. Adobe Campaignのホームページで、「 **Customer Profiles** 」カードまたは「 **Profiles** 」タブをクリックして、プロファイルのリストにアクセスします。

   ![](assets/profile_creation_1.png)

1. 次に、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/profile_creation.png)

1. プロファイルデータを入力します。

   ![](assets/profile_creation1.png)

   * 連絡先情報(名、姓、性別、生年月日、写真、好みの言語(多言語電子メール用 [](../../channels/using/creating-a-multilingual-email.md))など)は、配信をよりパーソナライズするのに役立ちます。
   * プロファイルのタイム **[!UICONTROL Time zone]** ゾーンで配信を送信する際に使用されます。 詳しくは、[この節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。
   * 電子メ **[!UICONTROL Channels]** ールアドレス、携帯電話番号、オプトアウト情報を含むカテゴリでは、プロファイルに到達可能なチャネルを特定できます。
   * プロフ **[!UICONTROL No longer contact]** ァイルがチャネルを購読解除すると、カテゴリが更新されます。
   * カテゴリ **[!UICONTROL Address]** には、このプロファイルにダイレクトメールを送信するためのオプションと共に入 **[!UICONTROL Address specified]** 力する必要があ [る住所が含まれ](../../channels/using/about-direct-mail.md) ます。 このオプション **[!UICONTROL Address specified]** を選択しない場合、このプロファイルはすべてのダイレクトメール配信から除外されます。
   * カテゴ **[!UICONTROL Access authorization]** リは、プロファイルの組織単位(権限を管理す [るため](../../administration/using/about-access-management.md))を示します。 プロファイルの分割も参 [照してください](../../administration/using/organizational-units.md#partitioning-profiles)。
   * カテゴ **[!UICONTROL Traceability]** リは、プロファイルを作成または変更したユーザーに関する情報で自動的に更新されます。

1. をクリック **[!UICONTROL Create]** して、プロファイルを保存します。

これで、プロファイルがリストに表示されます。

>[!NOTE]
>
>また、Adobe Campaign Standard APIを使用してプロファイルを作成することもできます。 For more on this, refer to the [dedicated documentation](../../api/using/creating-profiles.md).

また、組織単位に応じてプロファイルをパーティションに分割することもできます。 プロファイルに組織フィールドを追加するには、 [Partitioning profilesの節を参照して](../../administration/using/organizational-units.md#partitioning-profiles) ください。

>[!NOTE]
>
>多言語メッセージを送信する際に、言語を選択する際に使用する言語フィールドを指定します。 多言語メッセージの詳細については、 [このページを参照してください](../../channels/using/creating-a-multilingual-email.md)。

**関連トピック：**

* [ランディングページについて](../../channels/using/getting-started-with-landing-pages.md) 、ステップバイステップガイドを参照してください。
* [プロファイルの読み込み](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

