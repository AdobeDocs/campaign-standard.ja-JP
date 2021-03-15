---
solution: Campaign Standard
product: campaign
title: 配信エラーの理解
description: Campaign で配信エラーを管理する方法について説明します。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: 配信品質
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 76%

---


# 配信エラーの理解{#understanding-delivery-failures}

## 配信エラーについて {#about-delivery-failures}

配信をプロファイルに送信できない場合、リモートサーバーは自動的にエラーメッセージを送信します。エラーメッセージは Adobe Campaign プラットフォームによってピックアップされ、その E メールアドレスまたは電話番号を評価して、強制隔離すべきかが判断されます。[バウンスメールの選定](#bounce-mail-qualification)を参照してください。

>[!NOTE]
>
>**E メール**&#x200B;エラーメッセージ（「バウンス」）は、Enhanced MTA（同期バウンス）または inMail プロセス（非同期バウンス）で評価されます。
>
>**SMS** エラーメッセージまたは SR（「ステータスレポート」の意味）は MTA プロセスによって評価されます。

アドレスが隔離された場合やプロファイルが配信上にある場合は、メッセージの準備中にを除外するこブロックリストともできます。 除外されたメッセージは、配信ダッシュボードの「**[!UICONTROL Exclusion logs]**」タブに表示されます（[こちらの節](../../sending/using/monitoring-a-delivery.md#exclusion-logs)を参照）。

![](assets/exclusion_logs.png)

**関連トピック：**

* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## メッセージの配信エラーの識別 {#identifying-delivery-failures-for-a-message}

配信が送られると、「**[!UICONTROL Sending logs]**」タブ（[こちらの節](../../sending/using/monitoring-a-delivery.md#sending-logs)を参照）で、各プロファイルの配信ステータス、関連するエラーのタイプと理由（「[配信エラーのタイプと理由](#delivery-failure-types-and-reasons)」を参照）を確認できます。

![](assets/sending_logs.png)

既製の専用レポートも用意されています。このレポートには、配信中に発生したハードエラーとソフトエラーの全般、およびバウンスの自動処理の詳細が記載されます。詳しくは、[この節](../../reporting/using/bounce-summary.md)を参照してください。

## 配信エラーのタイプと理由 {#delivery-failure-types-and-reasons}

配信が失敗したときのエラーには次の 3 つのタイプがあります。

* **ハード**：「ハード」エラーは無効なアドレスの存在を示します。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。
* **ソフト**：これは一時的なエラーか、「無効なドメイン」または「メールボックス容量超過」など、分類が不可能なエラーです。
* **無視**：これは、「外出中」など一時的であることがわかっているエラーまたは送信者タイプが「postmaster」である場合などの技術的エラーです。

配信エラーの理由として考えられるものを以下に示します。

| エラーラベル | エラータイプ | 説明 |
---------|----------|---------
| **[!UICONTROL User unknown]** | ハード | アドレスが存在しません。このプロファイルに対する配信はこれ以上試行されません。 |
| **[!UICONTROL Quarantined address]** | ハード | アドレスは強制隔離されました。 |
| **[!UICONTROL Unreachable]** | ソフト／ハード | メッセージ配信チェーン(ドメインの一時未到達など)でエラーが発生しました。 プロバイダーから返されるエラーに従い、アドレスは強制隔離に直接送られます。また配信は、強制隔離ステータスが妥当と判断されるエラーを Campaign が受け取るまで、またはエラー件数が 5 に達するまで試行されます。 |
| **[!UICONTROL Address empty]** | ハード | アドレスが定義されていません。 |
| **[!UICONTROL Mailbox full]** | ソフト | このユーザーのメールボックスはいっぱいになっていて、メッセージをこれ以上受け入れることができません。このアドレスを強制隔離リストから削除して、再度試行できます。アドレスは、30 日後に自動的に削除されます。強制隔離されたアドレスのリストからアドレスを自動的に削除するには、**[!UICONTROL Database cleanup]**&#x200B;テクニカルワークフローを開始する必要があります。 |
| **[!UICONTROL Refused]** | ソフト／ハード | アドレスは、スパムレポートであるというセキュリティフィードバックが原因で強制隔離されました。プロバイダーから返されるエラーに従い、アドレスは強制隔離に直接送られます。また配信は、強制隔離ステータスが妥当と判断されるエラーを Campaign が受け取るまで、またはエラー件数が 5 に達するまで試行されます。 |
| **[!UICONTROL Duplicate]** | 無視 | アドレスは既にセグメントで検出されています。 |
| **[!UICONTROL Not defined]** | ソフト | エラーはまだ増加していないので、アドレスは認定対象です。 このタイプのエラーは、サーバーが新しいエラーメッセージを送信すると発生します。単独のエラーである可能性もありますが、再度発生した場合はエラーカウンターがインクリメントされ、テクニカルチームに警告されます。 |
| **[!UICONTROL Error ignored]** | 無視 | アドレスは許可リスト上にあり、場合によっては電子メールが送信されます。 |
| **[!UICONTROL Address on denylist]** | ハード | 送信時にアドレスがブロックリストに追加されました。 |
| **[!UICONTROL Account disabled]** | ソフト／ハード | インターネットアクセスプロバイダ(IAP)が長時間の無操作状態を検出した場合、ユーザーのアカウントを閉じる可能性があります。その場合、ユーザーのアドレスへの配信は不可能になります。 ソフト／ハードタイプは、受け取ったエラーの種類によって異なります。使用されていない期間が 6 ヶ月に達したのでアカウントが一時的に無効になっても、有効化できる場合は、「**[!UICONTROL Erroneous]**」ステータスが割り当てられ、配信が再試行されます。アカウントが永続的に無効化されたことを、受信したエラーが示している場合、アカウントは強制隔離に直接送られます。 |
| **[!UICONTROL Not connected]** | 無視 | プロファイルの携帯電話は、メッセージの送信時にオフになるか、ネットワークに接続されません。 |
| **[!UICONTROL Invalid domain]** | ソフト | E メールアドレスのドメインが正しくないか、存在しません。このプロファイルは、エラーカウントが 5 にならない限り、再びターゲットになります。その後、レコードは強制隔離ステータスに設定され、以降は再試行されなくなります。 |
| **[!UICONTROL Text too long]** | 無視 | SMSメッセージの文字数が制限を超えています。 詳しくは、[SMS のエンコーディング、長さ、表記変換](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)を参照してください。 |
| **[!UICONTROL Character not supported by encoding]** | 無視 | SMSメッセージに、エンコードでサポートされていない1つ以上の文字が含まれています。 詳しくは、[文字の一覧 - GSM 標準](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)を参照してください。 |

## 一時的な配信エラーの後の再試行 {#retries-after-a-delivery-temporary-failure}

「**無視**」のタイプの一時的エラーが原因でメッセージ送信が失敗した場合は、配信期間中に再試行がおこなわれます。エラーのタイプについて詳しくは、[配信エラーのタイプと理由](#delivery-failure-types-and-reasons)を参照してください。

再試行の数(送信が開始された翌日に実行される再試行の数)と、再試行間の最小遅延は、IPが特定のドメインで過去と現在の両方のパフォーマンスをどの程度上回るかに基づいて<!--managed by the Adobe Campaign Enhanced MTA,-->なされます。 Campaign の&#x200B;**再試行**&#x200B;設定は無視されます。

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

配信の期間を変更するには、配信または配信テンプレートの詳細設定パラメーターに移動して、「[Validity period](../../administration/using/configuring-email-channel.md#validity-period-parameters)」セクションの「**[!UICONTROL Delivery duration]**」フィールドを編集します。

>[!IMPORTANT]
>
>**Campaign 配信の「**[!UICONTROL Delivery duration]**」パラメーターは、3.5 日以下に設定した場合にのみ、使用されるようになりました。** 3.5 日を超える値を定義した場合、その値は考慮されません。

例えば、配信の再試行を1日後に停止する場合、配信期間を&#x200B;**1d**&#x200B;に設定すると、再試行キュー内のメッセージは1日後に削除されます。

<!--For example, if you want retries for a delivery to stop after one day, you can set the delivery duration to **1d**, and the Enhanced MTA will honor that setting by removing messages in the retry queue after one day.-->

>[!NOTE]
>
>メッセージが最大3.5日間再試行キューに入り、配信に失敗した場合は、タイムアウトになり、[配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs)の<!--from **[!UICONTROL Sent]**-->から&#x200B;**[!UICONTROL Failed]**&#x200B;にステータスが更新されます。

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同期エラーと非同期エラー {#synchronous-and-asynchronous-errors}

配信は、ただちにエラーになることも（同期エラー）、送信後しばらくしてエラーになることも（非同期エラー）あります。

* **同期エラー**：Adobe Campaign 配信サーバーからアクセスされたリモートサーバーが即座にエラーメッセージを返します。配信をプロファイルのサーバーに送ることは許可されません。
* **非同期エラー**：バウンスメールまたは SR が受信サーバーによって後で再送信された場合です。非同期エラーは、配信の送信から 1 週間が経過するまで発生する可能性があります。

## バウンスメールの選定 {#bounce-mail-qualification}

同期配信障害のエラーメッセージの場合、Message Enhanced MTA(Message Transfer Agent)がバウンスのタイプと条件を決定し、その情報をキャンペーンに返します。

>[!NOTE]
>
>Campaign の&#x200B;**[!UICONTROL Message qualification]**&#x200B;テーブルでのバウンスの選定は使用されなくなりました。

非同期バウンスは、引き続き「**[!UICONTROL Inbound email]**」ルールを通じて、inMail プロセスで選定されます。これらのルールにアクセスするには、左上の **[!UICONTROL Adobe Campaign]** ロゴをクリックしてから、**[!UICONTROL Administration > Channels > Email > Email processing rules]**&#x200B;を選択し、「**[!UICONTROL Bounce mails]**」を選択します。このルールについて詳しくは、[この節](../../administration/using/configuring-email-channel.md#email-processing-rules)を参照してください。

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 重複オプトインメカニズム{#optimizing-mail-deliverability-with-double-opt-in-mechanism}による電子メールの配信品質の最適化

ダブルオプトインは、E メールを送信する際のベストプラクティスです。不正な E メールアアドレスや、無効な E メールアドレス、スパムボットからプラットフォームを保護し、スパムの苦情が報告されないようにします。

ダブルオプトインの原則は、訪問者を「プロファイル」としてキャンペーンのデータベースに保存する前に、E メールを送信して合意を確認することです。オンラインランディングページに入力した訪問者は、受信した E メールの確認リンクをクリックして購読を確定する必要があります。

詳しくは、[この節](../../channels/using/setting-up-a-double-opt-in-process.md)を参照してください。
