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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 12%

---

# 送信の準備{#preparing-the-send}

準備は、ターゲット母集団を計算し、ターゲットに含まれるプロファイルごとにメッセージコンテンツを生成する手順に対応しています。 準備が完了すると、メッセージは、すぐに送信するか、[&#x200B; スケジュールされた日時 &#x200B;](../../sending/using/about-scheduling-messages.md) に送信できる状態になります。

1. 送信の準備を開始するには、アクションバーにある「**準備**」ボタンをクリックします。

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** ブロックには準備の進行状況が表示され、次に準備の統計が表示されます。ターゲットメッセージの数、送信するメッセージの数などがあります。

   ターゲット母集団のサイズによっては、この操作に時間がかかる場合があります。

   ![](assets/preparing_delivery.png)

1. アクションバーの **停止** ボタンを使用して、いつでも準備を停止できます。

   準備段階では、メッセージは送信されません。そのため、何かに影響を与えるリスクなく、準備を開始または停止できます。

   ![](assets/preparing_delivery_6.png)

1. メッセージは、配信の準備段階で自動的に保存されます。 準備ステップの後にメッセージのスケジュールを変更する必要がある場合は、「**[!UICONTROL Prepare]**」ボタンを再度クリックして、変更を反映させる必要があります。 メッセージのスケジュール方法について詳しくは、この [&#x200B; ページ &#x200B;](../../sending/using/about-scheduling-messages.md) を参照してください。

   ![](assets/preparing_delivery_5.png)

1. 準備ログを表示するには、ブロックの右下にあるボタンをクリックします。

   ![](assets/preparing_delivery_4.png)

1. **[!UICONTROL Deployment]** ウィンドウが開きます。エラーを修正して、準備を再開します。

   最後のログメッセージには、エラーメッセージとエラー件数が表示されます。特定のアイコンには、発生したエラータイプが表示されます。黄色のアイコンは重大ではない処理エラーを示し、赤いアイコンは配信が開始されない重大なエラーを示します。

   ![](assets/preparing_delivery_3.png)

1. メッセージの送信を確認する前に、準備統計を確認します。 送信するメッセージの数が設定と一致しない場合は、ターゲット母集団を編集し（[&#x200B; メッセージ内のオーディエンスの選択 &#x200B;](../../audiences/using/selecting-an-audience-in-a-message.md) を参照）、準備を再開します。

準備が完了したら、メッセージを送信する準備が整います。 詳しくは、[&#x200B; 送信の確認 &#x200B;](../../sending/using/confirming-the-send.md) を参照してください。

**タイポロジルール**

Adobe Campaignには、メッセージの準備中に適用される一連の組み込みタイポロジルールが付属しています。 これらは、メッセージが有効で、品質基準を満たしているかどうかを確認するために使用されます。 [&#x200B; タイポロジ &#x200B;](../../sending/using/about-typology-rules.md) を参照してください。 独自のタイポロジルールを定義できます。例えば、過剰に配信を受けているプロファイルをキャンペーンから自動的に除外するグローバルなクロスチャネル疲労ルールを設定できます。 [疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

**SMS メッセージチェック**

SMS メッセージのコンテンツにパーソナライゼーションフィールドまたは条件付きテキストを挿入している場合、これらの要因により、GSM エンコーディングで考慮されない文字が発生する可能性があります。 準備が実行されると、メッセージの長さが監視され、制限を超えると警告メッセージが表示されます。

詳しくは、[SMS エンコーディング、長さと表記変換 &#x200B;](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) および [SMS メッセージのパーソナライズ &#x200B;](../../channels/using/personalizing-sms-messages.md) の節を参照してください。
