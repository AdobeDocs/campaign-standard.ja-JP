---
title: 送信日の計算
description: 特定の日時にメッセージを送信する方法を確認する。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 7%

---

# 送信日の計算{#computing-the-sending-date}

特定の日時に各受信者にメッセージを送信する数式を定義できます。

## 日付式のカスタマイズ {#customizing-date-formula}

例えば、ランプアッププロセス中に送信時間の最適化を使用できます。

新しいプラットフォームを使用してメールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量のメールが突然送信されると、ISP はそれらのメールをスパムとしてマークします。

スパムと見なされないようにするには、大量のメールを別々の時間に配信することで、送信量を徐々に増やすことができます。 この方法により、スタートアップフェーズをスムーズに進め、無効なアドレスが全体に占める割合を減らすことができます。

例えば、ターゲットオーディエンスをランダムにセグメント化して、5 回のバッチで配信を送信できます。 6 月 1 日の午前 10:00 にターゲットオーディエンスの 10% を表す最初のバッチを送信し、24 時間後にオーディエンスの 15% を含む 2 番目のバッチを送信します。

ワークフローを使用してスケジュールできます。

![](assets/send-time_opt_workflow1.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。
1. **クエリ** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [ クエリ ](../../automating/using/query.md) の節を参照してください。
1. オーディエンス（例：すべての Gold 顧客）を選択し、「**[!UICONTROL Confirm]**」をクリックしてクエリを保存します。
1. **セグメント化** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [ セグメント化 ](../../automating/using/segmentation.md) の節を参照してください。
1. 5 つのセグメントを定義します。 各セグメントに対して：

   * **[!UICONTROL Segment code]** フィールドに入力します。メッセージを送信する日時を手動で入力します。

     例えば、6 月 1 日の午前 10:00 GMT+1 に最初のバッチを送信するとします。 **`YYYY-MM-DD hh:mm:ss+tz`** の形式を使用します。

     ![](assets/send-time_opt_segment_configuration.png)

     翌日に次のバッチを送信するには、2 番目のセグメントに **2017-06-02 10:00:00+01** と入力します。

     残りのセグメントに対して、次のバッチを次のように定義します。

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**

   * 必ず「**[!UICONTROL Limit the population of this segment]**」オプションを選択してください。

     「**[!UICONTROL Limitation]**」タブで「**[!UICONTROL Random sampling]**」を選択し、各セグメントに必要なパーセンテージを入力します。最初のバッチは 10、2 番目のバッチは 15 と続きます。

     ![](assets/send-time_opt_segment_limitation.png)

1. すべてのセグメントを定義したら、「**[!UICONTROL Generate all segments in the same transition]**」を選択し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/send-time_opt_segment_dates.png)

1. **メール配信** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [ メール配信 ](../../automating/using/email-delivery.md) の節を参照してください。
1. メールダッシュボードで「**[!UICONTROL Schedule]**」セクションをクリックし、「**[!UICONTROL Messages to be sent automatically on the date specified below]**」を選択します。
1. 「**[!UICONTROL Start sending from]**」フィールドで、連絡日を定義します。
1. 送信時間の最適化ドロップダウンメニューから、「**[!UICONTROL Send at a custom date defined by a formula]**」を選択します。
1. **[!UICONTROL Custom date formula]** フィールドの「**[!UICONTROL Edit an expression]**」ボタンをクリックします。

   ![](assets/send-time_opt_formula_define.png)

1. **[!UICONTROL ToDateTime]** 関数と **[!UICONTROL Segment code]** フィールドを使用して、次の式を作成します。 式に直接入力することもできますが、正しい構文とスペルを使用してください。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   **[!UICONTROL ToDateTime]** 関数は、セグメントコードをテキスト文字列から日時値に変換します。

   前の画面に戻るには、式を確認します。

   ![](assets/send-time_opt_formula_define_segment.png)

   **[!UICONTROL Schedule]** ウィンドウに、カスタムの日付式が次のように表示されます。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. スケジュールを確定し、配信を保存してワークフローを実行します。

配信は、5 日間ですべてのターゲット受信者に段階的に送信されます。

>[!NOTE]
>
>送信を確認する際は、すべての日付が未来であることを確認します。 それ以外の場合は、送信が確認されしだいメッセージが送信されます。

## 式の使用 {#using-an-expression}

