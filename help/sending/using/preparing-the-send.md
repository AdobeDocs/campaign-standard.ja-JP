---
title: 送信の準備
description: 送信前に準備を定義する方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
TQID: https://experienceleague.adobe.com/ARRxgarwKQmsl21vcz-rJ6MzcLP6RDmMnsBJDVsH25c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 462
ht-degree: 12%

---

# 送信の準備{#preparing-the-send}

準備は、ターゲット母集団を計算し、ターゲットに含まれる各プロファイルに対してメッセージコンテンツを生成するステップに対応する。 準備が完了すると、メッセージをすぐに送信するか、[ スケジュールされた日時](../../sending/using/about-scheduling-messages.md)に送信する準備が整います。

1. 送信の準備を開始するには、アクションバーにある「**準備**」ボタンをクリックします。

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** ブロックには、準備の進捗状況が表示され、準備統計（ターゲット メッセージの数、送信するメッセージの数など）が表示されます。

   ターゲット母集団のサイズによっては、この操作に時間がかかる場合があります。

   ![](assets/preparing_delivery.png)

1. アクションバーにある「**停止**」ボタンを使用して、いつでも準備を停止できます。

   準備段階では、メッセージは送信されません。 そのため、何かに影響を与えるリスクなく、準備を開始または停止できます。

   ![](assets/preparing_delivery_6.png)

1. メッセージは、配信準備段階で自動的に保存されます。 準備手順の後にメッセージのスケジュールに変更を加える必要がある場合は、変更を考慮に入れるために、**[!UICONTROL Prepare]** ボタンをもう一度クリックする必要があります。 メッセージのスケジュール方法について詳しくは、この[ ページ ](../../sending/using/about-scheduling-messages.md)を参照してください。

   ![](assets/preparing_delivery_5.png)

1. 準備ログを表示するには、ブロックの右下にあるボタンをクリックします。

   ![](assets/preparing_delivery_4.png)

1. **[!UICONTROL Deployment]** ウィンドウが開き、エラーを修正してから準備を再開します。

   最後のログメッセージには、エラーメッセージとエラー件数が表示されます。 特定のアイコンは、発生したエラータイプを示します。黄色のアイコンは、重要でない処理エラーを示し、赤いアイコンは、配信の開始を妨げる重大なエラーを示します。

   ![](assets/preparing_delivery_3.png)

1. メッセージの送信を確認する前に、準備統計を確認してください。 送信するメッセージの数が設定に対応しない場合は、ターゲット母集団を編集し（メッセージ内のオーディエンスの選択[1}を参照）、準備を再起動します。](../../audiences/using/selecting-an-audience-in-a-message.md)

準備が完了すると、メッセージを送信する準備が整います。 詳しくは、[送信確認](../../sending/using/confirming-the-send.md)を参照してください。

**タイポロジルール**

Adobe Campaignには、メッセージの準備中に適用されるビルトインタイポロジルールのセットが付属しています。 メッセージが有効で、品質基準を満たしているかどうかを確認するために使用されます。 [ タイポロジ ](../../sending/using/about-typology-rules.md)を参照してください。 例えば、独自のタイポロジルールを定義できます。例えば、キャンペーンから過度に孤立したプロファイルを自動的に除外する、グローバルクロスチャネルの疲労ルールを設定できます。 [疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

**SMS メッセージチェック**

パーソナライゼーションフィールドまたは条件テキストをSMS メッセージのコンテンツに挿入した場合、これらの要因により、GSM エンコーディングで考慮されない文字が発生する可能性があります。 準備が実行されると、メッセージの長さが監視され、制限を超えると警告メッセージが表示されます。

詳しくは、[SMS エンコーディング、長さ、文字起こし](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)および[SMS メッセージのパーソナライズ ](../../channels/using/personalizing-sms-messages.md)の節を参照してください。
