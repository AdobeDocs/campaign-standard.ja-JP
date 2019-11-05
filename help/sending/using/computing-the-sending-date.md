---
title: 送信日の計算
description: 特定の日時にメッセージを送信する方法を確認します。
page-status-flag: 非活性化の
uuid: fbbb37a0-7257-4407-a4c9-f76bf04460d4
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: スケジュール・メッセージ
discoiquuid: 02a87cc6-c40c-44fe-bb4e-b68870a4859b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 送信日の計算{#computing-the-sending-date}

特定の日時に各受信者にメッセージを送信する数式を定義できます。

## 日付式のカスタマイズ {#customizing-date-formula}

例えば、ランプアッププロセス中に送信時間の最適化を使用できます。

新しいプラットフォームを使用して E メールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量の E メールが突然送信されると、ISP はそれらの E メールをスパムとしてマークします。

スパムとしてマークされないように、大量の電子メールを異なる時間に配信することで、送信する電子メールの量を徐々に増やすことができます。 この方法により、スタートアップフェーズをスムーズに進め、無効なアドレスが全体に占める割合を減らすことができます。

例えば、ターゲットオーディエンスをランダムにセグメント化して、配信を5つのバッチに分けることができます。 6月1日の午前10:00にターゲットオーディエンスの10%を表す最初のバッチを送信し、24時間後にオーディエンスの15%を表す2番目のバッチを送信します。

ワークフローを使用してスケジュールを設定できます。

![](assets/send-time_opt_workflow1.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 詳しくは、 [ワークフローの作成を参照してください](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. Drag and drop a **Query** activity into your workflow and open it. 「クエリー」を参 [照してください](../../automating/using/query.md) 。
1. 例えば、すべてのゴールド顧客のオーディエンスを選択し、をクリックし **[!UICONTROL Confirm]** てクエリを保存します。
1. Drag and drop a **Segmentation** activity into your workflow and open it. 「分類」の節を参 [照してください](../../automating/using/segmentation.md) 。
1. 5つのセグメントを定義します。 各セグメントに対して、次の操作を行います。

   * フィールドに入力 **[!UICONTROL Segment code]** します。メッセージを送信する日時を手動で入力します。

      例えば、6月1日の午前10:00 GMT+1に最初のバッチを送信するとします。 次の形式を使用します。 **YYYY-MM-DD hh:mm:ss+tz**。

      ![](assets/send-time_opt_segment_configuration.png)

      次のバッチを次の日の翌日に送信するには、2番目のセグメントに **2017-06-02 10:00:00+01** と入力します。

      残りのセグメントに対して、次のバッチを次のように定義します。

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * 必ずこのオプションを選択してく **[!UICONTROL Limit the population of this segment]** ださい。

      タブで、 **[!UICONTROL Limitation]** 各セグメン **[!UICONTROL Random sampling]** トの必要な割合を選択して入力します。最初のバッチは10、2番目のバッチは15、のように続きます。

      ![](assets/send-time_opt_segment_limitation.png)


1. すべてのセグメントを定義したら、を選択し **[!UICONTROL Generate all segments in the same transition]** てをクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   ![](assets/send-time_opt_segment_dates.png)

1. 電子メール配信アクティビティ **をワークフロー** にドラッグ&amp;ドロップして開きます。 「電子メール配信 [」の節を参照](../../automating/using/email-delivery.md) 。
1. 電子メールダッ **[!UICONTROL Schedule]** シュボードのセクションをクリックし、を選択しま **[!UICONTROL Messages to be sent automatically on the date specified below]**&#x200B;す。
1. このフィールド **[!UICONTROL Start sending from]** で、連絡日を定義します。
1. 送信時間の最適化ドロップダウンメニューで、を選択しま **[!UICONTROL Send at a custom date defined by a formula]**&#x200B;す。
1. フィールドのボ **[!UICONTROL Edit an expression]** タンをクリック **[!UICONTROL Custom date formula]** します。

   ![](assets/send-time_opt_formula_define.png)

1. 関数とフィールドを使用して、次 **[!UICONTROL ToDateTime]** の式を作成し **[!UICONTROL Segment code]** ます。 また、式を直接入力することもできますが、正しい構文とスペルを使用するようにしてください。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   この関 **[!UICONTROL ToDateTime]** 数は、セグメントコードをテキスト文字列から日時値に変換します。

   式が前の画面に戻ることを確認します。

   ![](assets/send-time_opt_formula_define_segment.png)

   このウィン **[!UICONTROL Schedule]** ドウには、カスタム日付式が次のように表示されます。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. スケジュールを確認し、配信を保存してワークフローを実行します。

配信は、対象となるすべての受信者に対して5日間プログレッシブに送信されます。

>[!NOTE]
>
>送信を確認する際は、すべての日付が未来の日付であることを確認します。 それ以外の場合は、送信が確認され次第、メッセージが送信されます。

## 式の使用 {#using-an-expression}

送信時間の最適化は、コールセンターが関与するキャンペーンにも役立ちます。 すべてのメッセージを同時に受信しないようにすることができます。 これにより、組織はその容量に従って呼び出し数を処理できます。

例えば、プロモーションオファーを受け取るために、顧客がコールセンターに連絡するように招待する電子メールを送信するとします。 コールセンターが圧倒されるのを防ぐために、ターゲットとなる閲覧者をランダムにセグメント化し、電子メールを4つのバッチに分けて送信することにします。

ワークフローを使用してスケジュールを設定できます。

![](assets/send-time_opt_workflow2.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 詳しくは、 [ワークフローの作成を参照してください](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. Drag and drop a **Query** activity into your workflow and open it. 「クエリー」を参 [照してください](../../automating/using/query.md) 。
1. 例えば35件以上のプロファイルを含むオーディエンスを選択し、をクリックし **[!UICONTROL Confirm]** てクエリを保存します。
1. Drag and drop a **Segmentation** activity into your workflow and open it. 「分類」の節を参 [照してください](../../automating/using/segmentation.md) 。
1. 4つのセグメントを定義します。 各セグメントに対して、次の操作を行います。

   * 次のようにセグメントコードを定義します。

      * 8:00 AM ～ 10:00 AM: **0**. メッセージは、ターゲット母集団の第1四半期の午前8時（連絡日）に送信されます。
      * 10:00 AM - 12:00 PM: **2**. メッセージは、ターゲット母集団の第2四半期の午前10:00（連絡日+ 2時間）に送信されます。
      * 2:00 PM ～ 4:00 PM: **6**. コールセンターが午後12時から午後2時の間に閉鎖されると、メッセージはターゲット訪問者の第3四半期の午後2時（連絡日+ 6時間）に送信されます。
      * 4:00 PM ～ 6:00 PM: **8**. メッセージは、ターゲット母集団の前四半期の午後4時（連絡日+ 8時間）に送信されます。
      >[!NOTE]
      >
      >連絡日は、ワークフローの後半の電子メール配信アクティビティで定義されます。

   * 必ずこのオプションを選択してく **[!UICONTROL Limit the population of this segment]** ださい。
   * タブで、 **[!UICONTROL Limitation]** 各セグメン **[!UICONTROL Random sampling]** トの必要な割合を選択して入力します。 **25**.


1. すべてのセグメントを定義したら、を選択し **[!UICONTROL Generate all segments in the same transition]** てをクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   ![](assets/send-time_opt_segment.png)

1. 電子メール配信アクティビティ **をワークフロー** にドラッグ&amp;ドロップして開きます。 「電子メール配信 [」の節を参照](../../automating/using/email-delivery.md) 。
1. 電子メールダッシ **[!UICONTROL Schedule]** ュボードのセクションをクリックします。
1. Select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. このフィールド **[!UICONTROL Start sending from]** で、連絡日を定義します。

   この例では、5月25日午前8:00を選択します。

1. 送信時間の最適化ドロップダウンメニューで、を選択し、ボ **[!UICONTROL Send at a custom date defined by a formula]** タンをクリック **[!UICONTROL Edit an expression]** します。

   ![](assets/send-time_opt_formula_expression.png)

1. で、日 **[!UICONTROL Expression editor]**&#x200B;付とセグメントコードを設定し、各顧客のデータを計算します。

   関数のリストで、を選択します **[!UICONTROL AddHours]**。

   ![](assets/send-time_opt_formula_expression_addhours.png)

   使用可能なフィールドで、// **[!UICONTROL Current delivery]** を選 **[!UICONTROL Delivery scheduling]** 択しま **[!UICONTROL Contact date]**&#x200B;す。

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   これにより、フィールドに指定された日時を取得でき **[!UICONTROL Start sending from]** ます。

   関数のリストで、を選択します **[!UICONTROL ToInteger]**。 使用可能なフィールドで、/を選 **[!UICONTROL Additional data]** 択しま **[!UICONTROL Segment code]**&#x200B;す。

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   これにより、セグメントコードで指定した番号を取得できます。

   次の数式が必要です。

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 確認して式を保存します。 スケジュールを確認し、配信を保存してワークフローを実行します。

* 最初のセグメントは、連絡日（5月25日午前8時）にメッセージを受信します。
* 2番目のセグメントは、2時間後（5月25日午前10時）にメッセージを受信します。
* 3番目のセグメントは、6時間後（5月25日午後2時）にメッセージを受信します。
* 4番目のセグメントは、8時間後（5月25日午後4時）にメッセージを受信します。

