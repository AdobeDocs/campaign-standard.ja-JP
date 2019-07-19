---
title: 強制隔離について
seo-title: 強制隔離について
description: 強制隔離について
seo-description: 隔離管理で配信品質を最適化する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 3c287865-1ada-4351- b205-51807ff9f7ed
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: de3a50b6- ea8f-4521-996b- c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5b3ea982f08e1198e8c88f78a5faf8a80b935db4

---


# Understanding quarantine management{#understanding-quarantine-management}

## About quarantines {#about-quarantines}

電子メールアドレスまたは電話番号を隔離できます（例えば、メールボックスがいっぱいの場合や、アドレスが存在しない場合）。

In any case, the quarantine procedure complies with specific rules described in this [section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).

### Optimizing your delivery through quarantines {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-a-delivery)). これにより、配信速度に大きな影響があるので、配信速度が向上します。

一部のインターネットアクセスプロバイダーは、無効なアドレスのレートが高すぎる場合にスパムとなる電子メールを自動的に検討します。したがって、これらのプロバイダーによるブラックリストに記載されたブラックリストを避けることができます。

また、強制隔離された電話番号を配信から除外することによって、SMSのコストを削減することもできます。

For more on best practices to secure and optimize your deliveries, refer to [this page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantine vs blacklisting {#quarantine-vs-blacklisting}

**強制隔離** は、プロファイル自体ではなく、アドレスにのみ適用されます。つまり、2つのプロファイルが同じ電子メールアドレスを持つと、アドレスが隔離された場合にも影響を受けます。

同様に、電子メールアドレスが隔離されたプロファイルは、プロファイルを更新して新しいアドレスを入力し、その後配信アクションでターゲット設定することができます。

**一方、ブラックリスト**&#x200B;に登録されている場合、購読の対象外（オプトアウト（オプトアウト）後など）によってプロファイルがターゲット化されなくなります。For more on the blacklisting process, refer to [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>SMS配信からオプトアウトするために、ユーザーが「停止」などのキーワードを持つSMSメッセージに返信した場合、そのプロファイルは電子メールオプトアウトプロセスのようにブラックリストに記載されません。The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. このステータスは電話番号のみを指し、プロファイルはブラックリストに記載されておらず、ユーザーは電子メールメッセージの受信を継続します。For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifying quarantined addresses {#identifying-quarantined-addresses}

隔離されたアドレスは、特定の配信またはプラットフォーム全体でリストできます。

>[!NOTE]
>
>隔離から住所を削除する必要がある場合は、テクニカル管理者にお問い合わせください。

### Identifying quarantined addresses for a delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifying quarantined addresses for the entire platform {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>This menu lists quarantined elements for **email**, **SMS** and **Push notification** channels.

![](assets/quarantines1.png)

>[!NOTE]
>
>強制隔離の数は、データベースの「摩耗とスプール」に関連する通常の効果です。例えば、電子メールアドレスの存続期間が3年で、受信者テーブルが毎年50%増加した場合、四半期別の増加は次のように計算できます。年末1:（1*0.33）/（1+0.5）=22%.年末2:（（1.22*0.33）+0.33）/（1.5+0.75）=32.5%.

## Conditions for sending an address to quarantine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign manages quarantine according to the delivery failure type and the reason assigned during error messages qualification (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) and [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **無視されたエラー**:無視されたエラーは、強制隔離にアドレスを送信しません。
* **ハードエラー**:対応する電子メールアドレスが直ちに強制隔離に送信されます。
* **ソフトエラー**:ソフトエラーは、直ちに強制隔離するアドレスを送信しませんが、エラーカウンターを増分します。エラーカウンターが上限しきい値に達すると、アドレスが強制隔離されます。デフォルト設定では、しきい値は5つのエラーで設定され、2つのエラーが少なくとも24時間以上発生した場合は有意なエラーが発生します。6番目のエラーで住所が強制隔離されます。エラーカウンターしきい値は変更できます。For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   再試行後に配信が成功した場合、隔離された前のアドレスのエラーカウンターが再初期化されます。The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user's email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. このステータスはアドレスのみを参照し、プロファイルはブラックリストに記載されません。これにより、ユーザーはSMSメッセージおよびプッシュ通知の受信を継続します。

>[!NOTE]
Adobe Campaignでの強制隔離では大文字と小文字が区別されます。後で再ターゲット設定されないように、電子メールアドレスを小文字で読み込みます。

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

