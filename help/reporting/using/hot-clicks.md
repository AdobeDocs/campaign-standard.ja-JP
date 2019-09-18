---
title: ホットクリック
seo-title: ホットクリック
description: ホットクリック
seo-description: 最新のクリック音がすぐに届くレポートで、お客様がお客様の提供をクリックした場所を確認します。
page-status-flag: 未活性化の
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 報告
content-type: 参照
topic-tags: レポート一覧
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: 配信HotClicksReport，メイン
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# ホットクリック{#hot-clicks}

このレポートは、各配信メッセージまたはトランザクシ **[!UICONTROL Reports]** ョンメッセージのボタンからアクセスできます。

![](assets/delivery_reports_hot-clicks_4.png)

各リンクのクリック回数の割合で、メッセージの内容（HTMLまたはテキスト）を表示します。

![](assets/delivery_reports_10.png)

配信用に動的コンテンツを作成した場合は、定義した各条件のパーセンテージを表示できます。 デリバリへの条件付きコンテンツの挿入の詳細については、「動的コンテンツの定義」 [を参照してくださ](../../channels/using/defining-dynamic-content-in-a-landing-page.md)い。

たとえば、次の条件で搬送を作成したとします。

* 受信者が男性か女性の場合、メイン画像のリンクは異なります。
* また、25を超える受信者にのみ表示される特別なオファーへのリンクも追加しました。

メッセージが送信されたら、配信ダッシュボ **[!UICONTROL Reports]** ードか **[!UICONTROL Hot clicks]** ら「&gt;」を選択します。

既定では、プロファイルは選択されていません。 性別が不明な受信者と、25歳未満または年齢が不明な受信者に対してのみ、クリックが表示されます。

![](assets/delivery_reports_hot-clicks_1.png)

女性のクリックを表示するには、ボタンをク **[!UICONTROL Change profile]** リックし、女性のテストプロファイルを選択します。 男性用のクリックを表示するには、同様に操作し、男性のテストプロファイルを選択します。

![](assets/delivery_reports_hot-clicks_2.png)

25を超える受信者のクリックを表示するには、ボタンをク **[!UICONTROL Change profile]** リックし、この条件に一致する生年月日のテストプロファイルを選択します。

テストプロファイルの詳細については、「テストプロファイルにつ [いて」を参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)い。

>[!NOTE]
>
>特定のリンクでのクリック回数は、配信内のすべての条件付きコンテンツに対するクリック回数の合計に対する割合です。 したがって、動的コンテンツを定義した場合、特定のテストプロファイルに表示されるパーセンテージの合計は100とは異なる場合があります。

同様に、繰り返し配信とトランザクション·メッセージの場合は、表示する動的コンテンツに対応するテスト·プロファイルを選択できますが、選択した実行配信に応じてクリック率を表示することもできます。

実行配信は、次の場合に作成される、非アクションで非機能な技術メッセージです。

* 繰り返し配信が実行または更新されるたびに、

   たとえば、この配信を管理するワークフローが月に1回実行される場合、1か月に1回実行配信が行われます。 さらに、配信の内容が更新されるたびに、追加の実行配信が作成されます。

   定期的な電子メール配信の詳細については、「電子メール配信」を参 [照してくださ](../../automating/using/email-delivery.md)い。

* トランザクションメッセージの場合は、既定で月に1回、トランザクションメッセージが編集され、再発行されるたびに、

   トランザクション·メッセージの詳細は、「トランザクション·メッセ [ージについて」を参照してくださ](../../channels/using/about-transactional-messaging.md)い。

>[!NOTE]
>
>追跡されるURLのIDは実行ごとに異なるため、特定のメッセージのすべての実行配信に対してホットクリックデータを集計することはできません。 一度に表示できるのは、1つの実行デリバリに対してのみです。

メッセージが送信されたら、配信ダッシュボ **[!UICONTROL Reports]** ードか **[!UICONTROL Hot clicks]** ら「&gt;」を選択します。

デフォルトでは、最後の実行配信が選択されます。 別のボタンをク **[!UICONTROL Change execution delivery]** リックして選択します。

![](assets/delivery_reports_hot-clicks_3.png)

選択した搬送実行のクリック率のみが表示されます。
