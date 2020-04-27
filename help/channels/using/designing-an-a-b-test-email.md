---
title: A/B テスト用電子メールのデザイン
description: A/Bテスト機能を見つけ、次の手順に従って、Adobe CampaignのA/Bテストテンプレートから電子メールを作成します。
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# A/B テスト用電子メールのデザイン{#designing-an-a-b-test-email}

Adobe CampaignのA/Bテスト機能を使用すると、2 ～ 3種類の電子メールのバリエーションを定義できます。 各バリアントは、最良の結果を得るために母集団サンプルに送信されます。 判定が終わると、勝者のバリアントが残りの母集団に送信されます。

電子メールの内容、件名、送信者を変更できます。

>[!NOTE]
>
>Adobe Experience Managerで作成された電子メールに対するA/Bテストはできません。

## Creating an A/B test email {#creating-an-a-b-test-email}

A/Bテストは、A/Bテストの設定手順を追加する標準の電子メール作成ウィザードを使用して作成できます。 標準電子メールの作成について詳しくは、「電子メールの [作成」の節を参照してく](../../channels/using/creating-an-email.md) ださい。

A/Bテストの具体的なコンテキストでは、次のようになります。

1. 変更する要素に応じて、3つのA/Bテスト固有のテンプレートのいずれかから新しい電子メールを作成します。

   * 送信者に対するA/Bテスト
   * コンテンツのA/Bテスト
   * 対象に関するA/Bテスト
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >フォローアップおよびA/Bテストテンプレートは、デフォルトでは非表示になっています。 左側（横パネル）のA/Bテストボックスをチェックし&#x200B;**[!UICONTROL Filter]** て、表示します。

1. 標準の電子メールと同様に、電子メールの一般的なプロパティとターゲットオーディエンスを定義します。 「オーディエンスの作成 [](../../audiences/using/creating-audiences.md) 」を参照。
1. 作成ウィザードの4番目の手順で、A/Bテストのパラメーターを定義します。

   * **[!UICONTROL Number of variants]**:2つまたは3つのバリエーションを使用するように選択できます。 3つのバリエーションを選択した場合、この手順がウィザードで確認された後は、この選択を変更できません。
   * **[!UICONTROL Winning strategy]**:勝者のバリアントの判定に使用する条件を選択します。
   * **[!UICONTROL Target breakdown]**:各バリアントを受け取るターゲットの割合を選択します。 残りの割合は、決定された後に勝者のバリアントを受け取ります。 ターゲットプロファイルはランダムに選択されます。
   * **[!UICONTROL Winner sending method]**:勝者のバリアントを決定後に自動的に送信するか、残りの訪問者への送信を手動で確認するかを選択します。
   * **[!UICONTROL Test duration]**:テストの期間を指定します。 勝者のバリアントは、この期間の後に自動的に決定されます。 テストの終了前に、勝者のバリアントを電子メールダッシュボードから手動で選択できます。

      すべてのトラッキングデータを収集し、勝者のバリアントを正しく考慮して選択するには、テストが1時間以上である必要があります。
   ![](assets/ab_parameters.png)

1. A/Bテストパラメーターを定義したら、ウィザードの次の手順に進み、電子メールの内容を定義します。 選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なるコンテンツを定義できます。 カルーセルを使用して、要素の異なるバリエーション間を移動します。 詳しくは、コンテンツエディターの節 [を参照して](../../designing/using/designing-content-in-adobe-campaign.md) ください。

   ![](assets/create_ab_testing2.png)

1. 電子メールの作成を確認します。 電子メールダッシュボードが表示されます。
1. 送信のスケジュールを設定します。 定義された日付は、A/Bテストの開始を示します。
1. ブロック内に表示されているA/Bテストパラメータを確認 **[!UICONTROL A/B test parameters]** します。 ブロックを選択して、テスト（手順9）の送信を確認するまで変更できます。

   ![](assets/create_ab_testing3.png)

1. 電子メール送信を準備し、ターゲットと送信するメッセージ数を分析します。 「送信の準 [備」を参照](../../sending/using/preparing-the-send.md) 。
1. A/Bテストを送信する前に、電子メールを送信して確認してください。配達確認
1. 準備が完了したら、テストの送信を確認します。 確認後は、A/Bテストのパラメーターを変更できません。

   で定義された日付のA/Bテスト開始 **[!UICONTROL Schedule]**。 ブロックとブロックを使用して、進行状況を追 **[!UICONTROL A/B test]** 跡で **[!UICONTROL Deployment]** きます。

   テスト期間を短くしたい場合は、いつでも勝者のバリアントを手動で選択できます。

   テストが完了すると、概要テーブルがブロックに表示され、これによ **[!UICONTROL A/B Test]** り、テストされた異なるバリエーションの様々なインジケータを表示できます。

1. 送信方法として選択し **[!UICONTROL Send after confirmation]** た場合は、勝者のバリアントを手動で選択し、残りの母集団に送信する開始に送信する必要があります。 選択した場合、勝者 **[!UICONTROL Automatic]**&#x200B;のバリアントは、システムによって決定されるとすぐに残りの母集団に自動的に送信されます。

   >[!NOTE]
   >
   >結び付きがある場合は、勝者のバリアントを手動で選択する必要があります。 バリアントが選択されたか、選択する必要があることを電子メールの作成者および修飾子に通知できます。 詳しくは、 [Adobe Campaign通知を参照](../../administration/using/sending-internal-notifications.md)。

電子メールが定義され、送信されました。 ログやレポートにアクセスして、成功度を測定できます。キャンペーン

**関連トピック**:

[電子メールビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html) （英語）

## A/Bテストインジケーターについて {#about-a-b-test-indicators}

電子メールダッシュボードには、A/Bテストの測定に役立つ次のインジケーターがいくつか用意されています。クリック数、開く回数、バウンス数など。

このインジケータ **[!UICONTROL Estimated recipient reactivity]** ーは、クリックした受信者の数と電子メールを開いた受信者の数とを比較した割合です。 例えば、10人の受信者が電子メールを開き、5人の受信者がクリックしたとします。 反応率は50%です。
