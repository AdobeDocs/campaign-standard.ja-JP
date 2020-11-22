---
solution: Campaign Standard
product: campaign
title: 送信日の計算
description: 特定の日時にメッセージを送信する方法を確認します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 7%

---


# 送信日の計算{#computing-the-sending-date}

特定の日時に各受信者にメッセージを送信する数式を定義できます。

## 日付式のカスタマイズ {#customizing-date-formula}

例えば、ランプアップ処理中に送信時間の最適化を使用できます。

新しいプラットフォームを使用して E メールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量の E メールが突然送信されると、ISP はそれらの E メールをスパムとしてマークします。

スパムとしてマークされるのを防ぐために、大量の電子メールを異なる時間に配信することで、送信量を徐々に増やすことができます。 この方法により、スタートアップフェーズをスムーズに進め、無効なアドレスが全体に占める割合を減らすことができます。

例えば、ターゲットオーディエンスをランダムにセグメント化して、配信を5つのバッチで送信できます。 6月1日の午前10:00にターゲットオーディエンスの10%を表す最初のバッチを送信し、2回目のバッチを午前24時間後に送信し、15%のオーディエンスを表すバッチを送信します。

ワークフローを使用して、これをスケジュールできます。

![](assets/send-time_opt_workflow1.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。
1. Drag and drop a **Query** activity into your workflow and open it. 「 [クエリ](../../automating/using/query.md) 」の節を参照してください。
1. オーディエンス（例えば、すべてのゴールド顧客）を選択し、をクリックしてクエリ **[!UICONTROL Confirm]** を保存します。
1. Drag and drop a **Segmentation** activity into your workflow and open it. 「 [セグメント化](../../automating/using/segmentation.md) 」の節を参照してください。
1. 5つのセグメントを定義します。 各セグメントに対して、次の操作を行います。

   * フィールドに入力し **[!UICONTROL Segment code]** ます。メッセージを送信する日時を手動で入力します。

      例えば、6月1日の午前10時(GMT+1)に最初のバッチを送信するとします。 次の形式を使用します。 **YYYY-MM-DD hh:mm:ss+tz**。

      ![](assets/send-time_opt_segment_configuration.png)

      翌日に次のバッチを送信するには、2番目のセグメントに2017-06-02 **10:00:00+01** と入力します。

      残りのセグメントに対して、次のバッチを次のように定義します。

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * 必ずこの **[!UICONTROL Limit the population of this segment]** オプションを選択してください。

      タブで、 **[!UICONTROL Limitation]** 各セグメントを選択 **[!UICONTROL Random sampling]** し、必要な割合を入力します。最初のバッチは10、2番目のバッチは15、以降同様です。

      ![](assets/send-time_opt_segment_limitation.png)


1. すべてのセグメントを定義したら、を選択し **[!UICONTROL Generate all segments in the same transition]** てをクリックし **[!UICONTROL Confirm]**&#x200B;ます。

   ![](assets/send-time_opt_segment_dates.png)

1. Drag and drop an **Email delivery** activity into your workflow and open it. 「 [電子メール配信](../../automating/using/email-delivery.md) 」の節を参照してください。
1. 電子メールダッシュボードの **[!UICONTROL Schedule]** セクションをクリックし、を選択し **[!UICONTROL Messages to be sent automatically on the date specified below]**&#x200B;ます。
1. この **[!UICONTROL Start sending from]** フィールドで、連絡先の日付を定義します。
1. [送信時間の最適化]ドロップダウンメニューで、を選択し **[!UICONTROL Send at a custom date defined by a formula]**&#x200B;ます。
1. フィールドの **[!UICONTROL Edit an expression]** ボタンをクリックし **[!UICONTROL Custom date formula]** ます。

   ![](assets/send-time_opt_formula_define.png)

1. 関数とフィールドを使用して、次の式 **[!UICONTROL ToDateTime]** を作成し **[!UICONTROL Segment code]** ます。 式に直接入力することもできますが、正しい構文とスペルを使用するようにしてください。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   この **[!UICONTROL ToDateTime]** 関数は、セグメントコードをテキスト文字列から日付と時刻の値に変換します。

   前の画面に戻る式を確認します。

   ![](assets/send-time_opt_formula_define_segment.png)

   この **[!UICONTROL Schedule]** ウィンドウには、カスタム日付式が次のように表示されます。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. スケジュールを確認し、配信を保存して、ワークフローを実行します。

配信は、5日間にわたって対象となるすべての受信者にプログレッシブに送信されます。

>[!NOTE]
>
>送信を確認する際は、すべての日付が未来の日付になっていることを確認します。 それ以外の場合は、送信が確認され次第、メッセージが送信されます。

## 式の使用 {#using-an-expression}

送信時間の最適化は、コールセンターに関わるキャンペーンにも役立ちます。 すべてのメッセージを同時に受信しないようにすることができます。 これにより、組織は容量に応じて呼び出し数を処理できます。

例えば、プロモーションオファーを受け取るために、顧客がコールセンターに連絡するように勧める電子メールを送信するとします。 コールセンターの圧倒を避けるために、ターゲットオーディエンスをランダムにセグメント化して、電子メールを4つのバッチで送信することにします。

ワークフローを使用して、これをスケジュールできます。

![](assets/send-time_opt_workflow2.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。
1. Drag and drop a **Query** activity into your workflow and open it. 「 [クエリ](../../automating/using/query.md) 」の節を参照してください。
1. 例えば35プロファイル以上のオーディエンスを選択し、をクリックしてクエリ **[!UICONTROL Confirm]** を保存します。
1. Drag and drop a **Segmentation** activity into your workflow and open it. 「 [セグメント化](../../automating/using/segmentation.md) 」の節を参照してください。
1. 4つのセグメントを定義します。 各セグメントに対して、次の操作を行います。

   * セグメントコードを次のように定義します。

      * 8:00 AM ～ 10:00 AM: **0**. メッセージは、午前8時（連絡先日）にターゲットの人口の第1四半期に送信されます。
      * 10:00 AM - 12:00 PM: **2**. メッセージは、午前10時（連絡日+ 2時間）にターゲット訪問者の第2四半期に送信されます。
      * 2:00 PM - 4:00 PM: **6**. コールセンターは午後12時から午後2時の間に閉鎖され、ターゲットの第3四半期の午後2時（連絡日+ 6時間）にメッセージが送信されます。
      * 午後4時～午後6時： **8**. メッセージは、ターゲットの訪問者の最後の四半期の午後4時（連絡日+ 8時間）に送信されます。

      >[!NOTE]
      >
      >連絡先の日付は、ワークフローの後半の電子メール配信アクティビティで定義されます。

   * 必ずこの **[!UICONTROL Limit the population of this segment]** オプションを選択してください。
   * タブで、 **[!UICONTROL Limitation]** 各セグメントを選択 **[!UICONTROL Random sampling]** し、必要な割合を入力します。 **25**.


1. すべてのセグメントを定義したら、を選択し **[!UICONTROL Generate all segments in the same transition]** てをクリックし **[!UICONTROL Confirm]**&#x200B;ます。

   ![](assets/send-time_opt_segment.png)

1. Drag and drop an **Email delivery** activity into your workflow and open it. 「 [電子メール配信](../../automating/using/email-delivery.md) 」の節を参照してください。
1. 電子メールダッシュボードの **[!UICONTROL Schedule]** セクションをクリックします。
1. 「**[!UICONTROL Messages to be sent automatically on the date specified below]**」を選択します。
1. この **[!UICONTROL Start sending from]** フィールドで、連絡先の日付を定義します。

   この例では、5月25日午前8時を選択します。

1. 送信時間の最適化ドロップダウンメニューで、を選択し **[!UICONTROL Send at a custom date defined by a formula]** 、 **[!UICONTROL Edit an expression]** ボタンをクリックします。

   ![](assets/send-time_opt_formula_expression.png)

1. に、各顧客のデータを計算する日付とセグメントコードを設定 **[!UICONTROL Expression editor]**&#x200B;します。

   関数のリストで、を選択し **[!UICONTROL AddHours]**&#x200B;ます。

   ![](assets/send-time_opt_formula_expression_addhours.png)

   利用可能なフィールドで、/ **[!UICONTROL Current delivery]** /を選択し **[!UICONTROL Delivery scheduling]** ま **[!UICONTROL Contact date]**&#x200B;す。

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   これにより、フィールドに指定された日時を取得でき **[!UICONTROL Start sending from]** ます。

   関数のリストで、を選択し **[!UICONTROL ToInteger]**&#x200B;ます。 使用可能なフィールドで、/を選択 **[!UICONTROL Additional data]** し **[!UICONTROL Segment code]**&#x200B;ます。

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   これにより、セグメントコードで指定した数値を取得できます。

   次の数式が必要です。

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 確認して式を保存します。 スケジュールを確認し、配信を保存して、ワークフローを実行します。

* 最初のセグメントは、連絡日（5月25日午前8時）にメッセージを受け取ります。
* 2つ目のセグメントは、2時間後（5月25日午前10時）にメッセージを受信します。
* 3つ目のセグメントは、6時間後（5月25日午後2時）にメッセージを受信します。
* 4番目のセグメントには、8時間後（5月25日午後4時）にメッセージが表示されます。

