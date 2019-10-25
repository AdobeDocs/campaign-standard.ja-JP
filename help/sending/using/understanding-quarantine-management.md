---
title: 強制隔離管理の理解
seo-title: 強制隔離管理の理解
description: 強制隔離管理の理解
seo-description: 検疫管理を使用して配信品質を最適化する方法を説明します。
page-status-flag: 非活性化の
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 強制隔離管理の理解{#understanding-quarantine-management}

## 強制隔離について {#about-quarantines}

メールボックスがいっぱいの場合や、アドレスが存在しない場合など、電子メールアドレスや電話番号を隔離できます。

In any case, the quarantine procedure complies with specific rules described in this [section](#conditions-for-sending-an-address-to-quarantine).

### 強制隔離による配信の最適化 {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](#identifying-quarantined-addresses-for-a-delivery)). これによって配信が迅速になります。エラー率は配信の速度に大きく影響するからです。

一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、E メールを自動的にスパムとみなします。そのため、強制隔離することで、こうしたプロバイダーによるブラックリストへの登録を回避できます。

また、強制隔離は、誤りのある電話番号を配信から除外することで、SMS の送信コスト削減にも役立ちます。

配信を保護および最適化するベストプラクティスについて詳しくは、[このページ](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)を参照してください。

### 強制隔離とブラックリストへの登録 {#quarantine-vs-blacklisting}

**強制隔離**&#x200B;は、プロファイル自体ではなく、アドレスのみに適用されます。つまり、2 つのプロファイルに同じ E メールアドレスがある場合、そのアドレスが強制隔離されると、両方のプロファイルが影響を受けます。

同様に、E メールアドレスが強制隔離されているプロファイルは、プロファイルを更新して新しいアドレスを入力できるので、再び配信アクションのターゲットになる可能性があります。

一方、**ブラックリストへの登録**&#x200B;では、登録されたプロファイルが、購読解除（オプトアウト）後のように、それ以降はどのような配信のターゲットにもならなくなります。ブラックリスト作成プロセスの詳細は、「Campaignでのブラックリス [ト作成の管理」を参照してくださ](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)い。

>[!NOTE]
>
>SMS 配信からのオプトアウトのために「STOP」のようなキーワードを使ってユーザーが SMS メッセージに返信しても、そのユーザーのプロファイルは、E メールのオプトアウトプロセスのようにはブラックリストに登録されません。プロファイル電話番号は、状態の検疫に送信さ **[!UICONTROL Blacklisted]** れます。 このステータスは電話番号のみを表し、プロファイルはブラックリストに記載されていないので、ユーザーは電子メールメッセージを引き続き受信します。 詳しくは、[この節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)を参照してください。

## 強制隔離アドレスの識別 {#identifying-quarantined-addresses}

強制隔離されたアドレスは、特定の配信またはプラットフォーム全体を対象としてリストすることができます。

>[!NOTE]
>
>検疫から住所を削除する必要がある場合は、技術管理者に問い合わせてください。

### 配信用の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### プラットフォーム全体の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-the-entire-platform}

管理者は、メニューからプラットフォーム全体の検疫済みアドレスをリストで **[!UICONTROL Administration > Channels > Quarantines > Addresses]** きます。

>[!NOTE]
>
>このメニューでは、**E メール**、**SMS** および&#x200B;**プッシュ通知**&#x200B;チャネルの強制隔離された要素のリストが表示されます。

![](assets/quarantines1.png)

>[!NOTE]
>
>検疫数の増加は、データベースの「摩耗と裂傷」に関連する通常の効果です。 例えば、電子メールアドレスの有効期間が3年と見なされ、受信者テーブルが年に50%増加した場合、検疫の増加は次のように計算できます。1年目の終わり：(1*0.33)/(1+0.5)=22% 2年目の終わり：((1.22*0.33)+0.33)/(1.5+0.75)=32.5%

## アドレスを強制隔離する条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaignは、配信失敗のタイプとエラーメッセージの認定中に割り当てられた理由に従って検疫を管理します(配信失敗のタイプと理由 [、バウン](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) スのメール認定を参照 [](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification))。

* **無視のエラー**：アドレスを強制隔離しません。
* **ハードエラー**：対応する E メールアドレスがただちに強制隔離されます。
* **ソフトエラー**：ただちにアドレスが強制隔離されることはありませんが、エラーカウンターがインクリメントされます。エラーカウンターが制限しきい値に達すると、アドレスが強制隔離されます。デフォルトの設定では、しきい値はエラー 5 回に設定されています。2 つのエラーは、24 時間以上間隔を開けて発生する場合に意味を持ちます。6 回目のエラー発生時にアドレスが強制隔離されます。エラーカウンターのしきい値は変更できます。詳しくは、この[ページ](../../administration/using/configuring-email-channel.md#email-channel-parameters)を参照してください。

   再試行後に配信が成功すると、成功前は強制隔離されていたアドレスのエラーカウンターが再初期化されます。The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. その後、ユーザーの電子メールアドレスが自動的にステータスと共に検疫に送信さ **[!UICONTROL Blacklisted]** れます。 この状態はアドレスのみを表し、プロファイルはブラックリストに記載されていないので、ユーザーはSMSメッセージとプッシュ通知を受信し続けます。

>[!NOTE]
Adobe Campaignでの検疫では、大文字と小文字が区別されます。 後で再ターゲット設定されないように、電子メールアドレスは小文字でインポートしてください。

検疫済みアドレスのリスト(「隔離済みアド [レスの識別(プラットフォーム全体での検疫済みアドレスの識別](#identifying-quarantined-addresses-for-the-entire-platform)) **[!UICONTROL Error reason]** 」を参照)で、選択したアドレスが検疫に含まれた理由を示します。

![](assets/quarantines2.png)

