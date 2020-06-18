---
title: 配信エラーの理解
description: キャンペーンを使用して配信エラーを管理する方法を説明します。
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
source-git-commit: ecb57ccc4cafa609f7ddccb5f934aa3ab2368dde
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 27%

---


# 配信エラーの理解{#understanding-delivery-failures}

## 配信エラーについて {#about-delivery-failures}

配信をプロファイルに送信できない場合、リモートサーバーは自動的にエラーメッセージを送信します。エラーメッセージはAdobe Campaignプラットフォームによって取得され、電子メールアドレスまたは電話番号を隔離する必要があるかどうかを判断します。 [バウンスメールの選定](#bounce-mail-qualification)を参照してください。

>[!NOTE]
>
>**電子メール** エラーメッセージ（「バウンス」）は、拡張MTA（同期バウンス）またはinMailプロセス（非同期バウンス）で修飾されます。
>
>**SMS エラーメッセージ（ステータスレポートを表す「SR」）は MTA プロセスによって評価されます。**

アドレスが隔離された場合やブロックリスト上にプロファイルがある場合は、配信の準備中にメッセージを除外することもできます。 除外されたメッセージは、配信ダッシュボードの **[!UICONTROL Exclusion logs]** タブに表示されます( [この節を参照](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。

![](assets/exclusion_logs.png)

**関連トピック：**

* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## メッセージの配信エラーの識別 {#identifying-delivery-failures-for-a-message}

配信が送信されると、 **[!UICONTROL Sending logs]** タブ( [この節を参照](../../sending/using/monitoring-a-delivery.md#sending-logs))では、各プロファイルの配信ステータスと、関連する失敗タイプおよび理由( [配信の失敗タイプおよび理由を参照](#delivery-failure-types-and-reasons))を表示できます。

![](assets/sending_logs.png)

そのまま使用できる専用のレポートも用意されています。 このレポートは、配信中に発生したハードエラーとソフトエラーの全体、およびバウンスの自動処理の詳細を示します。 詳しくは、[この節](../../reporting/using/bounce-summary.md)を参照してください。

## 配信エラーのタイプと理由 {#delivery-failure-types-and-reasons}

配信が失敗した場合、次の3種類のエラーが発生します。

* **ハード**：「ハード」エラーは無効なアドレスの存在を示します。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。
* **ソフト**：これは一時的なエラーか、「無効なドメイン」または「メールボックス容量超過」など、分類が不可能なエラーです。
* **無視**：これは、「外出中」など一時的であることがわかっているエラーまたは送信者タイプが「postmaster」である場合などの技術的エラーです。

配信エラーの理由として考えられるものを以下に示します。

| エラーラベル | エラータイプ | 説明 |
---------|----------|---------
| **[!UICONTROL User unknown]** | ハード | アドレスが存在しません。このプロファイルに対する配信はこれ以上試行されません。 |
| **[!UICONTROL Quarantined address]** | ハード | アドレスは強制隔離されました。 |
| **[!UICONTROL Unreachable]** | ソフト／ハード | メッセージ配信チェーン(ドメインの一時未到達など)でエラーが発生しました。 プロバイダーから返されたエラーに応じて、アドレスは強制隔離に直接送信されるか、配信はキャンペーンが強制隔離ステータスを正当化するエラーを受け取るか、エラー数が5に達するまで再試行されます。 |
| **[!UICONTROL Address empty]** | ハード | アドレスが定義されていません。 |
| **[!UICONTROL Mailbox full]** | ソフト | このユーザーのメールボックスはいっぱいになっていて、メッセージをこれ以上受け入れることができません。このアドレスを強制隔離リストから削除して、再度試行できます。アドレスは、30 日後に自動的に削除されます。強制隔離されたアドレスのリストからアドレスを自動的に削除するには、**[!UICONTROL Database cleanup]** テクニカルワークフローを開始する必要があります。 |
| **[!UICONTROL Refused]** | ソフト／ハード | アドレスは、スパムレポートであるというセキュリティフィードバックが原因で強制隔離されました。プロバイダーから返されたエラーに応じて、アドレスは強制隔離に直接送信されるか、配信はキャンペーンが強制隔離ステータスを正当化するエラーを受け取るか、エラー数が5に達するまで再試行されます。 |
| **[!UICONTROL Duplicate]** | 無視 | アドレスは既にセグメントで検出されています。 |
| **[!UICONTROL Not defined]** | ソフト | エラーはまだ増加していないので、アドレスは認定対象です。 このタイプのエラーは、サーバーが新しいエラーメッセージを送信すると発生します。単独のエラーである可能性もありますが、再度発生した場合はエラーカウンターがインクリメントされ、テクニカルチームに警告されます。 |
| **[!UICONTROL Error ignored]** | 無視 | 許可リストのアドレスには電子メールが送信されます。 |
| **[!UICONTROL Address on block list]** | ハード | 送信時にブロックリストにアドレスが追加されました。 |
| **[!UICONTROL Account disabled]** | ソフト／ハード | インターネットアクセスプロバイダ(IAP)が長時間の無操作状態を検出した場合、ユーザーのアカウントを閉じる可能性があります。 その場合、ユーザーのアドレスへの配信は不可能になります。 「ソフト」(Soft)または「ハード」(Hard)タイプは、受け取ったエラーの種類に応じて異なります。 6か月間操作が行われなかったためにアカウントが一時的に無効になっていて、アクティブ化できる場合は、ステータスが割り当てら **[!UICONTROL Erroneous]** れ、配信が再試行されます。 アカウントが完全に非アクティブ化されるというシグナルを受け取ったエラーは、強制隔離に直接送信されます。 |
| **[!UICONTROL Not connected]** | 無視 | プロファイルの携帯電話は、メッセージの送信時にオフになるか、ネットワークに接続されません。 |
| **[!UICONTROL Invalid domain]** | ソフト | E メールアドレスのドメインが正しくないか、存在しません。このプロファイルは、エラーカウントが 5 にならない限り、再びターゲットになります。その後、レコードは強制隔離ステータスに設定され、以降は再試行されなくなります。 |
| **[!UICONTROL Text too long]** | 無視 | SMSメッセージの文字数が制限を超えています。 詳しくは、「 [SMS encoding, length, and transiteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)」を参照してください。 |
| **[!UICONTROL Character not supported by encoding]** | 無視 | SMSメッセージに、エンコードでサポートされていない1つ以上の文字が含まれています。 詳しくは、「文字 [表 — GSM標準](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)」を参照してください。 |

## 一時的な配信エラーの後の再試行 {#retries-after-a-delivery-temporary-failure}

「 **無視** 」タイプの一時的なエラーが原因でメッセージが失敗した場合は、配信期間中に再試行が実行されます。 エラーの種類について詳しくは、「 [配信エラーの種類と理由](#delivery-failure-types-and-reasons)」を参照してください。

再試行の数(送信開始後の日に実行する再試行の数)と再試行間の最小遅延は、IPが特定のドメインで過去と現在の両方でどの程度実行されているかに基づいて、Adobe Campaign拡張MTAによって管理されるようになりました。 キャンペーンの **再試行** 設定は無視されます。

配信の期間を変更するには、配信または配信テンプレートの高度なパラメーターに移動し、「 **[!UICONTROL Delivery duration]** 有効期間 [](../../administration/using/configuring-email-channel.md#validity-period-parameters) 」セクションのフィールドを編集します。

>[!IMPORTANT]
>
>**キャンペーン配信の&#x200B;**[!UICONTROL Delivery duration]**パラメーターは、3.5日以下に設定した場合にのみ使用されるようになりました。** 3.5日を超える値を定義した場合は、Adobe Campaign拡張MTAによって管理されるようになったので、この値は考慮されません。

例えば、配信の再試行を1日後に停止する場合は、配信期間を **1d**&#x200B;に設定すると、拡張MTAは1日後に再試行キューのメッセージを削除して、この設定を受け入れます。

>[!NOTE]
>
>メッセージが3.5日間拡張MTAキューに入り、配信に失敗した場合、タイムアウトになり、 **[!UICONTROL Sent]** 配信ログ内のからにステータスが更新され **[!UICONTROL Failed]** ます [](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同期エラーと非同期エラー {#synchronous-and-asynchronous-errors}

配信は、送信後すぐに失敗する（同期エラー）か、それ以降に失敗する（非同期エラー）可能性があります。

* **同期エラー**: Adobe Campaign配信サーバーが接続したリモートサーバーは直ちにエラーメッセージを返し、配信をプロファイルのサーバーに送信することは許可されません。
* **非同期エラー**: バウンスメールまたはSRが、後で受信サーバから再送された。 非同期エラーは、配信の送信から 1 週間が経過するまで発生する可能性があります。

## バウンスメール強制隔離 {#bounce-mail-qualification}

同期配信失敗のエラーメッセージの場合、拡張MTAはバウンスのタイプと条件を決定し、その情報をキャンペーンに返します。

Asynchronous bounces are still qualified by the inMail process through the **[!UICONTROL Inbound email]** rules. これらのルールにアクセスするには、左上の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、を選択し **[!UICONTROL Administration > Channels > Email > Email processing rules]** て選択し **[!UICONTROL Bounce mails]**&#x200B;ます。 For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>バウンスメールの資格は、Adobe Campaign拡張MTAで管理されるようになりました。 キャンペーン **[!UICONTROL Message qualification]** 表の直帰の条件は使用されなくなりました。

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 重複オプトインメカニズムによるメール配信品質の最適化 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

重複オプトインメカニズムは、電子メールを送信する際のベストプラクティスです。 これは、プラットフォームを誤ったまたは無効な電子メールアドレスやスパムから保護し、スパムの可能性がある苦情を防ぎます。

原則は、訪問者の契約を確認する電子メールを送信してから、「プロファイル」としてキャンペーンのデータベースに保存することです。 訪問者がオンラインランディングページに入力し、電子メールを受信したら、確認リンクをクリックして購読を終了する必要があります。

詳しくは、[この節](../../channels/using/setting-up-a-double-opt-in-process.md)を参照してください。
