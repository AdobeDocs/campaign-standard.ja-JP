---
title: プロファイルの作成
description: API、インポート機能、オンライン獲得、自動または手動の更新を使用して、プロファイルを作成し、連絡先のデータを収集する方法を説明します。
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
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# プロファイルの作成{#creating-profiles}

Adobe Campaignでは、プロファイルはデフォルトでメッセージのメインターゲットの定義に使用されます。

キャンペーンでプロファイルを作成または更新するには：

* ワークフローを使用したプロファイルリストのファイルからの読み [込み](../../automating/using/importing-data.md#example--import-workflow-template)
* データをオンラインで収集( [ランディングページ)](../../channels/using/getting-started-with-landing-pages.md)
* [REST APIを使用した一括作成](../../api/using/about-campaign-standard-apis.md)
* [Microsoft Dynamicsのプロファイルの同期](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* 以下に説明するように、グラフィカルインターフェイス画面を使用してデータを入力します。

例えば、ユーザーインターフェイスで直接新しいプロファイルを作成するには、次の手順に従います。

1. Adobe Campaignホームページで、「顧客プロファイル **」カードまたは「** プロファイル **」タブをクリックして、** リストのプロファイルにアクセスします。

   ![](assets/profile_creation_1.png)

1. 次に、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   ![](assets/profile_creation.png)

1. データをプロファイルします。

   ![](assets/profile_creation1.png)

   * 連絡先情報(名、姓、性別、生年月日、写真、お気に入りの言語(多言語電子メールの場合 [](../../channels/using/creating-a-multilingual-email.md))など)は、配信のパーソナライズに役立ちます。
   * プロファイルのタイ **[!UICONTROL Time zone]** ムゾーンで配信を送信するためにプロファイルが使用されます。 詳しくは、[この節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。
   * カテゴリ **[!UICONTROL Channels]** には、電子メールアドレス、携帯電話番号、オプトアウト情報が含まれ、プロファイルに到達可能なチャネルが示されます。
   * カテゴリ **[!UICONTROL No longer contact]** は、登録が解除されるとすぐにプロファイルが更新されます。
   * カテゴリ **[!UICONTROL Address]** には、このプロファイルにダイレクトメールを送信する際に入力する必要のある **[!UICONTROL Address specified]** 住所と共に [入力する必要があります](../../channels/using/about-direct-mail.md) 。 このオプションが **[!UICONTROL Address specified]** 選択されていない場合、このプロファイルはすべてのダイレクトメール配信から除外されます。
   * この **[!UICONTROL Access authorization]** カテゴリは、プロファイルの組織単位(権限を管 [理する](../../administration/using/about-access-management.md))を示します。 パーティション化 [プロファイル](../../administration/using/organizational-units.md#partitioning-profiles)。
   * カテゴリ **[!UICONTROL Traceability]** は、ユーザーを作成または変更したユーザーに関する情報で自動的に更新されます。プロファイル

1. をクリック **[!UICONTROL Create]** して、プロファイルを保存します。

プロファイルが表示されます。

>[!NOTE]
>
>プロファイルの作成は、Adobe Campaign Standard APIを使用して行うこともできます。 For more on this, refer to the [dedicated documentation](../../api/using/creating-profiles.md).

プロファイルは、組織単位に応じて分割することもできます。 組織のフィールドをプロファイルに追加するには、 [Partitioning Expertions](../../administration/using/organizational-units.md#partitioning-profiles) (分割プロファイル)を参照してください。

>[!NOTE]
>
>多言語メッセージを送信する際に、言語を選択するために使用する言語フィールドです。 多言語メッセージの詳細については、こ [のページを参照してください](../../channels/using/creating-a-multilingual-email.md)。

**関連トピック：**

* [ランディングページ](../../channels/using/getting-started-with-landing-pages.md) （ステップバイステップガイド）
* [読み込みプロファイル](https://video.tv.adobe.com/v/24993?captions=jpn) （ビデオ）
