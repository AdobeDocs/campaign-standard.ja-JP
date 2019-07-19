---
title: プロファイルトランザクションメッセージ
seo-title: プロファイルトランザクションメッセージ
description: プロファイルトランザクションメッセージ
seo-description: プロファイルトランザクションメッセージを作成して公開する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: a8efe979-74ae-46ff- a305- b86a90679581
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: トランザクションメッセージング
discoiquuid: dcb90fc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Profile transactional messages{#profile-transactional-messages}

トランザクションメッセージは、顧客のマーケティングプロファイルに基づいて送信でき、次のことが可能です。

* **[!UICONTROL Blacklisted address]**[例えば、疲労ルール](../../administration/using/fatigue-rules.md)などのマーケティングタイポロジルールを適用します。
* メッセージ内に購読解除リンクを含めます。
* トランザクションメッセージをグローバル配信レポートに追加します。
* 顧客の遍歴のトランザクションメッセージを活用します。

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send a profile transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。

## Sending a profile transactional message {#sending-a-profile-transactional-message}

プロファイルトランザクションメッセージの作成、パーソナライズおよび公開の手順は、イベントトランザクションメッセージと同じです。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

違いは以下のとおりです。

1. 作成されたトランザクションメッセージに移動します。
1. In the transactional message, click the **[!UICONTROL Content]** section. In addition to the transactional template, you can also choose the default email template, which targets **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. デフォルトの電子メールテンプレートを選択します。

   すべてのマーケティング電子メールと同様、購読解除リンクが含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   また、リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズすることができます。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

1. 変更を保存して、メッセージを公開します。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

メッセージが公開され、サイトの統合が完了したら、配信を監視できます。

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   For more information on accessing the logs, see [Monitoring the delivery](../../sending/using/monitoring-a-delivery.md).

1. **[!UICONTROL Sending logs]** タブを選択します。**[!UICONTROL Status]** 列に、プロファイルがオプトインしている **[!UICONTROL Sent]** ことを示します。

   ![](assets/message-center_marketing_sending_logs.png)

1. **[!UICONTROL Exclusions logs]** このタブを選択すると、ブラックリストに記載されたアドレスなど、メッセージターゲットから除外された受信者を表示できます。

   ![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Blacklisted address]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**関連トピック**:

* [サイトの統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [タイポロジ](../../administration/using/about-typology-rules.md)

