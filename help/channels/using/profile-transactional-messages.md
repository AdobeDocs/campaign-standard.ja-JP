---
title: プロファイルトランザクションメッセージ
description: プロファイルトランザクションメッセージ
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
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# プロファイルトランザクションメッセージ{#profile-transactional-messages}

顧客マーケティングトランザクションメッセージに基づいてプロファイルを送信でき、次の操作が可能です。

* または疲労ルールなどのマーケティングタイポロジルール **[!UICONTROL Blacklisted address]** を適 [用してくださ](../../sending/using/fatigue-rules.md)い。
* メッセージ内に購読解除リンクを含めます。
* 追加グローバル配信レポート。
* お客様の遍歴でトランザクションメッセージを活用します。

イベントを作成して公開すると(上の例に従って買い物かごの中断 [が](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) )、対応するトランザクションメッセージが自動的に作成されます。

設定手順は、「送信するイベントの [設定」のプロファイルトランザクションメッセージ](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

イベントがメッセージの送信をトリガーするには、トランザクションメッセージをパーソナライズし、テストして公開する必要があります。

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、セキュリティグループに属してい **[!UICONTROL Administrators (all units)]** る必要があります。
>
>疲労ルールは、疲労ルールとプロファイルトランザクションメッセージに対応します。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md)い。

## 送信，プロファイルトランザクションメッセージ {#sending-a-profile-transactional-message}

プロファイルトランザクションメッセージの作成、パーソナライズ、および公開の手順は、イベントトランザクションメッセージと同じです。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

相違点を次に示します。

1. 作成したトランザクションメッセージに移動して編集します。
1. トランザクションメッセージで、セクションをクリッ **[!UICONTROL Content]** クします。 トランザクションテンプレートに加えて、任意の電子メールテンプレートのターゲット設定を選択することもできま **[!UICONTROL Profile]**&#x200B;す。

   ![](assets/message-center_marketing_templates.png)

1. デフォルトの電子メールテンプレートを選択します。

   すべてのマーケティング電子メールと同様に、リンクに購読解除が含まれます。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   また、リアルタイムイベントに基づく設定とは異なり、すべてのプロファイル情報に直接アクセスしてメッセージをパーソナライズできます。 See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

1. 変更を保存し、メッセージを公開します。 詳しくは、 [トランザクションメッセージの公開](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## 監視，プロファイルトランザクションメッセージ配信 {#monitoring-a-profile-transactional-message-delivery}

メッセージが公開され、サイトの統合が完了したら、メッセージを監視できます。配信

1. メッセージ表示ログを配信するには、ブロックの右下にあるアイコンをクリック **[!UICONTROL Deployment]** します。

   ログへのアクセスの詳細については、「ログの監視」を [参照してください](../../sending/using/monitoring-a-delivery.md)。

1. タブを選択 **[!UICONTROL Sending logs]** します。 列内で、オ **[!UICONTROL Status]** プトイ **[!UICONTROL Sent]** ンしたプロファイルを示します。

   ![](assets/message-center_marketing_sending_logs.png)

1. このタブを選 **[!UICONTROL Exclusions logs]** 択して、表示受信者（例：メッセージアドレス）から除外されたブラックリスト登録済みターゲットを選択します。

   ![](assets/message-center_marketing_exclusion_logs.png)

オプトアウトしたプロファイルの場合、そのタイポロジルールは対応する **[!UICONTROL Blacklisted address]** 受信者を除外します。

このルールは、テーブルに基づくすべてのトランザクションメッセージに適用される特定のタイポロジの一部 **[!UICONTROL Profile]** です。

![](assets/message-center_marketing_typology.png)

**関連トピック**：

* [サイト統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [タイポロジ](../../sending/using/about-typology-rules.md)

