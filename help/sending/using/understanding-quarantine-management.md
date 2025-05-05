---
title: 強制隔離管理の理解
description: 強制隔離管理を使用して配信品質を最適化する方法について説明します。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 53%

---

# 強制隔離管理について{#understanding-quarantine-management}

## 強制隔離について {#about-quarantines}

例えば、メールボックスの容量が超過している場合や、アドレスが存在しない場合などに、メールアドレスや電話番号を強制隔離できます。

どのような場合でも、強制隔離手順は、この[節](#conditions-for-sending-an-address-to-quarantine)で説明する特定のルールに従います。

### 強制隔離による配信の最適化 {#optimizing-your-delivery-through-quarantines}

メールアドレスまたは電話番号が強制隔離されているプロファイルは、メッセージ準備の際に自動的に除外されます（[配信用の強制隔離アドレスの識別](#identifying-quarantined-addresses-for-a-delivery)を参照）。これによって配信が迅速になります。エラー率は配信の速度に大きく影響するからです。

一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、メールを自動的にスパムと見なします。したがって、強制隔離を使用すると、これらのプロバイダーによってブロックリストに追加されるのを回避できます。

また、強制隔離は、誤りのある電話番号を配信から除外することで、SMS の送信コスト削減にも役立ちます。

配信を保護および最適化するベストプラクティスについて詳しくは、[このページ](../../sending/using/delivery-best-practices.md)を参照してください。

### 強制隔離とブロックリスト {#quarantine-vs-denylist}

強制隔離とブロックリストは、同じオブジェクトには適用されません。

* **強制隔離**&#x200B;は、プロファイル自体ではなく、**アドレス**（または電話番号など）にのみ適用されます。例えば、メールアドレスが強制隔離されているプロファイルは、プロファイルを更新して新しいアドレスを入力できるので、再び配信アクションのターゲットになる可能性があります。 同様に、2 つのプロファイルの電話番号が同じ場合、その番号が強制隔離されると、両方のプロファイルが影響を受けます。

  強制隔離されたアドレスまたは電話番号は、[除外ログ](#identifying-quarantined-addresses-for-a-delivery)（配信の場合）または[強制隔離リスト](#identifying-quarantined-addresses-for-the-entire-platform)（プラットフォーム全体の場合）に表示されます。

* 一方、**ブロックリスト**&#x200B;への登録では、特定のチャネルを購読解除（オプトアウト）した後などは、**プロファイル**&#x200B;は配信のターゲットとなりません。例えば、メールチャネルのブロックリスト上のプロファイルに 2 つのメールアドレスがある場合、両方のアドレスが配信から除外されます。 ブロックリストプロセスについて詳しくは、[Campaign のオプトインとオプトアウトについて ](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md) を参照してください。

  プロファイルが 1 つ以上のチャネルのブロックリストに含まれているかどうかは、プロファイルの「**[!UICONTROL General]**」タブの「**[!UICONTROL No longer contact (on denylist)]**」セクションで確認できます。 詳しくは、[この節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)を参照してください。

>[!NOTE]
>
>強制隔離には、受信者がメッセージをスパムとして報告したり、「STOP」などのキーワードを使用して SMS メッセージに返信したりする場合に適用される **オン^ブロックリスト** ステータスが含まれます。 この場合、プロファイルの関連するアドレスまたは電話番号は、**[!UICONTROL On denylist]** ステータスで強制隔離に送信されます。 STOP SMS メッセージの管理について詳しくは、[この節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)を参照してください。

&lt;!- SMS 配信からオプトアウトするために、ユーザーが STOP などのキーワードを使用して SMS メッセージに返信した場合、そのユーザーのプロファイルは、メールオプトアウトプロセスのようにブロックリストには追加されません。 代わりに、プロファイルの電話番号は、**[!UICONTROL On denylist]** ステータスで強制隔離に送信されます。 このステータスは電話番号のみを参照し、プロファイルは引き続きメールメッセージを受信します。<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## 強制隔離アドレスの識別 {#identifying-quarantined-addresses}

強制隔離されたアドレスは、特定の配信先またはプラットフォーム全体について表示できます。

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### 配信の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-a-delivery}

特定の配信について強制隔離されたアドレスのリストは、配信準備フェーズの途中で、配信ダッシュボードの「**[!UICONTROL Exclusion logs]**」タブに記録されます（[この節](../../sending/using/monitoring-a-delivery.md#exclusion-logs)を参照）。配信準備について詳しくは、[この節](../../sending/using/preparing-the-send.md)を参照してください。

![](assets/exclusion_logs.png)

### プラットフォーム全体の強制隔離アドレスの識別 {#identifying-quarantined-addresses-for-the-entire-platform}

管理者は、**[!UICONTROL Administration > Channels > Quarantines > Addresses]** メニューから、プラットフォーム全体の強制隔離中のメールアドレスの詳細なリストにアクセスできます。

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>強制隔離件数の増加は、データベースの「消耗」に関連する通常の影響です。 例えば、メールアドレスの有効期間が 3 年と考えられ、受信者テーブルが毎年 50% 増加する場合、強制隔離の増加は次のように計算できます。1 年目の終了時：（1&#42;0.33）/（1+0.5）=22%。 2 年目の終了時：((1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

リストの参照に役立つフィルターを使用できます。 アドレス、ステータスまたはチャネル（あるいはその両方）でフィルタリングできます。

![](assets/quarantines-filters.png)

エントリごとに編集または [ 削除 ](#removing-a-quarantined-address) したり、新しいエントリを作成したりできます。

エントリを編集するには、対応する行をクリックし、必要に応じてフィールドを変更します。

![](assets/quarantines-edit.png)

新しいエントリを手動で追加するには、「**[!UICONTROL Create]**」ボタンを使用します。

![](assets/quarantines-create-button.png)

アドレス（または電話番号など）とチャネルタイプを定義します。 強制隔離リストに表示するステータスとエラー理由を設定できます。 また、エラーが発生した日付、エラー数を指定し、エラーテキストを入力することもできます。 そのアドレスに送信された最後の配信を、必要に応じてドロップダウンリストから選択します。

![](assets/quarantines-create-last-delivery.png)

## 強制隔離からのアドレスの削除 {#removing-a-quarantined-address}

### 自動更新 {#unquarantine-auto}

特定の条件に一致するアドレスは、データベースクリーンアップ ワークフローによって強制隔離リストから自動的に削除されます。 テクニカルワークフローについて詳しくは、[ この節 ](../../administration/using/technical-workflows.md#list-of-technical-workflows) を参照してください。

次の場合、アドレスは強制隔離リストから自動的に削除されます。

* **[!UICONTROL Erroneous]** ステータスのアドレスは、配信が成功した後に強制隔離リストから削除されます。
* 前回のソフトバウンスが 10 日以上前に発生した場合、**[!UICONTROL Erroneous]** ステータスのアドレスは強制隔離リストから削除されます。 ソフトエラー管理について詳しくは、[この節](#soft-error-management)を参照してください。
* **[!UICONTROL Mailbox full]** エラーでバウンスした **[!UICONTROL Erroneous]** ステータスのアドレスは、30 日後に強制隔離リストから削除されます。

その後、ステータスは **[!UICONTROL Valid]** に変わります。

ステータスが **[!UICONTROL Erroneous]** の場合に実行される再試行の最大数と再試行間の最小遅延は、現在、IP が特定のドメインで過去と現在の両方でどの程度機能しているかに基づいています。


>[!IMPORTANT]
>
>アドレスのステータスが **[!UICONTROL Quarantine]** または **[!UICONTROL Denylisted]** の受信者は、メールを受信した場合でも削除されません。


### 手動更新 {#unquarantine-manual}

アドレスの強制隔離を手動で解除することもできます。  強制隔離リストからアドレスを手動で削除するには、強制隔離リストからアドレスを削除するか、ステータスを **[!UICONTROL Valid]** に変更します。

* **[!UICONTROL Administration > Channels > Quarantines > Addresses]** リストからアドレスを選択し、「**[!UICONTROL Delete element]**」を選択します。

  ![](assets/quarantine-delete-address.png)

* アドレスを選択し、その **[!UICONTROL Status]** を **[!UICONTROL Valid]** に変更します。

  ![](assets/quarantine-valid-status.png)


### 一括更新 {#unquarantine-bulk}

例えば、ISP が停止した場合など、強制隔離リストで一括更新を実行する必要が生じる場合があります。 この場合、メールは受信者に正常に配信されないため、誤ってバウンスとマークされます。強制隔離リストからこれらのアドレスを削除する必要があります。

これを実行するには、ワークフローを作成し、強制隔離テーブルに **[!UICONTROL Query]** アクティビティを追加して、影響を受けたすべての受信者を除外します。 特定されると、それらは強制隔離リストから削除され、今後のキャンペーンメール配信に含めることができます。

インシデントの期間に基づいて、このクエリの推奨ガイドラインを以下に示します。

* **エラーテキスト（強制隔離テキスト）**&#x200B;には、「550-5.1.1」が含まれ、かつ&#x200B;**エラーテキスト（強制隔離テキスト）**&#x200B;には、「support.ISP.com」が含まれている

  例えば、「support.ISP.com」は「support.apple.com」または「support.google.com」になります

* **更新ステータス（@lastModified）**&#x200B;が `MM/DD/YYYY HH:MM:SS AM` 以降
* **更新ステータス（@lastModified）**&#x200B;が `MM/DD/YYYY HH:MM:SS PM` 以前

影響を受ける受信者のリストを受信したら、**[!UICONTROL Update data]** アクティビティを追加して、メール アドレスのステータスを **[!UICONTROL Valid]** に設定し、**[!UICONTROL Database cleanup]** ワークフローで強制隔離リストから削除されるようにします。 また、強制隔離テーブルから削除するだけでもかまいません。

## アドレスを強制隔離に送信するための条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign は、エラーメッセージの選定時に割り当てられた配信エラーのタイプと理由に従って強制隔離を管理します（[配信エラーのタイプと理由](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)および[バウンスメールの選定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)を参照）。

* **無視のエラー**：アドレスを強制隔離しません。
* **ハードエラー**：対応するメールアドレスがただちに強制隔離されます。
* **ソフトエラー**：ただちにアドレスが強制隔離されることはありませんが、エラーカウンターがインクリメントされます。詳しくは、[ソフトエラー管理](#soft-error-management)を参照してください。

  <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

ユーザーがメールをスパム（[フィードバックループ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#feedback-loops)）と見なした場合、メッセージは、アドビが管理するテクニカルメールボックスに自動的にリダイレクトされます。さらに、そのメールアドレスは自動的に強制隔離され、ステータスが「**[!UICONTROL On denylist]**」となります。このステータスはアドレスのみに適用され、プロファイルはブロックリストに登録されていないので、ユーザーは引き続き SMS メッセージやプッシュ通知を受信します。

>[!NOTE]
>
>Adobe Campaign の強制隔離では、大文字と小文字が区別されます。後から再度ターゲットされることのないよう、メールアドレスは必ず小文字でインポートしてください。

隔離されたアドレスのリスト（[プラットフォーム全体の強制隔離されたアドレスの識別](#identifying-quarantined-addresses-for-the-entire-platform)を参照）の「**[!UICONTROL Error reason]**」フィールドは、選択したアドレスが強制隔離された理由を示します。

![](assets/quarantines2.png)

### ソフトエラー管理 {#soft-error-management}

ハードエラーとは異なり、ソフトエラーでただちにアドレスが強制隔離されることはありませんが、エラーカウンターがインクリメントされます。

再試行は、[配信期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)中に実行されます。エラーカウンターが制限しきい値に達すると、アドレスが強制隔離されます。詳しくは、[一時的な配信エラーの後の再試行](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

最後に重大なエラーが発生したのが 10 日以上前の場合、エラーカウンターが再初期化されます。その後、アドレスのステータスは **有効** に変わり、**データベースクリーンアップ** ワークフローによって強制隔離のリストから削除されます。 （テクニカルワークフローについて詳しくは、[ この節 ](../../administration/using/technical-workflows.md#list-of-technical-workflows) を参照してください）。
