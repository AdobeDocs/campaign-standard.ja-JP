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
ht-degree: 100%

---


# プロファイルの作成{#creating-profiles}

Adobe Campaign では、メッセージのメインターゲットを定義する際に、プロファイルがデフォルトで使用されます。

Campaign でプロファイルを作成または更新するには、次の操作をおこないます。

* [ワークフロー](../../automating/using/creating-import-workflow-templates.md)を使用してプロファイルのリストをインポートする
* [ランディングページ](../../channels/using/getting-started-with-landing-pages.md)からオンラインでデータを収集する
* [REST API](../../api/using/get-started-apis.md) を使用して一括作成する
* [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) からプロファイルを同期する
* 以下に説明するように、グラフィカルインターフェイス画面からデータを入力する

例えば、ユーザーインターフェイスで直接新しいプロファイルを作成するには、次の手順に従います。

1. Adobe Campaign ホームページで、「**顧客プロファイル**」カードまたは「**プロファイル**」タブをクリックして、プロファイルのリストにアクセスします。

   ![](assets/profile_creation_1.png)

1. 次に、「**[!UICONTROL Create]**」をクリックします。

   ![](assets/profile_creation.png)

1. プロファイルデータを入力します。

   ![](assets/profile_creation1.png)

   * 姓、名、性別、生年月日、写真、優先言語（[多言語 E メールの場合](../../channels/using/creating-a-multilingual-email.md)）などの連絡先情報を使用すると、配信をパーソナライズしやすくなります。
   * プロファイルの **[!UICONTROL Time zone]** を設定すると、配信がプロファイルのタイムゾーンに従って送信されます。詳しくは、[この節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。
   * E メールアドレス、携帯電話番号、オプトアウト情報などの **[!UICONTROL Channels]** カテゴリを使用すると、プロファイルにリーチ可能なチャネルを把握できます。
   * プロファイルでチャネルが購読解除されると、**[!UICONTROL No longer contact]** カテゴリはただちに更新されます。
   * **[!UICONTROL Address]** カテゴリには住所の欄があり、このプロファイルに[ダイレクトメール](../../channels/using/about-direct-mail.md)を送る場合は「**[!UICONTROL Address specified]**」オプションと合わせて入力する必要があります。「**[!UICONTROL Address specified]**」オプションを選択しない場合、このプロファイルはすべてのダイレクトメール送付から除外されます。
   * 「**[!UICONTROL Access authorization]**」カテゴリは、プロファイルの組織単位（[権限の管理](../../administration/using/about-access-management.md)に使用）を表します。[プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)も参照してください。
   * 「**[!UICONTROL Traceability]**」カテゴリは、プロファイルの作成または変更をおこなったユーザーに関する情報により自動的に更新されます。

1. 「**[!UICONTROL Create]**」をクリックして、プロファイルを保存します。

プロファイルがリストに表示されます。

>[!NOTE]
>
>プロファイルの作成は、Adobe Campaign Standard API を使用しても可能です。詳しくは、[該当するドキュメント](../../api/using/creating-profiles.md)を参照してください。

プロファイルは、組織単位に応じて分割することもできます。組織関連のフィールドをプロファイルに追加するには、[プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)の節を参照してください。

>[!NOTE]
>
>優先言語フィールドは、多言語メッセージを送信する際に言語を選択するために使用します。多言語メッセージの詳細については、[このページ](../../channels/using/creating-a-multilingual-email.md)を参照してください。

**関連トピック：**

* [ランディングページについて](../../channels/using/getting-started-with-landing-pages.md) - ステップバイステップガイド
* [プロファイルのインポート](https://video.tv.adobe.com/v/24993?captions=jpn) - ビデオ
