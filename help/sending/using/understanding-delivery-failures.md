---
title: 配信エラーの理解
description: キャンペーンを使用して、配信障害を管理する方法
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c1287a360cdd1750996b47a27b85a11e90b29df0

---


# 配信エラーの理解{#understanding-delivery-failures}

## 配信エラーについて {#about-delivery-failures}

配信をプロファイルに送信できない場合、リモートサーバーはエラーメッセージを自動的に送信します。このメッセージはAdobe Campaignプラットフォームによって取得され、電子メールアドレスまたは電話番号を隔離する必要があるかどうかを判断します。 [バウンスメールの選定](#bounce-mail-qualification)を参照してください。

>[!NOTE]
>
>**電子メール** エラーメッセージ（「バウンス」）は、拡張MTA（同期バウンス）またはinMailプロセス（非同期バウンス）で修飾されます。
>
>**SMS エラーメッセージ（ステータスレポートを表す「SR」）は MTA プロセスによって評価されます。**

アドレスが強制隔離されているか、プロファイルがブラックリストに登録されている場合、配信準備の際にメッセージを除外することもできます。除外されたメッセージは、配信 **[!UICONTROL Exclusion logs]** ダッシュボードのタブに表示さ [れます](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

![](assets/exclusion_logs.png)

**関連トピック：**

* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [ブラックリストの管理キャンペーン](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## メッセージの配信エラーの識別 {#identifying-delivery-failures-for-a-message}

配信が送信されると、タブ **[!UICONTROL Sending logs]** (この節を参 [照](../../sending/using/monitoring-a-delivery.md#sending-logs))で各プロファイルの配信ステータスと、関連する障害のタイプと理由( [配信の障害のタイプと理由を参照](#delivery-failure-types-and-reasons))を表示できます。

![](assets/sending_logs.png)

すぐに使用できる専用のレポートも利用できます。 このレポートは、バウンス中に発生したハードエラーとソフトエラーの全体配信と、バウンスの自動処理の詳細を示します。 詳しくは、[この節](../../reporting/using/bounce-summary.md)を参照してください。

## 配信エラーのタイプと理由 {#delivery-failure-types-and-reasons}

エラーが発生した場合、次の3種類の配信があります。

* **ハード**：「ハード」エラーは無効なアドレスの存在を示します。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。
* **ソフト**：これは一時的なエラーか、「無効なドメイン」または「メールボックス容量超過」など、分類が不可能なエラーです。
* **無視**：これは、「外出中」など一時的であることがわかっているエラーまたは送信者タイプが「postmaster」である場合などの技術的エラーです。

配信エラーの理由として考えられるものを以下に示します。

* **[!UICONTROL User unknown]** （ハードタイプ）:アドレスが存在しません。 このプロファイルに対する配信はこれ以上試行されません。
* **[!UICONTROL Quarantined address]** （ハードタイプ）:住所は強制隔離。
* **[!UICONTROL Unreachable]** （ソフト/ハードタイプ）:メッセージ配信チェーン(ドメインの一時的な未到達など)でエラーが発生しました。 プロバイダーから返されたエラーに応じて、アドレスが強制隔離に直接送信されるか、キャンペーンが強制隔離ステータスを正当化するエラーを受け取るか、エラー数が5に達するまで、配信が再試行されます。
* **[!UICONTROL Address empty]** （ハードタイプ）:アドレスが定義されていません。
* **[!UICONTROL Mailbox full]** （ソフトタイプ）:このユーザーのメールボックスはいっぱいで、これ以上メッセージを受け付けることができません。 このアドレスを強制隔離リストから削除して、再度試行できます。アドレスは、30 日後に自動的に削除されます。

   強制隔離されたアドレスのリストからアドレスを自動的に削除するには、**[!UICONTROL Database cleanup]** テクニカルワークフローを開始する必要があります。

* **[!UICONTROL Refused]** （ソフト/ハードタイプ）:この住所は、スパムレポートとしてのセキュリティ強制隔離により、に配置されました。 プロバイダーから返されたエラーに応じて、アドレスが強制隔離に直接送信されるか、キャンペーンが強制隔離ステータスを正当化するエラーを受け取るか、エラー数が5に達するまで、配信が再試行されます。
* **[!UICONTROL Duplicate]**:このアドレスは既にセグメントで検出されています。
* **[!UICONTROL Not defined]** （ソフトタイプ）:エラーがまだ増加していないので、アドレスは認定されます。

   このタイプのエラーは、サーバーが新しいエラーメッセージを送信すると発生します。単独のエラーである可能性もありますが、再度発生した場合はエラーカウンターがインクリメントされ、テクニカルチームに警告されます。

* **[!UICONTROL Error ignored]**:このアドレスはホワイトリストに含まれており、どのような場合でも電子メールが送信されます。
* **[!UICONTROL Blacklisted address]**:住所は送信時のブラックリスト登録済みでした。
* **[!UICONTROL Account disabled]** （ソフト/ハードタイプ）:インターネットアクセスプロバイダ(IAP)は、長時間の無操作状態を検出した場合、ユーザーのアカウントを閉じることができます。配信のアドレスへのアクセスは不可能になります。 「ソフト」(Soft)または「ハード」(Hard)タイプは、受け取ったエラーのタイプに応じて異なります。6か月間操作が行われなかったためにアカウントが一時的に無効になっている場合でも、アクティブ化できると、ステータスが割り当て **[!UICONTROL Erroneous]** られ、配信が再試行されます。 アカウントが恒久的に非アクティブ化されるというエラーが表示された場合は、そのアカウントが直接強制隔離に送信されます。
* **[!UICONTROL Not connected]**:プロファイルの携帯電話は、メッセージの送信時にオフになるか、ネットワークに接続されません。
* **[!UICONTROL Invalid domain]** （ソフトタイプ）:電子メールアドレスのドメインが正しくないか、存在しません。 このプロファイルは、エラーカウントが 5 にならない限り、再びターゲットになります。その後、レコードは強制隔離ステータスに設定され、以降は再試行されなくなります。
* **[!UICONTROL Text too long]**:smsメッセージの文字数が制限を超えています。 詳しくは、 [SMSのエンコーディング、長さ、読み込みを参照してください](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。
* **[!UICONTROL Character not supported by encoding]**:smsメッセージに、エンコーディングでサポートされていない1つ以上の文字が含まれています。 詳しくは、「文字表 — GSM標準」を [参照してください](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。

## 一時的な配信エラーの後の再試行 {#retries-after-a-delivery-temporary-failure}

無視タイプの一時的なエラーが原因でメッセージが失敗し **た場合** 、再試行期間中に配信が実行されます。 エラーのタイプについて詳しくは、「 [配信エラーのタイプと理由](#delivery-failure-types-and-reasons)」を参照してください。

再試行の数(送信開始後の1日に実行する再試行の数)と再試行間の最小遅延は、IPが特定のドメインでどの程度過去に実行され、現在どの程度のパフォーマンスを示しているかに基づいて、Adobe Campaign拡張MTAで管理されるようになりました。 **再試行** 設定は無視されます。

配信の期間を変更するには、配信または配信テンプレートの詳細パラメーターに移動し、「有効期間」セクシ **[!UICONTROL Delivery duration]** ョンのフィールド [を編集し](../../administration/using/configuring-email-channel.md#validity-period-parameters) ます。

>[!IMPORTANT]
>
>**キャンペーン&#x200B;**[!UICONTROL Delivery duration]**配信内のパラメーターは、3.5日以下に設定した場合にのみ使用されるようになりました。** 3.5日を超える値を定義した場合、この値はAdobe Campaign拡張MTAで管理されるようになったので、考慮されません。

例えば、配信の再試行を1日後に停止する場合、配信期間を **1d**&#x200B;に設定すると、拡張MTAは1日後に再試行キュー内のメッセージを削除することで、この設定を受け入れます。

>[!NOTE]
>
>メッセージが3.5日間拡張MTAキューに入り、配信に失敗すると、タイムアウトになり、配信ログのからにステータスが更新さ **[!UICONTROL Sent]****[!UICONTROL Failed]** れ [ます](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同期エラーと非同期エラー {#synchronous-and-asynchronous-errors}

配信は、送信後すぐに（同期エラー）失敗するか、後で（非同期エラー）失敗する可能性があります。

* **同期エラー**:Adobe Campaign配信サーバーから接続されたリモートサーバーは直ちにエラーメッセージを返し、配信をプロファイルのサーバーに送信することは許可されていません。
* **非同期エラー**:バウンスメールまたはSRが、受信サーバによって後で再送信された。 非同期エラーは、配信の送信から 1 週間が経過するまで発生する可能性があります。

## バウンスメール強制隔離 {#bounce-mail-qualification}

同期配信障害のエラーメッセージの場合、拡張MTAはバウンスのタイプと条件を決定し、その情報をキャンペーンに返します。

非同期バウンスは、inMailプロセスでもルールを通じて認定さ **[!UICONTROL Inbound email]** れます。 これらのルールにアクセスするに **[!UICONTROL Adobe Campaign]** は、左上のロゴをクリックし、を選択 **[!UICONTROL Administration > Channels > Email > Email processing rules]** して選択しま **[!UICONTROL Bounce mails]**&#x200B;す。 For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>バウンスのメールの資格は、拡張MTAAdobe Campaignで管理されました。 キャンペーンテーブルの直帰 **[!UICONTROL Message qualification]** 条件は使用されなくなりました。

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 重複オプトインメカニズムによるメール配信品質の最適化 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

重複のオプトインメカニズムは、電子メールを送信する際のベストプラクティスです。 これは、間違ったまたは無効な電子メールアドレスやスパンボットからプラットフォームを保護し、迷惑メールの可能性を防ぎます。

原則として、訪問者の契約を確認する電子メールを送信し、「プロファイル」としてキャンペーンデータベースに保存します。訪問者がオンラインランディングページを入力し、電子メールを受信したら、確認リンクをクリックして購読を確定する必要があります。

詳しくは、[この節](../../channels/using/setting-up-a-double-opt-in-process.md)を参照してください。
