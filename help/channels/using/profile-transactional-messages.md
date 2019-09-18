---
title: トランザクションメッセージのプロファイル
seo-title: トランザクションメッセージのプロファイル
description: トランザクションメッセージのプロファイル
seo-description: プロファイルトランザクションメッセージを作成して公開する方法を説明します。
page-status-flag: 未活性化の
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: トランザクション·メッセージング
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# トランザクションメッセージのプロファイル{#profile-transactional-messages}

顧客マーケティング·プロファイルに基づいてトランザクション·メッセージを送信でき、次の操作を実行できます。

* または疲労ルールなどのマーケティング **[!UICONTROL Blacklisted address]** 類型ル [ールを適用](../../administration/using/fatigue-rules.md)。
* メッセージ内にサブスクリプション解除リンクを含めます。
* トランザクションメッセージをグローバル配信レポートに追加します。
* お客様の旅においてトランザクション·メッセージを活用します。

イベントを作成して公開すると(上記の例に従ってカートを破棄する [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) )、対応するトランザクションメッセージが自動的に作成されます。

構成手順は、「プロファイルトランザクショ [ンメッセージを送信するイベントの構成」セクションで説明します](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

イベントがトランザクション·メッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクション·メッセージにアクセスするには、管理権限を持っているか、(mcExec)セキュリ **[!UICONTROL Message Center agents]** ティ·グループに表示されている必要があります。 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

## プロファイルトランザクションメッセージの送信 {#sending-a-profile-transactional-message}

プロファイル·トランザクション·メッセージを作成、パーソナライズ、公開する手順は、イベント·トランザクション·メッセージと同じです。 「イベント·ト [ランザクション·メッセージ](../../channels/using/event-transactional-messages.md)」を参照。

次に、相違点を示します。

1. 作成されたトランザクションメッセージを編集するために移動します。
1. トランザクション·メッセージで、セクションをクリ **[!UICONTROL Content]** ックします。 トランザクションテンプレートに加えて、ターゲットとなる既定の電子メールテンプレートを選択することもできま **[!UICONTROL Profile]**&#x200B;す。

   ![](assets/message-center_marketing_templates.png)

1. 既定の電子メールテンプレートを選択します。

   すべてのマーケティング電子メールと同様に、サブスクリプション解除リンクが含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   また、リアルタイムイベントに基づく構成とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをカスタマイズできます。 「個人用設 [定フィールドの挿入」を参照してくださ](../../designing/using/personalization.md#inserting-a-personalization-field)い。

1. 変更を保存し、メッセージを発行します。 「トランザク [ション·メッセージの発行」を参照](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## プロファイルトランザクションメッセージ配信の監視 {#monitoring-a-profile-transactional-message-delivery}

メッセージが発行され、サイトの統合が完了したら、配信を監視できます。

1. メッセージ配信ログを表示するには、ブロックの右下にあるアイコンをクリック **[!UICONTROL Deployment]** します。

   ログへのアクセスの詳細については、「配信の監視」を [参照してください](../../sending/using/monitoring-a-delivery.md)。

1. タブを選択 **[!UICONTROL Sending logs]** します。 列で、縦断 **[!UICONTROL Status]** がオプ **[!UICONTROL Sent]** トインされていることを示します。

   ![](assets/message-center_marketing_sending_logs.png)

1. タブを選択 **[!UICONTROL Exclusions logs]** すると、ブラックリスト·アドレスなど、メッセージ·ターゲットから除外された受信者が表示されます。

   ![](assets/message-center_marketing_exclusion_logs.png)

オフにしたプロファイルの場合、類型規則によっ **[!UICONTROL Blacklisted address]** て対応する受信者が除外されます。

この規則は、テーブルに基づくすべてのトランザクションメッセージに適用される特定の類型の一部 **[!UICONTROL Profile]** です。

![](assets/message-center_marketing_typology.png)

**関連トピック**:

* [サイト統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [類型](../../administration/using/about-typology-rules.md)

