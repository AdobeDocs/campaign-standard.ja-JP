---
title: 送信の準備
description: 送信前に準備を定義する方法を説明します。
page-status-flag: never-activated
uuid: 1038dae2-164c-4579-9294-bdf2a4eb12d6
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 003abc83-7f07-471f-ab2f-1d352d22c26f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# 送信の準備{#preparing-the-send}

準備は、ターゲット母集団を計算し、そのメッセージに含まれる各プロファイルに対してメッセージ内容を生成するターゲットに対応する。 準備が完了すると、メッセージは即時またはスケジュールされた日時に送信 [できる状態になります](../../sending/using/about-scheduling-messages.md)。

1. 送信の準備を開始するには、アクショ **ンバーの** 「準備」ボタンをクリックします。

   ![](assets/preparing_delivery_2.png)

1. ブロッ **[!UICONTROL Deployment]** クには準備の進行状況が表示され、次に準備の統計が表示されます。対象となるメッセージの数、送信するメッセージの数など

   ターゲット母集団のサイズによっては、この操作に時間がかかる場合があります。

   ![](assets/preparing_delivery.png)

1. アクションバーにある「停止」ボタン **を使用し** 、いつでも準備を停止できます。

   準備段階では、メッセージは送信されません。 したがって、何かに影響を与えることなく、開始や停止を行うことができます。

   ![](assets/preparing_delivery_6.png)

1. メッセージは、メッセージの準備段階で自動的に配信されます。 準備手順の後にメッセージのスケジュールに変更を加える必要がある場合は、その変更を考慮するために、ボタンを再度クリックする必要が **[!UICONTROL Prepare]** あります。 メッセージのスケジュール方法の詳細については、このページを参照して [ください](../../sending/using/about-scheduling-messages.md)。

   ![](assets/preparing_delivery_5.png)

1. 準備ログを表示するには、ブロックの右下にあるボタンをクリックします。

   ![](assets/preparing_delivery_4.png)

1. ウィン **[!UICONTROL Deployment]** ドウが開き、エラーを修正してから準備を再開します。

   最後のログメッセージには、エラーメッセージとエラー件数が表示されます。特定のアイコンは、発生したエラーの種類を示します。黄色のアイコンは重要でない処理エラーを示し、赤のアイコンは重要なエラーを示し、配信の起動を妨げます。

   ![](assets/preparing_delivery_3.png)

1. メッセージの送信を確認する前に、準備の統計を確認します。 送信するオーディエンスの数が設定に一致しない場合は、ターゲット母集団を編集し(メッセージ内のメッセージの選択を参照 [](../../audiences/using/selecting-an-audience-in-a-message.md))、準備を再開します。

準備が完了すると、メッセージを送信する準備が整います。 詳しくは、送信の確認を参照し [てください](../../sending/using/confirming-the-send.md)。

**タイポロジルール**

Adobe Campaignには、メッセージの準備中に適用される一連の組み込みタイポロジルールが付属しています。 メッセージが有効で、品質基準を満たしているかどうかを確認するために使用されます。 タイポロジ [を参照し](../../sending/using/about-typology-rules.md)。 独自のタイポロジルールを定義できます。例えば、訪問者から過剰呼び出しのプロファイルを自動的に除外する、グローバルなチャネル間疲労ルールを設定できます。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md)い。

**SMSメッセージの確認**

SMSメッセージの内容にパーソナライゼーションフィールドや条件テキストを挿入した場合、GSMエンコーディングで考慮されない文字が含まれる可能性があります。 準備が実行されると、メッセージの長さが監視され、制限を超えると警告メッセージが表示されます。

詳細は、「 [SMSのエンコード、長さ、文字変換](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 、および [SMSメッセージの個人](../../channels/using/personalizing-sms-messages.md) 化」を参照。
