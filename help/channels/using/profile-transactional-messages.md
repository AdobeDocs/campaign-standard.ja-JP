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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---


# プロファイルトランザクションメッセージ{#profile-transactional-messages}

顧客マーケティングプロファイルに基づいてトランザクションメッセージを送信でき、次のことができます。

* **[!UICONTROL Address on block list]** または [疲労ルールなどのマーケティングタイポロジルールを適用します](../../sending/using/fatigue-rules.md)。
* メッセージ内に購読解除リンクを含めます。
* グローバル追加配信レポートへのトランザクションメッセージ。
* お客様の遍歴でトランザクションメッセージを活用します。

イベントを作成して公開すると( [上の例に従って買い物かごが中断した場合](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) )、対応するトランザクションメッセージが自動的に作成されます。

設定手順は、「プロファイルトランザクションメッセージを送信するためのイベントの [設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」の節に記載されています。

イベントがトランザクションメッセージの送信をトリガーするには、メッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、 **[!UICONTROL Administrators (all units)]** セキュリティグループに属している必要があります。
>
>疲労ルールは、プロファイルトランザクションメッセージと互換性があります。 「 [疲労ルール](../../sending/using/fatigue-rules.md)」を参照してください。

## プロファイルトランザクションメッセージの送信 {#sending-a-profile-transactional-message}

プロファイルトランザクションメッセージの作成、個人化、および公開の手順は、イベントトランザクションメッセージの場合と同じです。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

相違点を次に示します。

1. 作成したトランザクションメッセージに移動して編集します。
1. トランザクションメッセージで、セクションをクリックし **[!UICONTROL Content]** ます。 トランザクションテンプレートに加えて、任意の電子メールテンプレートのターゲット設定を選択することもで **[!UICONTROL Profile]**&#x200B;きます。

   ![](assets/message-center_marketing_templates.png)

1. デフォルトの電子メールテンプレートを選択します。

   すべてのマーケティング電子メールと同様、購読解除リンクが含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   また、リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスして、メッセージをパーソナライズできます。 See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

1. 変更を保存し、メッセージを発行します。 詳しくは、トランザクションメッセージの [公開を参照してください](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## プロファイルトランザクションメッセージ配信の監視 {#monitoring-a-profile-transactional-message-delivery}

メッセージが公開され、サイトの統合が完了したら、配信を監視できます。

1. メッセージ配信ログを表示するには、 **[!UICONTROL Deployment]** ブロックの右下にあるアイコンをクリックします。

   ログへのアクセスの詳細については、「配信の [監視](../../sending/using/monitoring-a-delivery.md)」を参照してください。

1. タブを選択し **[!UICONTROL Sending logs]** ます。 列内の **[!UICONTROL Status]** は、プロファイルがオプトインしたことを **[!UICONTROL Sent]** 示します。

   ![](assets/message-center_marketing_sending_logs.png)

1. 「 **[!UICONTROL Exclusions logs]** 」タブを選択して、ブロックリスト上のアドレスなど、メッセージターゲットから除外された受信者を表示します。

   ![](assets/message-center_marketing_exclusion_logs.png)

オプトアウトしたプロファイルの場合、 **[!UICONTROL Address on block list]** タイポロジルールは対応する受信者を除外します。

このルールは、テー **[!UICONTROL Profile]** ブルに基づくすべてのトランザクションメッセージに適用される特定のタイポロジの一部です。

![](assets/message-center_marketing_typology.png)

**関連トピック**：

* [サイト統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [タイポロジ](../../sending/using/about-typology-rules.md)

