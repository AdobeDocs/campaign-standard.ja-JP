---
solution: Campaign Standard
product: campaign
title: A/B テスト用 E メールのデザイン
description: A/B テスト機能を使って、Adobe Campaign 内の A/B テストテンプレートから E メールを作成する方法を説明します。
audience: channels
content-type: reference
topic-tags: email-messages
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# A/B テスト用 E メールのデザイン{#designing-an-a-b-test-email}

Adobe Campaign の A/B テスト機能を使用すると、2～3 種類の E メールのバリエーションを定義できます。どのバリエーションがどのターゲットで最良の結果を得られるか確認するために、各バリエーションが母集団のサンプルに送られます。結果が明確になったら、勝者バリアントが残りの母集団に送信されます。

E メールの内容、件名、送信者を変更できます。

>[!NOTE]
>
>Adobe Experience Manager で作成された電子メールに対する A/B テストは実行できません。

## A/B テスト用 E メールのデザイン {#creating-an-a-b-test-email}

A/B テストは、通常の E メール作成ウィザードに A/B テストの設定手順を追加して作成できます。一般的な E メールの作成について詳しくは、[E メールの作成](../../channels/using/creating-an-email.md)の節を参照してください。

A/B テストの具体的なコンテキストは次のようになります。

1. 変更する要素に応じて、3 つの A/B テスト用の特定のテンプレートのいずれかから新しい E メールを作成します。

   * 送信者に対する A/B テスト
   * コンテンツに対する A/B テスト
   * 件名に関する A/B テスト

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >フォローアップおよび A/B テストテンプレートは、デフォルトで非表示になっています。左側（**[!UICONTROL Filter]**&#x200B;横パネル）の A/B テストボックスをオンにして表示します。

1. 通常の E メールと同様に、E メールの一般的なプロパティとターゲットオーディエンスを定義します。[オーディエンスの作成](../../audiences/using/creating-audiences.md)の節を参照してください。
1. 作成ウィザードの 4 番目の手順で、A/B テストパラメーターを次のように定義します。

   * **[!UICONTROL Number of variants]**：2 つまたは 3 つのバリエーションを使用するように選択できます。バリエーションを 3 つ選択した場合、この手順がウィザードで確認された後は変更できません。
   * **[!UICONTROL Winning strategy]**：勝者バリアントを決定するための条件を選択します。
   * **[!UICONTROL Target breakdown]**：各バリアントを受け取るターゲットの割合（%）を選択します。勝者バリアントが決定されたら、残りのターゲットには、判定後、その勝者バリアントが送信されます。ターゲットプロファイルはランダムに選択されます。
   * **[!UICONTROL Winner sending method]**：選択されなかったターゲットに、勝者バリアントを自動的に送信するか、送信を手動で確認するかを選択します。
   * **[!UICONTROL Test duration]**：テスト期間を指定します。勝者バリアントは、テスト期間終了後に自動的に決定されます。テストが終了する前に、電子メールダッシュボードから勝者バリアントを手動で選択できます。

      すべてのトラッキングデータを収集して適切に考慮したうえで勝者バリアントを選択するために、テスト期間は最低 1 時間必要です。
   ![](assets/ab_parameters.png)

1. A/B テストパラメーターを定義したら、ウィザードの次の手順に進み、E メールの内容を定義します。選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なる内容を定義できます。カルーセルを使用して、要素の様々なバリアント間を移動します。詳しくは、[コンテンツエディター](../../designing/using/designing-content-in-adobe-campaign.md)の節を参照してください。

   ![](assets/create_ab_testing2.png)

1. E メールの作成を確認します。E メールダッシュボードが表示されます。
1. 送信のスケジュールを設定します。定義された日付は、A/B テストの開始日を示します。
1. 「**[!UICONTROL A/B test parameters]**」ブロック内に表示されている A/B テストパラメーターを確認し ます。このパラメーターは、次の手順 9 でテストの送信を確認するまでは、ブロックを選択して変更できます。

   ![](assets/create_ab_testing3.png)

1. E メール送信を準備して、ターゲットと送信するメッセージ数を分析します。[送信の準備](../../sending/using/preparing-the-send.md)を参照してください。
1. A/B テストを送信する前に、配達確認を送信して内容を確認してください。
1. 準備が完了したら、テストの送信を確定します。確定後は、A/B テストのパラメーターを変更できません。

   A/B テストは「**[!UICONTROL Schedule]**」で定義した日に開始されます。テストの進行状況は、「**[!UICONTROL A/B test]**」および「**[!UICONTROL Deployment]**」ブロックを使用して追跡できます。

   テスト期間を短縮したい場合は、いつでも手動で勝者バリアントを選択できます。

   テストが完了すると、概要テーブルが「**[!UICONTROL A/B Test]**」ブロックに表示され、テストされた様々なバリアントの各種インジケーターを表示できます。

1. 送信方法として「**[!UICONTROL Send after confirmation]**」を選択した場合、勝者バリアントを手動で選択して、残りの母集団に送信する必要があります。送信方法として「**[!UICONTROL Automatic]**」を選択した場合、勝者バリアントはシステムで決定されしだい、残りの母集団に自動的に送信されます。

   >[!NOTE]
   >
   >結果に優劣がない場合、勝者バリアントを手動で選択する必要があります。バリアントが選択された、または選択する必要があることを、電子メールの作成者と調整者に通知できます。 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。

これで E メールが定義され、送信されます。次にログやレポートにアクセスして、キャンペーンの成功を測定できます。

## A/B テストインジケーターについて{#about-a-b-test-indicators}

E メールダッシュボードには、クリック数、開封回数、バウンス回数など、A/B テストの測定に役立ついくつかのインジケーターが用意されています。

**[!UICONTROL Estimated recipient reactivity]**&#x200B;インジケーターは、クリックした受信者の数と E メールを開いた受信者の数を比較した割合です。例えば、10 人の受信者が E メールを開き、5 人の受信者がクリックした場合、反応率は 50% です。
