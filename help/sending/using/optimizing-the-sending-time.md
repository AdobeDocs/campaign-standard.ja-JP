---
title: 送信時間の最適化
description: 送信時間を設定し、メッセージの開封率を改善する方法を説明します。
page-status-flag: 非活性化の
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: スケジュール・メッセージ
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 送信時間の最適化{#optimizing-the-sending-time}

メッセージの開封率を向上させるには、受信者1人あたりの送信時間を手動で定義します。 各プロファイルは、可能な限り、指定した日時にメッセージを受信します。

送信時間の定義は、配信レベルで行うことも、ワークフローを使用することもできます。

電子メールの場合、サーバーの読み込みと再試行の回数に応じて、各受信者に対してスケジュールされた日時にメッセージを送信するのに最善の方法が講じられます。

* 再試行は、インターネットプロバイダーと評判によって異なります。 最初の試行時にメッセージが受け入れられない場合があり、再試行がいくつか行われる場合があります。 詳しくは、電 [子メールチャネルパラメーターのリストを参照してくださ](../../administration/using/configuring-email-channel.md)い。
* 帯域幅が不十分なため、電子メールの受信に遅延が生じる場合があります。

送信ログで、各受信者にメッセージがいつ送信されたかを確 [認できます](../../sending/using/monitoring-a-delivery.md#sending-logs)。

次のいくつかのオプションを使用できます。

* **[!UICONTROL No optimization]**:メッセージはユーザーの時刻に送信されます。

   例えば、タイムゾーンがGMT+1で、フィールドに午前9:00を入力した場合、GMT+3タイムゾーンの受信者は、その受信者の現地時間の午前11:00時にメッセージを受信します。 **[!UICONTROL Start sending from]**

* **[!UICONTROL Send at the recipient's time zone]**:すべての受信者は、タイムゾーンを考慮したメッセージを受信します。

   例えば、フィールドに「9:00 AM」と入力した場合、GMT+3タイムゾーンの受信者は、その受信者の現地時間の午前9:00にメッセージを受信します。 **[!UICONTROL Start sending from]**

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**:各受信者は、指定した数式で設定された日時にメッセージを受信します。

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

