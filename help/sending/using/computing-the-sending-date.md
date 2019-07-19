---
title: 送信日の計算
seo-title: 送信日の計算
description: 送信日の計算
seo-description: 特定の日時にメッセージを送信する方法を確認します。
page-status-flag: 常にアクティブ化されていない
uuid: fbbb37a0-7257-4407- a4c9- f76bf04460d4
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 削除されたドキュメント
discoiquuid: 02a87cc6- c40c-44fe- bb4e- b68870a4859b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 28abc1e8aa31f3e0c7f09926f34a977d4c491fd8

---


# Computing the sending date{#computing-the-sending-date}

特定の日時に各受信者にメッセージを送信する数式を定義できます。

## Customizing date formula {#customizing-date-formula}

例えば、カーブアッププロセス中に送信時間の最適化を使用できます。

新しいプラットフォームを使用して電子メールを送信する場合、インターネットサービスプロバイダー（ISP）は認識されないIPアドレスに不審です。大量の電子メールが突然送信されると、ISPはそれらをスパムとしてマークします。

スパムとしてマークされないようにするには、様々な時間に大量の電子メールを配信して送信されるボリュームをプログレッシブに増やすことができます。これにより、開始段階をスムーズに開発し、無効なアドレスの全体的なレートを減らすことができます。

例えば、ターゲットオーディエンスをランダムにセグメント化して、5つのバッチで配信を送信できます。ターゲットオーディエンスの10%を、10:00AMでは6月1日に、オーディエンスの15%の2番目のバッチで2番目のバッチを送信します。

ワークフローを使用して、これをスケジュールできます。

![](assets/send-time_opt_workflow1.png)

1. マーケティングアクティビティリストにアクセスして、新しいワークフローを作成します。See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. **クエリー** アクティビティをワークフローにドラッグアンドドロップして開きます。[「クエリ](../../automating/using/query.md) 」セクションを参照してください。
1. Select an audience, for example all your Gold customers and click **[!UICONTROL Confirm]** to save the query.
1. **セグメント** アクティビティをワークフローにドラッグアンドドロップして開きます。[「セグメント化](../../automating/using/segmentation.md) 」セクションを参照してください。
1. 5つのセグメントを定義します。各セグメントの場合:

   * **[!UICONTROL Segment code]** フィールドに入力します。は、メッセージを送信するための目的の日時を手動で入力します。

      例えば、6月1日の最初のバッチを午前10:00AM+1に送信したいとします。Use the following format: **YYYY-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      To send the next batch the day after, enter **2017-06-02 10:00:00+01** for the second segment.

      残りのセグメントでは、次のように次のバッチを定義します。

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * **[!UICONTROL Limit the population of this segment]** このオプションを選択していることを確認してください。

      **[!UICONTROL Limitation]** タブで、 **[!UICONTROL Random sampling]** 各セグメントに対して目的の割合を選択して入力します。最初のバッチの場合は10、2番目のバッチの場合は15です。

      ![](assets/send-time_opt_segment_limitation.png)


1. Once all segments are defined, select **[!UICONTROL Generate all segments in the same transition]** and click **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. **電子メール配信** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。[「電子メール配信](../../automating/using/email-delivery.md) 」セクションを参照してください。
1. Click the **[!UICONTROL Schedule]** section in the email dashboard and select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. **[!UICONTROL Start sending from]** フィールドに連絡先日付を定義します。
1. From the send time optimization drop-down menu, choose **[!UICONTROL Send at a custom date defined by a formula]**.
1. Click the **[!UICONTROL Edit an expression]** button of the **[!UICONTROL Custom date formula]** field.

   ![](assets/send-time_opt_formula_define.png)

1. **[!UICONTROL ToDateTime]** 関数と **[!UICONTROL Segment code]** フィールドを使用して次の式を作成します。式を直接入力することもできますが、正しい構文とスペルを必ず使用してください。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   The **[!UICONTROL ToDateTime]** function transforms the segment code from a text string to a date and time value.

   式を確認して前の画面に戻ります。

   ![](assets/send-time_opt_formula_define_segment.png)

   **[!UICONTROL Schedule]** ウィンドウでは、カスタム日付数式は次のように表示されます。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. スケジュールを確認し、配信を保存してワークフローを実行します。

配信は、ターゲット設定されたすべての受信者に対して5日間分のプログレッシブに送信されます。

