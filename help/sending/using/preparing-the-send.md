---
solution: Campaign Standard
product: campaign
title: 送信の準備
description: 送信前の準備を定義する方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 5%

---


# 送信の準備{#preparing-the-send}

作成は、ターゲット母集団を計算し、ターゲットに含まれる各プロファイルに対してメッセージ内容を生成するステップに対応する。 準備が完了すると、メッセージは即座に送信するか、スケジュールされた日時 [に送信する準備が整います](../../sending/using/about-scheduling-messages.md)。

1. 送信の準備を開始するには、アクションバーにある **「準備** 」ボタンをクリックします。

   ![](assets/preparing_delivery_2.png)

1. ブロックには、準備の進行状況が表示され、次に準備の統計が表示されます。 **[!UICONTROL Deployment]** ターゲットメッセージ数、送信するメッセージ数など

   ターゲット母集団のサイズによっては、この操作に時間がかかる場合があります。

   ![](assets/preparing_delivery.png)

1. アクションバーにある **停止** ボタンを使用して、準備をいつでも停止できます。

   準備段階では、メッセージは送信されません。 したがって、何も影響を与えるリスクを伴うことなく、開始や停止が可能です。

   ![](assets/preparing_delivery_6.png)

1. メッセージは、配信の準備段階で自動的に保存されます。 準備手順の後にメッセージのスケジュールに変更を加える必要がある場合は、その変更を考慮するために、 **[!UICONTROL Prepare]** ボタンを再度クリックする必要があります。 For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. 準備ログを表示するには、ブロックの右下にあるボタンをクリックします。

   ![](assets/preparing_delivery_4.png)

1. ウィンドウが開き、エラーを修正してから準備を再開します。 **[!UICONTROL Deployment]**

   最後のログメッセージには、エラーメッセージとエラー件数が表示されます。特定のアイコンに、発生したエラーの種類が表示されます。黄色のアイコンは重大でない処理エラーを示し、赤のアイコンは重大なエラーを示します。このエラーは、配信の起動を妨げます。

   ![](assets/preparing_delivery_3.png)

1. メッセージの送信を確認する前に、準備の統計を確認します。 送信するメッセージの数が設定に一致しない場合は、ターゲットの母集団を編集し(メッセージ内のオーディエンスの [選択を参照](../../audiences/using/selecting-an-audience-in-a-message.md))、準備を再開します。

準備が完了すると、メッセージを送信する準備が整います。 詳しくは、「送信の [確認](../../sending/using/confirming-the-send.md)」を参照してください。

**タイポロジルール**

Adobe Campaignには、メッセージの準備中に適用される組み込みタイポロジルールのセットが付属しています。 メッセージが有効で、品質の基準を満たしているかどうかを確認するために使用されます。 タイ [ポロジを参照してください](../../sending/using/about-typology-rules.md)。 独自のタイポロジルールを定義できます。例えば、グローバルなチャネル間の疲労ルールを設定して、訪問者から過剰ビルサイティングプロファイルを自動的に除外することができます。 [疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

**SMSメッセージの確認**

SMSメッセージのコンテンツにパーソナライゼーションフィールドや条件付きテキストを挿入した場合、GSMエンコーディングで考慮されない文字が含まれる可能性があります。 準備が実行されると、メッセージの長さが監視され、制限を超えると警告メッセージが表示されます。

詳細については、 [SMSのエンコード、長さ、変換](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 、 [SMSメッセージのパーソナライズの各セクションを参照してください](../../channels/using/personalizing-sms-messages.md) 。
