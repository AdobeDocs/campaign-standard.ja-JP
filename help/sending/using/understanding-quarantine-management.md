---
title: 強制隔離管理の理解
description: 強制隔離管理を使用して配信品質を最適化する方法を学びます。
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 121ec37cef6193d3a7085b6d0296b6a2e7cafa06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 45%

---


# 強制隔離管理の理解{#understanding-quarantine-management}

## 強制隔離について {#about-quarantines}

メールボックスがいっぱいの場合や、アドレスが存在しない場合など、電子メールアドレスや電話番号を隔離できます。

In any case, the quarantine procedure complies with specific rules described in this [section](#conditions-for-sending-an-address-to-quarantine).

### 強制隔離による配信の最適化 {#optimizing-your-delivery-through-quarantines}

E メールアドレスまたは電話番号が強制隔離されているプロファイルは、メッセージ準備の際に自動的に除外されます（[配信用の強制隔離アドレスの識別](#identifying-quarantined-addresses-for-a-delivery)を参照）。これによって配信が迅速になります。エラー率は配信の速度に大きく影響するからです。

一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、E メールを自動的にスパムとみなします。したがって、強制隔離を使用すると、これらのプロバイダーによってブロックリストに追加されるのを回避できます。

また、強制隔離は、誤りのある電話番号を配信から除外することで、SMS の送信コスト削減にも役立ちます。

配信を保護および最適化するベストプラクティスについて詳しくは、[このページ](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)を参照してください。

### 強制隔離とブロックリスト {#quarantine-vs-block-list}

**強制隔離**&#x200B;は、プロファイル自体ではなく、アドレスのみに適用されます。つまり、2 つのプロファイルに同じ E メールアドレスがある場合、そのアドレスが強制隔離されると、両方のプロファイルが影響を受けます。

同様に、E メールアドレスが強制隔離されているプロファイルは、プロファイルを更新して新しいアドレスを入力できるので、再び配信アクションのターゲットになる可能性があります。

Being on the **block list**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). ブロックリストプロセスについて詳しくは、キャンペーンでのオプトインとオプトアウトに [ついてを参照してください](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!NOTE]
>
>ユーザがSMS配信からオプトアウトするために「STOP」などのキーワードを持つSMSメッセージに返信した場合、電子メールオプトアウト処理のように、ブロックリストにプロファイルは追加されません。 プロファイルの電話番号は、ステータスと共に強制隔離に送信され **[!UICONTROL On block list]** ます。 このステータスは電話番号のみを表し、プロファイルはブロックリスト上にないので、ユーザーは電子メールメッセージの受信を続行します。 詳しくは、[この節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)を参照してください。

## 強制隔離アドレスの識別 {#identifying-quarantined-addresses}

強制隔離されたアドレスは、特定の配信またはプラットフォーム全体を対象としてリストすることができます。

>[!NOTE]
>
>強制隔離から住所を削除する必要がある場合は、テクニカル管理者に問い合わせてください。

### 配信用の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### プラットフォーム全体の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-the-entire-platform}

管理者は、 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** メニューからプラットフォーム全体のアドレスを強制隔離してリストできます。

>[!NOTE]
>
>このメニューでは、**E メール**、**SMS** および&#x200B;**プッシュ通知**&#x200B;チャネルの強制隔離された要素のリストが表示されます。

![](assets/quarantines1.png)

>[!NOTE]
>
>強制隔離数の増加は、データベースの「損耗」に関連する通常の効果です。 例えば、電子メールアドレスの有効期間が3年と見なされ、受信者表の値が年に50%増加する場合、強制隔離数の増加は次のように計算できます。 1年目の終わり： (1*0.33)/(1+0.5)=22% 2 年目の終了時：((1.22*0.33)+0.33)/(1.5+0.75)=32.5%

## アドレスを強制隔離する条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaignは、強制隔離の失敗タイプとエラーメッセージの資格時に割り当てられた理由に従って配信を管理します( [配信の失敗タイプと理由](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) 、 [バウンスのメール資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification))。

* **無視のエラー**：アドレスを強制隔離しません。
* **ハードエラー**：対応する E メールアドレスがただちに強制隔離されます。
* **ソフトエラー**：ただちにアドレスが強制隔離されることはありませんが、エラーカウンターがインクリメントされます。エラーカウンターが制限しきい値に達すると、アドレスが強制隔離されます。デフォルトの設定では、しきい値はエラー 5 回に設定されています。2 つのエラーは、24 時間以上間隔を開けて発生する場合に意味を持ちます。5 回目のエラー発生時にアドレスが強制隔離されます。エラーカウンターのしきい値は変更できます。詳しくは、この[ページ](../../administration/using/configuring-email-channel.md#email-channel-parameters)を参照してください。

   再試行後に配信が成功すると、成功前は強制隔離されていたアドレスのエラーカウンターが再初期化されます。The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user&#39;s email address is then automatically sent to quarantine with the **[!UICONTROL On block list]** status. この状態はアドレスのみを表し、プロファイルはブロックリスト上にないので、SMSメッセージやプッシュ通知を受信し続けます。

>[!NOTE]
Adobe Campaign の強制隔離では、大文字と小文字が区別されます。後から再度ターゲットされることのないよう、E メールアドレスは必ず小文字でインポートしてください。

隔離されたアドレスのリスト(プラットフォーム全体の隔離されたアドレスの [識別を参照](#identifying-quarantined-addresses-for-the-entire-platform))で、 **[!UICONTROL Error reason]** フィールドは選択したアドレスが強制隔離に配置された理由を示します。

![](assets/quarantines2.png)

