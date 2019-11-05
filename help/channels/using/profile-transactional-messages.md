---
title: プロファイルトランザクションメッセージ
description: プロファイルトランザクションメッセージを作成して公開する方法について説明します。
page-status-flag: 非活性化の
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: トランザクションメッセージング
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# プロファイルトランザクションメッセージ{#profile-transactional-messages}

顧客マーケティングプロファイルに基づいてトランザクションメッセージを送信でき、次のことができます。

* または疲労ルールなどのマーケティングタイポロジ **[!UICONTROL Blacklisted address]** ルールを [適用します](../../administration/using/fatigue-rules.md)。
* メッセージ内に購読解除リンクを含めます。
* グローバル配信レポートにトランザクションメッセージを追加します。
* お客様の遍歴でトランザクション・メッセージを活用します。

イベントを作成して発行すると(上の例に従って買い物かごの中断が発生し [た](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) )、対応するトランザクションメッセージが自動的に作成されます。

設定手順は、「プロファイルトランザクションメ [ッセージを送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」の節に記載されています。

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、セキュリティグループに属してい **[!UICONTROL Administrators (all units)]** る必要があります。
>
>疲労ルールは、プロファイルトランザクションメッセージと互換性があります。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

## プロファイルトランザクションメッセージの送信 {#sending-a-profile-transactional-message}

プロファイルトランザクションメッセージの作成、パーソナライズ、および公開の手順は、イベントトランザクションメッセージの場合と同じです。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

相違点を次に示します。

1. 作成されたトランザクションメッセージに移動して編集します。
1. トランザクションメッセージで、セクションをクリッ **[!UICONTROL Content]** クします。 トランザクションテンプレートに加えて、任意の電子メールテンプレートのターゲット設定を選択することもできま **[!UICONTROL Profile]**&#x200B;す。

   ![](assets/message-center_marketing_templates.png)

1. デフォルトの電子メールテンプレートを選択します。

   すべてのマーケティング電子メールと同様に、購読解除リンクが含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   また、リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。 See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

1. 変更を保存し、メッセージを公開します。 詳しくは、ト [ランザクションメッセージの公開を参照してくださ](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)い。

## プロファイルトランザクションメッセージ配信の監視 {#monitoring-a-profile-transactional-message-delivery}

メッセージが公開され、サイト統合が完了したら、配信を監視できます。

1. メッセージ配信ログを表示するには、ブロックの右下にあるアイコンをクリックし **[!UICONTROL Deployment]** ます。

   ログへのアクセスの詳細については、「配信の監視」を [参照してください](../../sending/using/monitoring-a-delivery.md)。

1. Select the **[!UICONTROL Sending logs]** tab. 列には、プロ **[!UICONTROL Status]** ファイルがオ **[!UICONTROL Sent]** プトインされたことを示します。

   ![](assets/message-center_marketing_sending_logs.png)

1. タブを選択し **[!UICONTROL Exclusions logs]** て、ブラックリストに記載されたアドレスなど、メッセージターゲットから除外された受信者を表示します。

   ![](assets/message-center_marketing_exclusion_logs.png)

オプトアウトしたプロファイルの場合、タイポロジルールによ **[!UICONTROL Blacklisted address]** って、対応する受信者が除外されます。

このルールは、テーブルに基づくすべてのトランザクションメッセージに適用される特定のタイポロジの一部 **[!UICONTROL Profile]** です。

![](assets/message-center_marketing_typology.png)

**関連トピック**：

* [サイト統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [タイポロジ](../../administration/using/about-typology-rules.md)

