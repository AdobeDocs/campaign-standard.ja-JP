---
title: プロファイルの作成
description: API、インポート機能、オンライン獲得、自動または手動更新を使用して、プロファイルを作成し、連絡先のデータを収集する方法を説明します。
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
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 3%

---


# プロファイルの作成{#creating-profiles}

Adobe Campaignでは、プロファイルはデフォルトでメッセージのメインターゲットの定義に使用されます。

キャンペーンでプロファイルを作成または更新するには、次の操作を行います。

* ワークフローを使用したファイルからのプロファイルリストの読み込み [](../../automating/using/creating-import-workflow-templates.md)
* [ランディングページを介してオンラインでデータを収集](../../channels/using/getting-started-with-landing-pages.md)
* [REST APIを使用した一括作成](../../api/using/get-started-apis.md)
* [Microsoft Dynamicsのプロファイルの同期](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* 以下に説明するように、グラフィカルインターフェイス画面を使用してデータを入力します

例えば、ユーザーインターフェイスに直接新しいプロファイルを作成するには、次の手順に従います。

1. Adobe Campaignホームページで、「 **プロファイル** 」カードまたは「 **プロファイル** 」タブをクリックして、プロファイルのリストにアクセスします。

   ![](assets/profile_creation_1.png)

1. 次に、をクリックし **[!UICONTROL Create]**&#x200B;ます。

   ![](assets/profile_creation.png)

1. プロファイルデータを入力します。

   ![](assets/profile_creation1.png)

   * 姓、姓、性別、生年月日、写真、好みの言語( [多言語電子メールの場合](../../channels/using/creating-a-multilingual-email.md))などの連絡先配信を使用すると、情報をパーソナライズしやすくなります。
   * プロファイルのタイムゾーン **[!UICONTROL Time zone]** で配信を送信するには、プロファイルのタイムゾーンが使用されます。 詳しくは、[この節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。
   * 電子メールアドレス、携帯電話番号、オプトアウト情報を含む **[!UICONTROL Channels]** カテゴリは、プロファイルに到達可能なチャネルを通知します。
   * プロファイルがチャネルを登録解除すると、 **[!UICONTROL No longer contact]** カテゴリはすぐに更新されます。
   * この **[!UICONTROL Address]** カテゴリには、このプロファイルにダイレクトメールを送信するためのオプションと共に、入力する必要がある **[!UICONTROL Address specified]** 住所が含まれています [](../../channels/using/about-direct-mail.md) 。 この **[!UICONTROL Address specified]** オプションを選択しない場合、このプロファイルはすべてのダイレクトメール配信から除外されます。
   * カテゴリは、プロファイルの組織単位(権限の **[!UICONTROL Access authorization]** 管理 [](../../administration/using/about-access-management.md))を示します。 プロファイルの [分割も参照してください](../../administration/using/organizational-units.md#partitioning-profiles)。
   * カテゴリは、プロファイルの作成または変更を行ったユーザに関する情報で自動的に更新されます。 **[!UICONTROL Traceability]**

1. をクリック **[!UICONTROL Create]** して、プロファイルを保存します。

プロファイルがリストに表示されます。

>[!NOTE]
>
>プロファイルの作成は、Adobe Campaign標準APIを使用しても可能です。 For more on this, refer to the [dedicated documentation](../../api/using/creating-profiles.md).

プロファイルは、組織単位に応じて分割することもできます。 組織のフィールドをプロファイルに追加するには、「 [プロファイルの](../../administration/using/organizational-units.md#partitioning-profiles) 分割」の項を参照してください。

>[!NOTE]
>
>多言語メッセージを送信する際に、言語を選択する際に優先言語フィールドを使用します。 多言語メッセージの詳細については、このページ [を参照してください](../../channels/using/creating-a-multilingual-email.md)。

**関連トピック：**

* [ランディングページ](../../channels/using/getting-started-with-landing-pages.md) — ステップバイステップガイド
* [プロファイル](https://video.tv.adobe.com/v/24993?captions=jpn) ・ビデオの読み込み