>[!NOTE]
>
>送信の確認時に、すべての日付が未来にあることを確認してください。そうしないと、送信が確定されるとすぐにメッセージが送信されます。

## Using an expression {#using-an-expression}

送信時間の最適化は、コールセンターを含むキャンペーンにも便利です。すべてのメッセージが同時に受信されないようにすることができます。これにより、組織は容量に応じて呼び出し数を処理できます。

例えば、プロモーションオファーを取得するために、顧客を誘い文句（CTA:コールセンター）に招待する電子メールを送信するとします。コールセンターが圧倒されるのを防ぐために、ターゲットオーディエンスをランダムにセグメント化して電子メールを4つのバッチで送信します。

ワークフローを使用して、これをスケジュールできます。

![](assets/send-time_opt_workflow2.png)

1. マーケティングアクティビティリストにアクセスして、新しいワークフローを作成します。See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. **クエリー** アクティビティをワークフローにドラッグアンドドロップして開きます。[「クエリ](../../automating/using/query.md) 」セクションを参照してください。
1. Select an audience, for example over 35 profiles and click **[!UICONTROL Confirm]** to save the query.
1. **セグメント** アクティビティをワークフローにドラッグアンドドロップして開きます。[「セグメント化](../../automating/using/segmentation.md) 」セクションを参照してください。
1. 4つのセグメントを定義します。各セグメントの場合:

   * 次のようにセグメントコードを定義します。

      * 8:00 AM - 10:00 AM: **0**. メッセージは、午前8:00（連絡日）のターゲット母集団の最初の四半期に送信されます。
      * 10:00 AM - 12:00 PM: **2**. メッセージは、10:00AM（連絡日+2時間）のターゲット母集団の2番目の四半期に送信されます。
      * 2:00 PM - 4:00 PM: **6**. 午後12:00~午後2時の間にコールセンターが閉じられると、2:00PM（連絡日+6時間）のターゲット母集団の3等分にメッセージが送信されます。
      * 4:00 PM - 6:00 PM: **8**. メッセージは、午後4時（連絡日+8時間）のターゲット母集団の最後の四半期に送信されます。
      >[!NOTE]
      >
      >連絡先日付は、ワークフローの後で電子メール配信アクティビティで定義されます。

   * **[!UICONTROL Limit the population of this segment]** このオプションを選択していることを確認してください。
   * **[!UICONTROL Limitation]** タブで、 **[!UICONTROL Random sampling]** 各セグメントに対して目的の割合を選択して入力します。 **25.**


1. Once all segments are defined, select **[!UICONTROL Generate all segments in the same transition]** and click **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. **電子メール配信** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。[「電子メール配信](../../automating/using/email-delivery.md) 」セクションを参照してください。
1. Click the **[!UICONTROL Schedule]** section in the email dashboard.
1. Select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. **[!UICONTROL Start sending from]** フィールドに連絡先日付を定義します。

   この例では、午前8時20分の午前8時を選択します。

1. From the send time optimization drop-down menu, choose **[!UICONTROL Send at a custom date defined by a formula]** and click the **[!UICONTROL Edit an expression]** button.

   ![](assets/send-time_opt_formula_expression.png)

1. In the **[!UICONTROL Expression editor]**, set the date and the segment codes to compute the data for each customer.

   In the list of functions, select **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   In the available fields, select **[!UICONTROL Current delivery]** &gt; **[!UICONTROL Delivery scheduling]** &gt; **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   This enables you to retrieve the date and time specified in the **[!UICONTROL Start sending from]** field.

   In the list of functions, select **[!UICONTROL ToInteger]**. In the available fields, select **[!UICONTROL Additional data]** &gt; **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   これにより、セグメントコードで指定した数値を取得できます。

   次の数式を取得する必要があります。

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 式を保存して、式を保存します。スケジュールを確認し、配信を保存してワークフローを実行します。

* 最初のセグメントは、連絡先日（午前8:00の午前8時25分）にメッセージを受け取ります。
* 2つ目のセグメントは、メッセージを2時間後（午前10時20分）に受け取ります。
* 3つ目のセグメントは、メッセージを6時間後（2:00PMで25日）受け取ります。
* 4つ目のセグメントは、メッセージを8時間後に受け取ります（5月25日午後4時）。

