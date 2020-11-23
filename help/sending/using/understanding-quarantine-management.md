---
solution: Campaign Standard
product: campaign
title: 強制隔離管理の理解
description: 強制隔離管理を使用して配信品質を最適化する方法について説明します。
audience: sending
content-type: reference
topic-tags: monitoring-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 84%

---


# 強制隔離管理の理解{#understanding-quarantine-management}

## 強制隔離について {#about-quarantines}

例えば、メールボックスの容量が超過している場合や、アドレスが存在しない場合などに、E メールアドレスや電話番号を強制隔離できます。

どのような場合でも、強制隔離手順は、この[節](#conditions-for-sending-an-address-to-quarantine)で説明する特定のルールに従います。

### 強制隔離による配信の最適化 {#optimizing-your-delivery-through-quarantines}

E メールアドレスまたは電話番号が強制隔離されているプロファイルは、メッセージ準備の際に自動的に除外されます（[配信用の強制隔離アドレスの識別](#identifying-quarantined-addresses-for-a-delivery)を参照）。これによって配信が迅速になります。エラー率は配信の速度に大きく影響するからです。

一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、E メールを自動的にスパムとみなします。したがって、強制隔離を使用すると、これらのプロバイダーによってブロックリストに追加されるのを回避できます。

また、強制隔離は、誤りのある電話番号を配信から除外することで、SMS の送信コスト削減にも役立ちます。

配信を保護および最適化するベストプラクティスについて詳しくは、[このページ](https://helpx.adobe.com/jp/campaign/kb/delivery-best-practices.html)を参照してください。

### Quarantine vs Denylist {#quarantine-vs-denylist}

**強制隔離**&#x200B;は、プロファイル自体ではなく、アドレスのみに適用されます。つまり、2 つのプロファイルに同じ E メールアドレスがある場合、そのアドレスが強制隔離されると、両方のプロファイルが影響を受けます。

同様に、E メールアドレスが強制隔離されているプロファイルは、プロファイルを更新して新しいアドレスを入力できるので、再び配信アクションのターゲットになる可能性があります。

Being on the **Denylist**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). キャンペーンプロセスについて詳しくは、ブロックリストでのオプトインおよびオプトアウトについてを参照してください [](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!NOTE]
>
>ユーザがSMS配信からオプトアウトするために「STOP」などのキーワードを含むSMSメッセージに返信すると、電子メールオプトアウト処理のように、プロファイルブロックリストは上にありません。 プロファイルの電話番号は「**[!UICONTROL On denylist]**」ステータスになり、強制隔離されます。このステータスは電話番号のみを表し、プロファイルは電ブロックリスト子メールの受信を続けるため、はオンになっていません。 詳しくは、[この節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)を参照してください。

## 強制隔離アドレスの識別 {#identifying-quarantined-addresses}

強制隔離されたアドレスは、特定の配信またはプラットフォーム全体を対象としてリストすることができます。

>[!NOTE]
>
>強制隔離からアドレスを削除する必要がある場合は、技術管理者にお問い合わせください。

### 配信用の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-a-delivery}

特定の配信について強制隔離されたアドレスのリストは、配信準備フェーズの途中で、配信ダッシュボードの「**[!UICONTROL Exclusion logs]**」タブに記録されます（[この節](../../sending/using/monitoring-a-delivery.md#exclusion-logs)を参照）。配信準備について詳しくは、[この節](../../sending/using/preparing-the-send.md)を参照してください。

![](assets/exclusion_logs.png)

### プラットフォーム全体の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-the-entire-platform}

管理者は、**[!UICONTROL Administration > Channels > Quarantines > Addresses]** メニューからプラットフォーム全体の強制隔離されたアドレスをリスト表示できます。

>[!NOTE]
>
>このメニューでは、**E メール**、**SMS** および&#x200B;**プッシュ通知**&#x200B;チャネルの強制隔離された要素のリストが表示されます。

![](assets/quarantines1.png)

>[!NOTE]
>
>強制隔離数の増加は、データベースの「老朽化」に関連する、正常な影響です。例えば、E メールアドレスの寿命が 3 年と考えられ、受信者テーブルが毎年 50％増加する場合、強制隔離の増加は次のように計算できます。1 年目の終了時：(1*0.33)/(1+0.5)=22%、2 年目の終了時：((1.22*0.33)+0.33)/(1.5+0.75)=32.5%

## アドレスを強制隔離する条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign は、エラーメッセージの選定時に割り当てられた配信エラーのタイプと理由に従って強制隔離を管理します（[配信エラーのタイプと理由](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)および[バウンスメールの選定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)を参照）。

* **無視のエラー**：アドレスを強制隔離しません。
* **ハードエラー**：対応する E メールアドレスがただちに強制隔離されます。
* **ソフトエラー**：ただちにアドレスが強制隔離されることはありませんが、エラーカウンターがインクリメントされます。エラーカウンターが制限しきい値に達すると、アドレスが強制隔離されます。デフォルトの設定では、しきい値はエラー 5 回に設定されています。2 つのエラーは、24 時間以上間隔を開けて発生する場合に意味を持ちます。5 回目のエラー発生時にアドレスが強制隔離されます。エラーカウンターのしきい値は変更できます。詳しくは、この[ページ](../../administration/using/configuring-email-channel.md#email-channel-parameters)を参照してください。

   再試行後に配信が成功すると、成功前は強制隔離されていたアドレスのエラーカウンターが再初期化されます。アドレスのステータスが「**[!UICONTROL Valid]**」に変わり、**[!UICONTROL Database cleanup]** ワークフローによって、2 日後に強制隔離のリストから削除されます。

ユーザーが E メールをスパム（**フィードバックループ**）と評価した場合、メッセージは Campaign が管理するテクニカルメールボックスに自動的にリダイレクトされます。さらに、その E メールアドレスは自動的に強制隔離され、ステータスが「**[!UICONTROL On denylist]**」となります。この状態はアドレスのみを表し、プロファイルはブロックリスト上にないので、SMSメッセージやプッシュ通知を受け取り続けます。

>[!NOTE]
>
>Adobe Campaign の強制隔離では、大文字と小文字が区別されます。後から再度ターゲットされることのないよう、E メールアドレスは必ず小文字でインポートしてください。

隔離されたアドレスのリスト（[プラットフォーム全体の強制隔離されたアドレスの識別](#identifying-quarantined-addresses-for-the-entire-platform)を参照）の「**[!UICONTROL Error reason]**」フィールドは、選択したアドレスが強制隔離された理由を示します。

![](assets/quarantines2.png)

