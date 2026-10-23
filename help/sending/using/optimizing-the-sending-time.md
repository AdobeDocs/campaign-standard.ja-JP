---
title: 送信時間の最適化
description: 送信時間を設定し、メッセージの開封率を高める方法を説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
TQID: 'https://experienceleague.adobe.com/FjL5t1ohvrgDdqLiCr03z1Nbq6IukIBysKkmXJ7561c'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: 0d3d7867-163e-5570-9cfc-7132e55fb049
    internal-label: Send Time Optimization
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 73%
---
# 送信時間の最適化{#optimizing-the-sending-time}

メッセージの開封率が上がるように、受信者ごとに送信時刻を手動で定義できます。 各プロファイルは、可能な限り、それぞれ指定された日時にメッセージを受信します。

送信時刻は、配信レベルで、またはワークフローを使用して定義できます。

メールの場合は、サーバーの負荷と再試行の回数に応じて、個々の受信者がスケジュールされた日時にメッセージを受け取れるように、ベストエフォート方式で送信されます。

* 再試行は、インターネットプロバイダーや送信者の評判によって決まります。 初回の試行時にメッセージが受け入れられない場合があります。このときは、何度か再試行が実行されることがあります。 [メールチャネルパラメーターのリスト](../../administration/using/configuring-email-channel.md)を参照してください。
* 帯域幅の不足が原因で、メールの受信に遅延が生じる場合があります。

メッセージが[送信ログ](../../sending/using/monitoring-a-delivery.md#sending-logs)の各受信者に送信された日時を表示できます。

次のオプションを選択できます。

* **[!UICONTROL No optimization]**：メッセージはユーザーの時間帯で送信されます。

  例えば、タイムゾーンがGMT+1で、**[!UICONTROL Start sending from]** フィールドに9:00 AMと入力した場合、GMT+3 タイムゾーンの受信者は、その受信者の現地時間の午前11:00にメッセージを受け取ります。

* **[!UICONTROL Send at the recipient's time zone]**：すべての受信者に、それぞれのタイムゾーンを考慮してメッセージが届けられます。

  例えば、**[!UICONTROL Start sending from]** フィールドに「午前9:00」と入力すると、GMT+3 タイムゾーンの受信者は、その受信者の現地時間の午前9:00にメッセージを受け取ります。

  [受信者のタイムゾーンでのメッセージの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)を参照してください。

* **[!UICONTROL Send at a custom date defined by a formula]**：各受信者は、指定された数式で設定された日時にメッセージを受信します。

  [送信日の計算](../../sending/using/computing-the-sending-date.md)を参照してください。
