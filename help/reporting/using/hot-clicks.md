---
title: ホットクリック
seo-title: ホットクリック
description: ホットクリック
seo-description: '[ホットクリック]レポートで、顧客が配信をクリックした場所を確認します。'
page-status-flag: 常にアクティブ化されていない
uuid: 7ed49dd3- d7ee-466a-9a7b- d2aa16961667
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのリスト
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: DeliveryHotclicksReport， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Hot clicks{#hot-clicks}

This report can be accessed from the **[!UICONTROL Reports]** button in each delivery or transactional message.

![](assets/delivery_reports_hot-clicks_4.png)

各リンクのクリック数の割合を示すメッセージコンテンツ（HTMLまたはテキスト）が表示されます。

![](assets/delivery_reports_10.png)

配信の動的コンテンツを作成した場合は、定義した各条件の割合を表示できます。For more on inserting conditional content in a delivery, see [Defining dynamic content](../../designing/using/defining-dynamic-content-in-a-landing-page.md).

例えば、次の条件を使用して配信を作成したとします。

* 受信者が男性または女性の場合、メイン画像上のリンクは異なります。
* 25を超える受信者にのみ表示される特別オファーへのリンクも追加しました。

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

デフォルトでは、プロファイルは選択されていません。性別が不明な受信者、25歳未満の受信者、または年齢が不明な受信者のクリックのみが表示されます。

![](assets/delivery_reports_hot-clicks_1.png)

To display clicks for women, click the **[!UICONTROL Change profile]** button and select a female test profile. 男性のクリックを表示するには、同様に手順を続行し、男性テストプロファイルを選択します。

![](assets/delivery_reports_hot-clicks_2.png)

To display clicks for recipients over 25, click the **[!UICONTROL Change profile]** button and select a test profile whose birth date is matching this condition.

For more on test profiles, see [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

>[!NOTE]
>
>特定リンクのクリック数は、配信のすべての条件付きコンテンツのクリック数の合計に対する割合です。したがって、動的コンテンツを定義した場合、特定のテストプロファイルに対して表示される割合の合計が100と等しくない可能性があります。

同様に、定期的な配信およびトランザクションメッセージの場合、表示する動的コンテンツに対応するテストプロファイルを選択できますが、選択した実行配信に応じてクリック率を表示することもできます。

実行配信は、次の場合に作成される、実用的ではない、機能しない技術的なメッセージです。

* 定期的な配信が実行または更新されるたびに実行されます。

   例えば、この配信の管理ワークフローが月に1回実行されると、1か月に1回の実行配信が行われます。これに加えて、配信のコンテンツが更新されるたびに、追加の実行配信が作成されます。

   For more on recurring email deliveries, see [Email delivery](../../automating/using/email-delivery.md).

* トランザクションメッセージの場合は1か月につき1回、トランザクションメッセージが編集および公開されるたびに、デフォルトで発行されます。

   For more on transactional messages, see [About transactional messaging](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>トラッキングされたURLのIDは実行ごとに異なるので、特定のメッセージのすべての実行配信でホットクリックデータを集計することはできません。一度に1つの実行配信のみを表示できます。

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

デフォルトでは、最後の実行配信が選択されます。Click the **[!UICONTROL Change execution delivery]** button to select another one.

![](assets/delivery_reports_hot-clicks_3.png)

選択した配信実行のクリック率のみが表示されます。
