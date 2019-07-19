---
title: 送信時間の最適化
seo-title: 送信時間の最適化
description: 送信時間の最適化
seo-description: 送信時間を設定し、メッセージのオープンレートを向上させる方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: c2c13934-9819-4e18- b5c7-60915c907f37
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 削除されたドキュメント
discoiquuid: 609355f6-9003-41b9-9981- ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimizing the sending time{#optimizing-the-sending-time}

メッセージのオープンレートを向上させるために、受信者ごとに送信時間を手動で定義できます。可能な限り、各プロファイルは指定された日時にメッセージを受け取ります。

送信時間の定義は、配信レベルで行うことも、ワークフローを使用することもできます。

電子メールの場合、サーバーの負荷と再試行量に応じて、各受信者に対してスケジュールされた日時にメッセージを送信します。

* 再試行は、インターネットプロバイダーと評価によって異なります。最初の試行時にメッセージが受け入れられない場合があり、いくつかの再試行が実行される可能性があります。See [List of email channel parameters](../../administration/using/configuring-email-channel.md).
* 帯域幅が不足していると、電子メールの受信時に遅延が発生することがあります。

You can view when the message was sent to each recipient in the [sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

いくつかのオプションがあります。

* **[!UICONTROL No optimization]**:メッセージはユーザーの時刻に送信されます。

   For example, if your time zone is GMT+1 and if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 11:00 AM local time for that recipient.

* **[!UICONTROL Send at the recipient's time zone]**:すべての受信者は、タイムゾーンを考慮してメッセージを受け取ります。

   **[!UICONTROL Start sending from]** 例えば、フィールドに"9:00AM"と入力した場合、GMT+3タイムゾーンにある受信者は、その受信者の午前9:00の午前9時にメッセージを受け取ります。

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**:各受信者は、指定した数式によって設定された日時にメッセージを受け取ります。

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

