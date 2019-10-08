---
title: ホットクリック
seo-title: ホットクリック
description: ホットクリック
seo-description: そのまま使用できるホットクリック数レポートを使用して、顧客が配信をクリックした場所を確認します。
page-status-flag: 非活性化の
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのリスト
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 159c33639ab7b53558dac2ce183c3801c15ccb0f

---


# ホットクリック{#hot-clicks}

このレポートは、各配信メッセージまたはトランザクシ **[!UICONTROL Reports]** ョンメッセージのボタンからアクセスできます。

![](assets/delivery_reports_hot-clicks_4.png)

メッセージコンテンツ（HTMLやテキスト）を各リンクのクリックの割合で表示します。

![](assets/delivery_reports_10.png)

配信用に動的コンテンツを作成した場合は、定義した各条件の割合を表示できます。 配信への条件付きコンテンツの挿入について詳しくは、動的コンテンツの定 [義を参照してください](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

例えば、次の条件で配信を作成したとします。

* 受信者が男性または女性の場合、メイン画像のリンクは異なります。
* また、25人を超える受信者にのみ表示される特別オファーへのリンクを追加しました。

メッセージが送信されたら、配信ダッシュボ **[!UICONTROL Reports]** ードで/ **[!UICONTROL Hot clicks]** を選択します。

デフォルトでは、プロファイルは選択されていません。 性別が不明な受信者と、25歳未満または年齢が不明な受信者に対するクリックのみが表示されます。

![](assets/delivery_reports_hot-clicks_1.png)

女性のクリック数を表示するには、ボタンをクリ **[!UICONTROL Change profile]** ックし、女性テストプロファイルを選択します。 男性のクリック数を表示するには、同様に進み、男性のテストプロファイルを選択します。

![](assets/delivery_reports_hot-clicks_2.png)

25を超える受信者のクリック数を表示するには、ボタンをク **[!UICONTROL Change profile]** リックし、生年月日がこの条件に一致するテストプロファイルを選択します。

テストプロファイルについて詳しくは、テストプロファイ [ルについてを参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)い。

>[!NOTE]
>
>特定のリンクのクリック数は、配信内のすべての条件付きコンテンツの合計クリック数に対する割合です。 したがって、動的コンテンツを定義した場合、特定のテストプロファイルに対して表示された割合の合計が100に等しくない可能性があります。

同様に、定期的な配信やトランザクションメッセージの場合は、表示する動的コンテンツに対応するテストプロファイルを選択できますが、選択した実行配信に従ってクリック率を表示することもできます。

実行配信は、次の場合に作成される、アクションを実行できない、機能しない技術的なメッセージです。

* 定期的な配信が実行または更新されるたびに発生します。

   例えば、この配信を管理するワークフローが月に1回実行される場合、1か月に1回実行配信が行われます。 さらに、配信のコンテンツが更新されるたびに、追加の実行配信が作成されます。

   定期的な電子メール配信について詳しくは、電子メール配信を参 [照してくださ](../../automating/using/email-delivery.md)い。

* デフォルトでは、トランザクションメッセージに対して1か月に1回、トランザクションメッセージが再び編集され、公開されるたびです。

   トランザクションメッセージについて詳しくは、トランザクションメッセ [ージについてを参照してくださ](../../channels/using/about-transactional-messaging.md)い。

>[!NOTE]
>
>追跡されるURLのIDは実行ごとに異なるので、特定のメッセージの実行配信のすべてに対してホットクリックデータを集計することはできません。 一度に1つの実行配信に対してのみ表示できます。

メッセージが送信されたら、配信ダッシュボ **[!UICONTROL Reports]** ードで/ **[!UICONTROL Hot clicks]** を選択します。

デフォルトでは、最後の実行配信が選択されます。 別のボタンをク **[!UICONTROL Change execution delivery]** リックして選択します。

![](assets/delivery_reports_hot-clicks_3.png)

選択した配信実行に対するクリックの割合のみが表示されます。