送信時間の最適化は、コールセンターを使用するキャンペーンの場合にも便利です。 すべてのメッセージが同時に受信されるわけではありません。 これにより、組織は処理能力に応じて呼び出し数を処理できます。

例えば、プロモーションのオファーを受けるために、コールセンターに連絡するよう顧客に招待するメールを送信するとします。 コールセンターに圧倒されないようにするために、ターゲットオーディエンスをランダムにセグメント化して、メールを 4 回のバッチで送信することにしました。

ワークフローを使用してスケジュールできます。

![](assets/send-time_opt_workflow2.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。
1. **クエリ** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [ クエリ ](../../automating/using/query.md) の節を参照してください。
1. オーディエンス（例：35 を超えるプロファイル）を選択し、「**[!UICONTROL Confirm]**」をクリックしてクエリを保存します。
1. **セグメント化** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [ セグメント化 ](../../automating/using/segmentation.md) の節を参照してください。
1. 4 つのセグメントを定義します。 各セグメントに対して：

   * セグメントコードを次のように定義します。

      * 午前 8:00～午前 10:00:**0**。 メッセージは、ターゲット母集団の第 1 四半期に午前 8:00 （コンタクト日）に送信されます。
      * 午前 10:00～午後 12:00:**2**。 メッセージは、ターゲット母集団の第 2 四半期に午前 10:00 （コンタクト日+ 2 時間）に送信されます。
      * 午後 2:00～午後 4:00:**6**。 コールセンターが午後 12:00～午後 2:00 に閉鎖されると、メッセージはターゲット母集団の第 3 四半期の午後 2:00 （連絡日+ 6 時間）に送信されます。
      * 午後 4:00～午後 6:00:**8**。 メッセージは、ターゲット母集団の最終四半期の午後 4:00 （コンタクト日+ 8 時間）に送信されます。

     >[!NOTE]
     >
     >連絡日は、ワークフローの後半のメール配信アクティビティで定義します。

   * 必ず「**[!UICONTROL Limit the population of this segment]**」オプションを選択してください。
   * 「**[!UICONTROL Limitation]**」タブで「**[!UICONTROL Random sampling]**」を選択し、各セグメントに任意の割合を入力します。**25**。

1. すべてのセグメントを定義したら、「**[!UICONTROL Generate all segments in the same transition]**」を選択し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/send-time_opt_segment.png)

1. **メール配信** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [ メール配信 ](../../automating/using/email-delivery.md) の節を参照してください。
1. メールダッシュボードで「**[!UICONTROL Schedule]**」セクションをクリックします。
1. 「**[!UICONTROL Messages to be sent automatically on the date specified below]**」を選択します。
1. 「**[!UICONTROL Start sending from]**」フィールドで、連絡日を定義します。

   この例では、5 月 25 日午前 8 時を選択します。

1. 送信時間の最適化ドロップダウンメニューから「**[!UICONTROL Send at a custom date defined by a formula]**」を選択し、「**[!UICONTROL Edit an expression]**」ボタンをクリックします。

   ![](assets/send-time_opt_formula_expression.png)

1. **[!UICONTROL Expression editor]** で、日付とセグメントコードを設定して、各顧客のデータを計算します。

   関数のリストで、「**[!UICONTROL AddHours]**」を選択します。

   ![](assets/send-time_opt_formula_expression_addhours.png)

   使用可能なフィールドで、**[!UICONTROL Current delivery]**/**[!UICONTROL Delivery scheduling]**/**[!UICONTROL Contact date]** を選択します。

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   これにより、**[!UICONTROL Start sending from]** フィールドで指定された日時を取得できます。

   関数のリストで、「**[!UICONTROL ToInteger]**」を選択します。 使用可能なフィールドで、**[!UICONTROL Additional data]**/**[!UICONTROL Segment code]** を選択します。

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   これにより、セグメントコードで指定した数値を取得できます。

   次の式が得られます。

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 確認して式を保存します。 スケジュールを確定し、配信を保存してワークフローを実行します。

* 最初のセグメントは、連絡日（5 月 25 日午前 8 時）にメッセージを受信します。
* 2 番目のセグメントには、2 時間後（5 月 25 日午前 10:00）にメッセージが届きます。
* 3 番目のセグメントには、6 時間後（5 月 25 日午後 2 時）にメッセージが届きます。
* 4 番目のセグメントは、8 時間後（5 月 25 日午後 4:00）にメッセージを受信します。
