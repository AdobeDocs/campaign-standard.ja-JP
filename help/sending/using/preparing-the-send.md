---
title: 送信の準備
description: 送信前の準備を定義する方法を説明します。
page-status-flag: 非活性化の
uuid: 1038dae2-164c-4579-9294-bdf2a4eb12d6
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: 準備とテストのメッセージ
discoiquuid: 003abc83-7f07-471f-ab2f-1d352d22c26f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 送信の準備{#preparing-the-send}

準備は、ターゲット母集団を計算し、ターゲットに含まれる各プロファイルに対してメッセージ内容を生成するステップに対応する。 準備が完了すると、メッセージは即座に、またはスケジュールされた日時に、送 [信する準備が整います](../../sending/using/about-scheduling-messages.md)。

1. 送信の準備を開始するには、アクションバ **ーにある** 「準備」ボタンをクリックします。

   ![](assets/preparing_delivery_2.png)

1. ブロッ **[!UICONTROL Deployment]** クには準備の進行状況が表示され、次に準備の統計が表示されます。対象となるメッセージの数、送信するメッセージの数など

   ターゲット母集団のサイズによっては、この操作に時間がかかる場合があります。

   ![](assets/preparing_delivery.png)

1. アクションバーにある「停止」ボタン **を使用し** 、いつでも準備を停止できます。

   準備段階では、メッセージは送信されません。 したがって、何かに影響を与えることなく、この機能を開始または停止できます。

   ![](assets/preparing_delivery_6.png)

1. メッセージは、配信ステージの準備中に自動的に保存されます。 準備手順の後にメッセージのスケジュールに変更を加える必要がある場合は、その変更を考慮するために、ボタンを再度クリックする必要があ **[!UICONTROL Prepare]** ります。 メッセージのスケジュール方法の詳細については、このページを参照して [ください](../../sending/using/about-scheduling-messages.md)。

   ![](assets/preparing_delivery_5.png)

1. 準備ログを表示するには、ブロックの右下にあるボタンをクリックします。

   ![](assets/preparing_delivery_4.png)

1. ウィン **[!UICONTROL Deployment]** ドウが開き、エラーを修正してから準備を再開します。

   最後のログメッセージには、エラーメッセージとエラー件数が表示されます。特定のアイコンは、発生したエラーのタイプを示します。黄色のアイコンは重要でない処理エラーを示し、赤のアイコンは配信を開始できない重大なエラーを示します。

   ![](assets/preparing_delivery_3.png)

1. メッセージの送信を確認する前に、準備の統計を確認します。 送信するメッセージの数が設定に一致しない場合は、ターゲットの訪問者を編集し(「メッセージ内のオーディエンスの選択 [](../../audiences/using/selecting-an-audience-in-a-message.md)」を参照)、準備を再開します。

準備が完了すると、メッセージを送信する準備が整います。 詳しくは、送信の確認を参照し [てください](../../sending/using/confirming-the-send.md)。

**タイポロジルール**

Adobe Campaignには、メッセージの準備中に適用される組み込みのタイポロジルールのセットが付属しています。 メッセージが有効で、品質基準を満たしているかどうかを確認するために使用されます。 タイポロジ [を参照してくださ](../../administration/using/about-typology-rules.md)い。 独自のタイポロジルールを定義できます。例えば、キャンペーンから過剰ビルクエイティングプロファイルを自動的に除外するグローバルなチャネル間疲労ルールを設定できます。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

**SMSメッセージチェック**

SMSメッセージのコンテンツにパーソナライゼーションフィールドまたは条件テキストを挿入した場合、これらの要因によって、GSMエンコーディングで考慮されない文字が生じる可能性があります。 準備が実行されると、メッセージの長さが監視され、制限を超えると警告メッセージが表示されます。

詳細については、「 [SMSのエンコード、長さ、読み取り、およびSMSメッセージのパーソナライズ](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 」の項 [を参照してください](../../channels/using/personalizing-sms-messages.md) 。
