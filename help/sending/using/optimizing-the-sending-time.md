---
title: 送信時間の最適化
description: 送信時間を設定し、メッセージの開封率を高める方法を説明します。
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 100%

---


# 送信時間の最適化{#optimizing-the-sending-time}

メッセージの開封率が上がるように、受信者ごとに送信時刻を手動で定義できます。各プロファイルは、可能な限り、それぞれ指定された日時にメッセージを受信します。

送信時刻は、配信レベルで、またはワークフローを使用して定義できます。

E メールの場合は、サーバーの負荷と再試行の回数に応じて、個々の受信者が予定された日時にメッセージを受け取れるように、ベストエフォート方式で送信されます。

* 再試行は、インターネットプロバイダーや送信者の評判によって決まります。初回の試行時にメッセージが受け入れられない場合があります。このときは、何度か再試行が実行されることがあります。[E メールチャネルパラメーターのリスト](../../administration/using/configuring-email-channel.md)を参照してください。
* 帯域幅の不足が原因で、E メールの受信に遅延が生じる場合があります。

メッセージが[送信ログ](../../sending/using/monitoring-a-delivery.md#sending-logs)の各受信者に送信された日時を表示できます。

次のオプションを選択できます。

* **[!UICONTROL No optimization]**：メッセージはユーザーの時間帯で送信されます。

   例えば、送信側のタイムゾーンが GMT+1 で、「**[!UICONTROL Start sending from]**」フィールドに午前 9 時と入力した場合、GMT+3 のタイムゾーンにいる受信者は、現地時間の午前 11 時にそのメッセージを受け取ります。

* **[!UICONTROL Send at the recipient's time zone]**：すべての受信者に、それぞれのタイムゾーンを考慮してメッセージが届けられます。

   例えば、「**[!UICONTROL Start sending from]**」フィールドに午前 9 時と入力した場合、GMT+3 タイムゾーンの受信者は、現地時刻の午前 9 時にそのメッセージを受信します。

   [受信者のタイムゾーンでのメッセージの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。

* **[!UICONTROL Send at a custom date defined by a formula]**：各受信者は、指定された数式で設定された日時にメッセージを受信します。

   [送信日の計算](../../sending/using/computing-the-sending-date.md)を参照してください。

