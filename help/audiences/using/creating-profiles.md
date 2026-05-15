---
title: プロファイルの作成
description: API、インポート機能、オンライン獲得、自動または手動更新を使用して、プロファイルを作成し、連絡先のデータを収集する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Beginner
exl-id: 827df9f6-070c-466a-890c-e363de6b129b
TQID: https://experienceleague.adobe.com/STHpDRtsdjT7OMDg3aOtVHdzqLokzOxvM2PI0ho9WLA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 395
ht-degree: 84%

---

# プロファイルの作成{#creating-profiles}

Adobe Campaign では、メッセージのメインターゲットを定義する際に、プロファイルがデフォルトで使用されます。

>[!NOTE]
>
>プロファイルの作成は、Adobe Campaign Standard API を使用しても可能です。 詳しくは、[該当するドキュメント](../../api/using/creating-profiles-api.md)を参照してください。

![](assets/do-not-localize/how-to-video.png) [&#x200B; ビデオでワークフローを使用してプロファイルを読み込む方法を確認](#video)

Campaign でプロファイルを作成または更新するには、次の操作をおこないます。

* [ワークフロー](../../automating/using/creating-import-workflow-templates.md)を使用してプロファイルのリストをインポートする
* [ランディングページ](../../channels/using/getting-started-with-landing-pages.md)からオンラインでデータを収集する
* [REST API](../../api/using/get-started-apis.md) を使用して一括作成する
* [Microsoft Dynamics](../../integrating/using/d365-acs-get-started.md) からプロファイルを同期する
* 以下で説明するように、ユーザーインターフェイスを使用してデータを入力します

例えば、ユーザーインターフェイスで直接新しいプロファイルを作成するには、次の手順に従います。

1. Adobe Campaign ホームページで、「**顧客プロファイル**」カードまたは「**プロファイル**」タブをクリックして、プロファイルのリストにアクセスします。

   ![](assets/profile_creation_1.png)

1. 「**[!UICONTROL Create]**」をクリックします。

   ![](assets/profile_creation.png)

1. プロファイルデータを入力します。

   ![](assets/profile_creation1.png)

   * 姓、名、性別、生年月日、写真、優先言語（[多言語メールの場合](../../channels/using/creating-a-multilingual-email.md)）などの連絡先情報を使用すると、配信をパーソナライズしやすくなります。
   * プロファイルの **[!UICONTROL Time zone]** を設定すると、配信がプロファイルのタイムゾーンに従って送信されます。 詳しくは、[この節](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。
   * メールアドレス、携帯電話番号、オプトアウト情報などの **[!UICONTROL Channels]** カテゴリを使用すると、プロファイルにリーチ可能なチャネルを把握できます。

     >[!NOTE]
     > 携帯電話番号は、プロファイルテーブルでは常に国際形式（`+<country><number>`）である必要があります。

   * プロファイルでチャネルが購読解除されると、**[!UICONTROL No longer contact]** カテゴリはただちに更新されます。
   * **[!UICONTROL Address]** カテゴリには住所の欄があり、このプロファイルに[ダイレクトメール](../../channels/using/about-direct-mail.md)を送る場合は「**[!UICONTROL Address specified]**」オプションと合わせて入力する必要があります。 「**[!UICONTROL Address specified]**」オプションを選択しない場合、このプロファイルはすべてのダイレクトメール送付から除外されます。
   * **[!UICONTROL Access authorization]** カテゴリは、[権限を管理](../../administration/using/about-access-management.md)するためのプロファイルの組織単位を示します。 組織関連のフィールドをプロファイルに追加するには、[プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)の節を参照してください。
   * 「**[!UICONTROL Traceability]**」カテゴリは、プロファイルの作成または変更をおこなったユーザーに関する情報により自動的に更新されます。

1. 「**[!UICONTROL Create]**」をクリックして、プロファイルを保存します。

プロファイルがリストに表示されます。

>[!NOTE]
>優先言語フィールドは、多言語メッセージを送信する際に言語を選択するために使用します。 多言語メッセージの詳細については、[このページ](../../channels/using/creating-a-multilingual-email.md)を参照してください。

## チュートリアルビデオ {#video}

このビデオでは、ワークフローでプロファイルを読み込む方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/24993?quality=12)

その他のCampaign Standardのハウツー動画は[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)でご覧いただけます。
