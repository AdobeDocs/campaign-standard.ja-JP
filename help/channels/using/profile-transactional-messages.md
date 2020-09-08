---
title: プロファイルトランザクションメッセージ
description: プロファイルトランザクションメッセージを作成して公開する方法について説明します。
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 95%

---


# プロファイルトランザクションメッセージ{#profile-transactional-messages}

顧客マーケティングプロファイルに基づいてトランザクションメッセージを送信すると、次のことができます。

* **[!UICONTROL Denylisted address]** または[疲労ルール](../../sending/using/fatigue-rules.md)などのマーケティングタイポロジルールを適用する。
* メッセージ内に購読解除リンクを含める。
* グローバル配信レポートにトランザクションメッセージを追加する。
* カスタマージャーニーでトランザクションメッセージを活用する。

イベントを作成して公開すると（上の[例](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)では買い物かごが放棄された場合）、対応するトランザクションメッセージが自動的に作成されます。

設定手順については、[プロファイルトランザクションメッセージを送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)の節を参照してください。

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、**[!UICONTROL Administrators (all units)]** セキュリティグループに属している必要があります。
>
>疲労ルールは、プロファイルトランザクションメッセージと互換性があります。[疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

## プロファイルトランザクションメッセージの送信 {#sending-a-profile-transactional-message}

プロファイルトランザクションメッセージの作成、パーソナライゼーション、および公開の手順は、イベントトランザクションメッセージの場合と同じです。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

相違点を次に示します。

1. 作成したトランザクションメッセージに移動して編集します。
1. トランザクションメッセージで、「**[!UICONTROL Content]**」セクションをクリックします。トランザクションテンプレートに加えて、**[!UICONTROL Profile]** をターゲットとする任意の E メールテンプレートを選択することもできます。

   ![](assets/message-center_marketing_templates.png)

1. デフォルトの E メールテンプレートを選択します。

   すべてのマーケティング E メールと同様、購読解除リンクが含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   また、リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。[パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)を参照してください。

1. 変更を保存し、メッセージを公開します。[トランザクションメッセージの公開](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)を参照してください。

## プロファイルトランザクションメッセージ配信の監視 {#monitoring-a-profile-transactional-message-delivery}

メッセージが公開され、サイトの統合が完了すると、配信を監視できます。

1. メッセージ配信ログを表示するには、**[!UICONTROL Deployment]** ブロックの右下にあるアイコンをクリックします。

   ログへのアクセスについて詳しくは、[配信の監視](../../sending/using/monitoring-a-delivery.md)を参照してください。

1. 「**[!UICONTROL Sending logs]**」タブを選択します。**[!UICONTROL Status]** 列内の **[!UICONTROL Sent]** は、プロファイルがオプトインしたことを示します。

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as denylisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

オプトアウトしたプロファイルの場合、**[!UICONTROL Denylisted address]** タイポロジルールは対応する受信者を除外します。

このルールは、**[!UICONTROL Profile]** テーブルに基づくすべてのトランザクションメッセージに適用される特定のタイポロジの一部です。

![](assets/message-center_marketing_typology.png)

**関連トピック**：

* [サイトの統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [タイポロジ](../../sending/using/about-typology-rules.md)

