---
title: A/BテストのEメールの設計
seo-title: A/BテストのEメールの設計
description: A/BテストのEメールの設計
seo-description: A/Bテスト機能を確認し、次の手順に従って、Adobe CampaignのA/Bテストテンプレートから電子メールを作成します。
page-status-flag: 未活性化の
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: E-メールメッセージ
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: 配信，abTesting,back；配信作成，ウィザード；配信，メイン
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# A/BテストのEメールの設計{#designing-an-a-b-test-email}

Adobe CampaignのA/Bテスト機能を使用すると、2 ~ 3つのEメールバリアントを定義できます。 各変異体は、最も良い結果を持つ個体を決定するために母集団標本に送られる。 決定されると、勝ち抜きのバリアントが残りの母集団に送られます。

電子メールの内容、件名、または送信者を変更できます。

>[!NOTE]
>
>Adobe Experience Managerで作成された電子メールに対するA/Bテストは行えません。

## A/Bテスト用の電子メールの作成 {#creating-an-a-b-test-email}

A/Bテストは、A/Bテスト構成ステップが追加された標準の電子メール作成ウィザードを使用して作成できます。 標準の電子メールの作成の詳細については、「電子メールの作 [成」の項を参照してく](../../channels/using/creating-an-email.md) ださい。

A/Bテストの特定のコンテキストで、次の操作を行います。

1. 変更する要素に従って、3つのA/Bテスト用の特定のテンプレートの1つから新しい電子メールを作成します。

   * 送信者のA/Bテスト
   * コンテンツのA/Bテスト
   * A/Bテスト（対象）
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >フォローアップとA/Bテストテンプレートは、既定では非表示になっています。 左側（横パネル）のA/Bテストボックスをチェ **[!UICONTROL Filter]** ックして表示します。

1. 標準の電子メールと同様に、電子メールの一般プロパティと対象ユーザーを定義します。 「対象ユーザーの作 [成」の項を参照](../../audiences/using/creating-audiences.md) 。
1. 作成ウィザードの4番目の手順で、A/Bテスト·パラメータを定義します。

   * **[!UICONTROL Number of variants]**:2つまたは3つのバリアントを使用することができます。 3つのバリアントを選択した場合は、ウィザードでこの手順を確認した後で、この選択を変更することはできません。
   * **[!UICONTROL Winning strategy]**:勝ち抜きのバリアントを決定する基準を選択します。
   * **[!UICONTROL Target breakdown]**:各バリアントを受け取るターゲットの割合を選択します。 残りのパーセンテージは、決定された後に獲得したバリアントを受け取ります。 ターゲットプロファイルはランダムに選択されます。
   * **[!UICONTROL Winner sending method]**:決定後に、勝ち抜いたバリアントを自動的に送信するか、残りの母集団への送信を手動で確認するかを選択します。
   * **[!UICONTROL Test duration]**:テストの期間を指定します。 当選バリアントは、この期間の後に自動的に決定されます。 Eメールダッシュボードから、テストの終了前に、勝ち取ったバリアントを手動で選択できます。

      すべての追跡データを収集し、正しく考慮して当選バリアントを選択するには、テストが少なくとも1時間必要です。
   ![](assets/ab_parameters.png)

1. A/Bテスト·パラメータを定義したら、ウィザードの次の手順に進み、電子メール·コンテンツを定義します。 選択したテンプレートに応じて、複数の件名、複数の送信者名、または複数の異なる内容を定義できます。 カルーセルを使用して、要素の異なるバリアント間を移動します。 詳細については、コンテンツエディタのセクシ [ョンを参照してくださ](../../designing/using/overview.md) い。

   ![](assets/create_ab_testing2.png)

1. 電子メールの作成を確認します。 次に、電子メールのダッシュボードが表示されます。
1. 送信をスケジュールします。 定義された日付は、A/Bテストの開始を示します。
1. ブロックに表示されているA/Bテストパラメータを確認 **[!UICONTROL A/B test parameters]** します。 ブロックを選択して、テストの送信を確認（手順9）するまで、それらを修正できます。

   ![](assets/create_ab_testing3.png)

1. 送信先と送信するメッセージの数を分析するために、電子メール送信を準備します。 「送信の準 [備」の項を参照](../../sending/using/preparing-the-send.md) 。
1. A/Bテストを送信する前に、校正を送信してメールを確認してください。
1. 準備が完了したら、テストの送信を確認します。 確認後、A/Bテストパラメータは変更できません。

   A/Bテストは、で定義された日付から開始します。 **[!UICONTROL Schedule]**&#x200B;とのブロックを使用して、その進行状況を追跡 **[!UICONTROL A/B test]** でき **[!UICONTROL Deployment]** ます。

   テスト期間を短くする場合は、いつでも手動で優勝バリアントを選択できます。

   テストが完了すると、ブロックに要約テーブルが表示され、テストさ **[!UICONTROL A/B Test]** れた異なるバリアントのさまざまなインジケータを表示できます。

1. 送信方法として選 **[!UICONTROL Send after confirmation]** 択した場合は、残りの母集団への送信を開始するには、獲得したバリアントを手動で選択する必要があります。 を選択した場合、 **[!UICONTROL Automatic]**&#x200B;勝ち抜いたバリアントは、システムによって決定されるとすぐに、残りの母集団に自動的に送信されます。

   >[!NOTE]
   >
   >タイがある場合は、勝ちのバリアントを手動で選択する必要があります。 バリアントが選択されたか、選択する必要があることを電子メールの作成者と修飾子に通知できます。 「 [Adobe Campaignの通知」を参照](../../administration/using/sending-internal-notifications.md)。

メールが定義され、送信されました。 そのログとレポートにアクセスして、キャンペーンの成功を測定できます。

**関連トピック**:

[電子メールビデオの作成](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) ..

## A/Bテスト·インジケータについて {#about-a-b-test-indicators}

電子メールダッシュボードには、A/Bテストの測定に役立ついくつかのインジケータが表示されます。クリック回数、開く回数、バウンス回数など。

このインジケータ **[!UICONTROL Estimated recipient reactivity]** は、クリックした受信者の数と、電子メールを開いた受信者の数とを比較した率です。 たとえば、10人の受信者が電子メールを開き、5人の受信者が電子メールをクリックしたとします。 反応率は50%であった。
