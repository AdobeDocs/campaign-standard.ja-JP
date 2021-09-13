---
title: 送信日の計算
description: 特定の日時にメッセージを送信する方法を確認します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 7%

---

# 送信日の計算{#computing-the-sending-date}

各受信者に特定の日時にメッセージを送信する数式を定義できます。

## 日付式のカスタマイズ {#customizing-date-formula}

例えば、ランプアッププロセス中に送信時間の最適化を使用できます。

新しいプラットフォームを使用して E メールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量の E メールが突然送信されると、ISP はそれらの E メールをスパムとしてマークします。

スパムとしてマークされないように、異なる時間に大量のEメールを配信することで、送信される量を徐々に増やすことができます。 この方法により、スタートアップフェーズをスムーズに進め、無効なアドレスが全体に占める割合を減らすことができます。

例えば、ターゲットオーディエンスをランダムにセグメント化して、配信を5つのバッチで送信できます。 6月1日の午前10:00にターゲットオーディエンスの10%を表す最初のバッチを送信し、2番目のバッチを午前24時間後に、15%のオーディエンスを表すバッチを送信するといった具合に実行します。

ワークフローを使用して、スケジュールを設定できます。

![](assets/send-time_opt_workflow1.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。
1. **クエリ**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [クエリ](../../automating/using/query.md)の節を参照してください。
1. オーディエンス（例えば、すべてのゴールド顧客）を選択し、**[!UICONTROL Confirm]**&#x200B;をクリックしてクエリを保存します。
1. **Segmentation**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [セグメント化](../../automating/using/segmentation.md)の節を参照してください。
1. 5つのセグメントを定義します。 セグメントごとに、

   * **[!UICONTROL Segment code]**&#x200B;フィールドに入力します。メッセージを送信する日時を手動で入力します。

      例えば、6月1日の午前10時(GMT+1)に最初のバッチを送信するとします。 次の形式を使用します。**YYYY-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      翌日に次のバッチを送信するには、2番目のセグメントに&#x200B;**2017-06-02 10:00:00+01**&#x200B;と入力します。

      残りのセグメントに対して、次のバッチを次のように定義します。

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * 必ず&#x200B;**[!UICONTROL Limit the population of this segment]**&#x200B;オプションを選択してください。

      「**[!UICONTROL Limitation]**」タブで「**[!UICONTROL Random sampling]**」を選択し、各セグメントに対して目的の割合を入力します。1回目のバッチは10、2回目のバッチは15、などです。

      ![](assets/send-time_opt_segment_limitation.png)


1. すべてのセグメントを定義したら、**[!UICONTROL Generate all segments in the same transition]**&#x200B;を選択し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/send-time_opt_segment_dates.png)

1. **Eメール配信**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [Eメール配信](../../automating/using/email-delivery.md)の節を参照してください。
1. Eメールダッシュボードの「**[!UICONTROL Schedule]**」セクションをクリックし、「**[!UICONTROL Messages to be sent automatically on the date specified below]**」を選択します。
1. 「**[!UICONTROL Start sending from]**」フィールドで、コンタクト日を定義します。
1. 送信時間の最適化ドロップダウンメニューから、**[!UICONTROL Send at a custom date defined by a formula]**&#x200B;を選択します。
1. **[!UICONTROL Custom date formula]**&#x200B;フィールドの&#x200B;**[!UICONTROL Edit an expression]**&#x200B;ボタンをクリックします。

   ![](assets/send-time_opt_formula_define.png)

1. **[!UICONTROL ToDateTime]**&#x200B;関数と&#x200B;**[!UICONTROL Segment code]**&#x200B;フィールドを使用して、次の式を作成します。 また、式を直接入力することもできますが、正しい構文とスペルを使用するようにしてください。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   **[!UICONTROL ToDateTime]**&#x200B;関数は、セグメントコードをテキスト文字列から日時値に変換します。

   前の画面に戻る式を確認します。

   ![](assets/send-time_opt_formula_define_segment.png)

   **[!UICONTROL Schedule]**&#x200B;ウィンドウに、カスタムの日付式が次のように表示されます。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. スケジュールを確認し、配信を保存して、ワークフローを実行します。

配信は、5日間ですべてのターゲット受信者にプログレッシブに送信されます。

>[!NOTE]
>
>送信を確認する際は、すべての日付が将来の日付であることを確認します。 それ以外の場合は、送信が確認されるとすぐにメッセージが送信されます。

## 式の使用 {#using-an-expression}

送信時間の最適化は、コールセンターが関与するキャンペーンにも役立ちます。 すべてのメッセージが同時に受信されないようにすることができます。 これにより、組織は処理能力に従って呼び出し数を処理できます。

例えば、プロモーションオファーを受け取るために、顧客をコールセンターに連絡するよう招待するEメールを送信する場合などです。 コールセンターを圧倒するのを避けるために、ターゲットオーディエンスをランダムにセグメント化して、Eメールを4つのバッチで送信することにします。

ワークフローを使用して、スケジュールを設定できます。

![](assets/send-time_opt_workflow2.png)

1. マーケティングアクティビティリストにアクセスし、新しいワークフローを作成します。 [ワークフローの作成](../../automating/using/building-a-workflow.md#creating-a-workflow)を参照してください。
1. **クエリ**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [クエリ](../../automating/using/query.md)の節を参照してください。
1. 例えば35を超えるプロファイルのオーディエンスを選択し、「**[!UICONTROL Confirm]**」をクリックしてクエリを保存します。
1. **Segmentation**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [セグメント化](../../automating/using/segmentation.md)の節を参照してください。
1. 4つのセグメントを定義します。 セグメントごとに、

   * 次のようにセグメントコードを定義します。

      * 午前8時～午前10時：**0**&#x200B;です。 メッセージは、ターゲット母集団の第1四半期の午前8時（コンタクト日）に送信されます。
      * 午前10時～午後12時：**2**&#x200B;です。 メッセージは、ターゲット母集団の第2四半期の午前10時（コンタクト日+ 2時間）に送信されます。
      * 午後2時～午後4時：**6**&#x200B;です。 コールセンターが午後12:00から午後2:00に閉じられると、メッセージはターゲット母集団の第3四半期の午後2:00（コンタクト日+ 6時間）に送信されます。
      * 午後4時～午後6時：**8**&#x200B;です。 メッセージは、ターゲット母集団の最後の四半期の午後4時（コンタクト日+ 8時間）に送信されます。

      >[!NOTE]
      >
      >コンタクト日は、後でワークフローの「 Eメール配信」アクティビティで定義します。

   * 必ず&#x200B;**[!UICONTROL Limit the population of this segment]**&#x200B;オプションを選択してください。
   * 「**[!UICONTROL Limitation]**」タブで「**[!UICONTROL Random sampling]**」を選択し、各セグメントに対して目的の割合を入力します。**25**.


1. すべてのセグメントを定義したら、**[!UICONTROL Generate all segments in the same transition]**&#x200B;を選択し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/send-time_opt_segment.png)

1. **Eメール配信**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。 [Eメール配信](../../automating/using/email-delivery.md)の節を参照してください。
1. Eメールダッシュボードの「 **[!UICONTROL Schedule]** 」セクションをクリックします。
1. 「**[!UICONTROL Messages to be sent automatically on the date specified below]**」を選択します。
1. 「**[!UICONTROL Start sending from]**」フィールドで、コンタクト日を定義します。

   この例では、5月25日午前8時に「 」を選択します。

1. 送信時間の最適化ドロップダウンメニューから&#x200B;**[!UICONTROL Send at a custom date defined by a formula]**&#x200B;を選択し、「**[!UICONTROL Edit an expression]**」ボタンをクリックします。

   ![](assets/send-time_opt_formula_expression.png)

1. **[!UICONTROL Expression editor]**&#x200B;で、日付とセグメントコードを設定して、各顧客のデータを計算します。

   関数のリストで、「**[!UICONTROL AddHours]**」を選択します。

   ![](assets/send-time_opt_formula_expression_addhours.png)

   使用可能なフィールドで、**[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**&#x200B;を選択します。

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   これにより、**[!UICONTROL Start sending from]**&#x200B;フィールドで指定された日時を取得できます。

   関数のリストで、「**[!UICONTROL ToInteger]**」を選択します。 使用可能なフィールドで、**[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**&#x200B;を選択します。

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   これにより、セグメントコードで指定した番号を取得できます。

   次の数式が得られます。

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 確認して式を保存します。 スケジュールを確認し、配信を保存して、ワークフローを実行します。

* 最初のセグメントは、コンタクト日（5月25日午前8時）にメッセージを受信します。
* 2番目のセグメントは、2時間後（5月25日午前10時）にメッセージを受信します。
* 3番目のセグメントは、6時間後（5月25日午後2時）にメッセージを受信します。
* 4番目のセグメントは、8時間後（5月25日午後4時）にメッセージを受信します。
