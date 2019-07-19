---
title: 送信の準備
seo-title: 送信の準備
description: 送信の準備
seo-description: 送信前に準備を定義する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 1038ae2-164c-4579-9294- bdf2a4eb12d6
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 準備とテストのメッセージ
discoiquuid: 003abc83-7f07-471f- ab2f-1d352d22c26f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Preparing the send{#preparing-the-send}

準備は、ターゲット母集団を計算し、ターゲットに含まれる各プロファイルのメッセージコンテンツを生成する手順に対応しています。Once preparation is finished, the messages are ready to be sent, either immediately or at [the scheduled date and time](../../sending/using/about-scheduling-messages.md).

1. To start preparing the send, click the **Prepare** button located in the action bar.

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** ブロックには準備の進行状況が表示され、次に準備の統計が表示されます。ターゲットメッセージ数、送信するメッセージ数など

   ターゲット母集団のサイズによっては、この操作に時間がかかる場合があります。

   ![](assets/preparing_delivery.png)

1. Stop the preparation at any time using the **Stop** button, located in the action bar.

   準備段階では、メッセージは送信されません。したがって、影響を受けることなく、これを開始または停止できます。

   ![](assets/preparing_delivery_6.png)

1. 配信段階の準備中にメッセージが自動的に保存されます。If you need to make any changes to your message's schedule after the preparation step, you will need to make sure that you click the **[!UICONTROL Prepare]** button again for those changes to be taken into account. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. 準備ログを表示するには、ブロックの右下にあるボタンをクリックします。

   ![](assets/preparing_delivery_4.png)

1. **[!UICONTROL Deployment]** ウィンドウが開き、エラーが修正されたら、準備を再開します。

   最後のログメッセージには、エラーメッセージとエラーの数が表示されます。特定のアイコンに、検出されたエラータイプが表示されます。黄色のアイコンは、重大でない処理エラーを示し、赤のアイコンは配信が開始されないようにする重大なエラーを示します。

   ![](assets/preparing_delivery_3.png)

1. メッセージの送信を確認する前に、準備の統計を確認してください。If the number of messages to send does not correspond to your configuration, edit the targeted population (see [Selecting an audience in a message](../../audiences/using/selecting-an-audience-in-a-message.md)) and restart the preparation.

準備が完了すると、メッセージを送信できるようになります。For more on this, see [Confirming send](../../sending/using/confirming-the-send.md).

**タイポロジルール**

Adobe Campaignには、メッセージの準備中に適用される組み込みタイポロジルールのセットが付属しています。これらは、メッセージが有効であり、品質条件を満たすかどうかを確認するために使用されます。See [Typologies](../../administration/using/about-typology-rules.md). 例えば、独自のタイポロジルールを定義することで、グローバルなクロスチャネルの疲労ルールをキャンペーンから自動的に除外するグローバルなクロスチャネルルールを設定できます。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。

**SMSメッセージチェック**

パーソナライゼーションフィールドまたは条件テキストをSMSメッセージのコンテンツに挿入する場合、これらの要因によって、GSMエンコーディングによって考慮されない文字が生成されることがあります。準備が完了すると、メッセージの長さが監視され、制限を渡すと警告メッセージが表示されます。

For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) and [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) sections.
