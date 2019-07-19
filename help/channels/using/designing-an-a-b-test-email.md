---
title: A/Bテスト用電子メールのデザイン
seo-title: A/Bテスト用電子メールのデザイン
description: A/Bテスト用電子メールのデザイン
seo-description: A/Bテスト機能を作成し、次の手順に従ってAdobe CampaignでA/Bテストテンプレートから電子メールを作成します。
page-status-flag: 常にアクティブ化されていない
uuid: 104f6973-68a7-4692- a90a- a5570a980ec7
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: 電子メールメッセージ
discoiquuid: e249ba70-90d0-43f2-868c- ce9fdc7e642d
context-tags: delivery， abtesting， back;DeliveryCreation，ウィザード;delivery， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Designing an A/B test email{#designing-an-a-b-test-email}

Adobe CampaignのA/Bテスト機能を使用すると、2~3つの電子メールバリアントを定義できます。各バリエーションは、最適な結果があるかどうかを判断するために、母集団のサンプルに送信されます。決定すると、勝者のバリエーションが残りの母集団に送信されます。

電子メールのコンテンツ、件名または送信者を変更できます。

>[!NOTE]
>
>Adobe Experience Managerで作成された電子メールに関するA/Bテストはできません。

## Creating an A/B test email {#creating-an-a-b-test-email}

A/Bテストは、標準の電子メール作成ウィザードを使用して作成し、A/Bテストの設定手順を追加することができます。Creating a standard email is detailed in the [Creating an email](../../channels/using/creating-an-email.md) section.

A/Bテストの特定のコンテキスト内:

1. 変化する要素に従って、3つのA/Bテスト専用テンプレートのいずれかから新しい電子メールを作成します。

   * 送信者に対するA/Bテスト
   * コンテンツのA/Bテスト
   * 件名のA/Bテスト
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >フォローアップおよびA/Bテストテンプレートは、デフォルトでは非表示です。Check the A/B test box on the left side ( **[!UICONTROL Filter]** lateral panel) to display them.

1. 標準の電子メールと同様に、電子メールの一般的なプロパティとターゲットオーディエンスを定義します。Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. 作成ウィザードの4つ目の手順で、A/Bテストパラメーターを定義します。

   * **[!UICONTROL Number of variants]**:2つまたは3つのバリエーションを使用できます。3つのバリアントを選択した場合、この手順の後にこの選択肢を変更することはできません。
   * **[!UICONTROL Winning strategy]**:勝者バリアントの決定に使用する条件を選択します。
   * **[!UICONTROL Target breakdown]**:各バリエーションを受け取るターゲットの割合を選択します。残りの割合は、決定されたら勝者のバリアントを受け取ります。ターゲットプロファイルはランダムに選択されます。
   * **[!UICONTROL Winner sending method]**:勝者のバリアントを決定した後に自動的に送信するかどうかを選択します。または、残りの母集団への送信を手動で確認するかどうかを選択します。
   * **[!UICONTROL Test duration]**:テストの期間を指定します。勝者のバリエーションは、この期間後に自動的に決定されます。電子メールダッシュボードからテストの終了前に、手動で勝者のバリエーションを選択できます。

      すべてのトラッキングデータが収集され、勝者のバリアントを選択するために正しく考慮されるには、テストは少なくとも1時間である必要があります。
   ![](assets/ab_parameters.png)

1. A/Bテストパラメータが定義されたら、ウィザードの次の手順に合格して電子メールコンテンツを定義します。選択したテンプレートに応じて、複数の件名、複数の送信者名、複数の異なるコンテンツを定義できます。カルーセルを使用して、要素の異なるバリエーション間を移動します。For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/create_ab_testing2.png)

1. 電子メールの作成を確認します。その後、電子メールダッシュボードが表示されます。
1. 送信をスケジュールします。定義された日付は、A/Bテストの開始を示します。
1. **[!UICONTROL A/B test parameters]** ブロックに表示されているA/Bテストパラメーターを確認します。ブロックを選択してテスト（手順9）を送信するまで、それらを変更できます。

   ![](assets/create_ab_testing3.png)

1. 送信するメッセージのターゲットと数を分析するための電子メール送信を準備します。Consult the [Preparing the send](../../sending/using/preparing-the-send.md) section.
1. A/Bテストを送信する前に、配達確認を送信して電子メールをチェックしてください。
1. 準備が完了したら、テストの送信を確認します。確認後、A/Bテストパラメーターは変更できません。

   The A/B test starts on the date defined in the **[!UICONTROL Schedule]**.You can track its progress using the **[!UICONTROL A/B test]** and **[!UICONTROL Deployment]** blocks.

   テスト期間を短くする場合は、いつでも勝者のバリエーションを手動で選択できます。

   Once testing has finished, a summary table is displayed in the **[!UICONTROL A/B Test]** block and this allows you to view the various indicators for the different variants that were tested.

1. If you have selected **[!UICONTROL Send after confirmation]** as the sending method, you have to manually select the winning variant to start sending it to the remaining population. If you have selected **[!UICONTROL Automatic]**, the winning variant is automatically sent to the remaining population as soon as it has been determined by the system.

   >[!NOTE]
   >
   >ネクタイがある場合、勝者のバリエーションを手動で選択する必要があります。バリアントが選択されたか、選択されているかを電子メールの作成者と修飾子に通知できます。See [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

電子メールが定義および送信されるようになりました。キャンペーンの成功を測定するために、ログおよびレポートにアクセスできます。

**関連トピック**:

[電子メール](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) ビデオの作成

## About A/B test indicators {#about-a-b-test-indicators}

電子メールダッシュボードでは、A/Bテストの測定に役立ついくつかのインジケーターを利用できます。クリック数、開封数、バウンス数などです。

**[!UICONTROL Estimated recipient reactivity]** このインジケーターは、電子メールを開いた受信者の数をクリックした受信者数を比較するレートです。例えば、10人の受信者が電子メールを開き、5人の受信者がクリックしたとします。反応率は50%です。
