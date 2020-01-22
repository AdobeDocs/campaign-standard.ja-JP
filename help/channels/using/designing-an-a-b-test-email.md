---
title: A/B テスト用電子メールのデザイン
description: A/Bテスト機能を発見し、次の手順に従って、Adobe CampaignのA/Bテストテンプレートから電子メールを作成します。
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# A/B テスト用電子メールのデザイン{#designing-an-a-b-test-email}

Adobe CampaignのA/Bテスト機能を使用すると、2 ～ 3種類の電子メールバリアントを定義できます。 各バリアントは、最良の結果を得るために母集団サンプルに送信されます。 判定が終わると、勝者のバリアントが残りの母集団に送信されます。

電子メールのコンテンツ、件名、送信者を変更できます。

>[!NOTE]
>
>Adobe Experience Managerで作成された電子メールに対するA/Bテストはできません。

## Creating an A/B test email {#creating-an-a-b-test-email}

A/Bテストは、A/Bテストの設定手順を追加する標準の電子メール作成ウィザードを使用して作成できます。 標準電子メールの作成について詳しくは、「電子メールの作 [成」の節を参照してく](../../channels/using/creating-an-email.md) ださい。

A/Bテストの具体的なコンテキスト：

1. 変更する要素に応じて、3つのA/Bテスト固有のテンプレートのいずれかから新しい電子メールを作成します。

   * 送信者に対するA/Bテスト
   * コンテンツに対するA/Bテスト
   * 主題に関するA/Bテスト
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >フォローアップおよびA/Bテストテンプレートは、デフォルトで非表示になっています。 左側のA/Bテストボックス（横パネル）にチェッ **[!UICONTROL Filter]**クマークを付けて表示します。

1. 標準電子メールと同様に、電子メールの一般プロパティとターゲットオーディエンスを定義します。 「オーディエンスの作成 [」の節を参照](../../audiences/using/creating-audiences.md) 。
1. 作成ウィザードの4番目の手順で、A/Bテストパラメーターを定義します。

   * **[!UICONTROL Number of variants]**:2つまたは3つのバリアントを使用するように選択できます。 3つのバリアントを選択した場合、この手順がウィザードで確認された後は、この選択を変更できません。
   * **[!UICONTROL Winning strategy]**:勝者バリアントの判定に使用する条件を選択します。
   * **[!UICONTROL Target breakdown]**:各バリアントを受け取るターゲットの割合を選択します。 残りの割合は、勝者のバリアントが決定された後に受け取ります。 ターゲットプロファイルはランダムに選択されます。
   * **[!UICONTROL Winner sending method]**:勝者のバリアントを決定後に自動的に送信するか、残りの訪問者への送信を手動で確認するかを選択します。
   * **[!UICONTROL Test duration]**:テストの期間を指定します。 勝者のバリアントは、この期間の後に自動的に決定されます。 電子メールダッシュボードから、テストの終了前に勝者のバリアントを手動で選択できます。

      すべてのトラッキングデータを収集し、勝者のバリアントを選択するために正しく考慮するには、テストが少なくとも1時間である必要があります。
   ![](assets/ab_parameters.png)

1. A/Bテストパラメーターを定義したら、ウィザードの次の手順に進み、電子メールの内容を定義します。 選択したテンプレートに応じて、複数の主題、複数の送信者名、または複数の異なるコンテンツを定義できます。 カルーセルを使用して、要素の様々なバリエーション間を移動します。 詳しくは、「コンテンツエディター」の節 [を参照してくださ](../../designing/using/designing-content-in-adobe-campaign.md) い。

   ![](assets/create_ab_testing2.png)

1. 電子メールの作成を確認します。 電子メールダッシュボードが表示されます。
1. 送信をスケジュールします。 定義された日付は、A/Bテストの開始を示します。
1. ブロックに表示されているA/Bテストパラメータを確認し **[!UICONTROL A/B test parameters]**ます。 ブロックを選択して、テストの送信を確認する（手順9）まで変更できます。

   ![](assets/create_ab_testing3.png)

1. ターゲットと送信するメッセージの数を分析するために、電子メール送信を準備します。 「送信の準 [備」を参照してください](../../sending/using/preparing-the-send.md) 。
1. A/Bテストを送信する前に、校正を送信して電子メールを確認します。
1. 準備が完了したら、テストの送信を確認します。 確認後は、A/Bテストのパラメーターを変更できません。

   A/Bテストは、で定義された日付に開始します。 **[!UICONTROL Schedule]**とのブロックを使用して進行状況を追**[!UICONTROL A/B test]** 跡でき **[!UICONTROL Deployment]**ます。

   テスト期間を短くする場合は、いつでも勝者のバリアントを手動で選択できます。

   テストが完了すると、概要テーブルがブロックに表示され **[!UICONTROL A/B Test]**、テストされた異なるバリアントに関する様々なインジケーターを表示できます。

1. 送信方法として選択し **[!UICONTROL Send after confirmation]**た場合は、勝者のバリアントを手動で選択して、残りの訪問者への送信を開始する必要があります。 選択した場合、勝**[!UICONTROL Automatic]**&#x200B;者のバリアントは、システムによって決定されるとすぐに残りの母集団に自動的に送信されます。

   >[!NOTE]
   >
   >関連付けがある場合は、勝者のバリアントを手動で選択する必要があります。 バリアントが選択されたか、選択する必要があることを電子メールの作成者および修飾子に通知できます。 詳しくは、 [Adobe Campaign通知を参照してください](../../administration/using/sending-internal-notifications.md)。

電子メールが定義され、送信されます。 ログやレポートにアクセスして、キャンペーンの成功を測定できます。

**関連トピック**:

[電子メールビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html) （英語のみ）

## A/Bテストインジケーターについて {#about-a-b-test-indicators}

電子メールダッシュボードには、A/Bテストの測定に役立つ次のインジケーターがいくつか用意されています。クリック数、開く回数、バウンス数など。

このインジケータ **[!UICONTROL Estimated recipient reactivity]**ーは、クリックした受信者の数と電子メールを開いた受信者の数とを比較した率です。 例えば、10人の受信者が電子メールを開き、5人の受信者が電子メールをクリックしたとします。 反応率は50%である。
