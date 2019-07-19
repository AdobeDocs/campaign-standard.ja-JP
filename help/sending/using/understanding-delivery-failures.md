---
title: 配信エラーについて
seo-title: 配信エラーについて
description: 配信エラーについて
seo-description: キャンペーンで配信エラーを管理する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 2735aa05-7b6f-47c9-98c4- a15cc33be39d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: 38452841-4cd4-4f92- a5c3-1fddd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Understanding delivery failures{#understanding-delivery-failures}

## About delivery failures {#about-delivery-failures}

配信をプロファイルに送信できない場合、リモートサーバーは自動的にエラーメッセージを送信します。エラーメッセージは、Adobe Campaignプラットフォームによって取得され、電子メールアドレスまたは電話番号が隔離されるかどうかを判断するために使用されます。[バウンスメールの資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)情報を参照してください。

>[!NOTE]
>
>**電子メール** エラーメッセージ（またはバウンス）は、InMailプロセスによって修飾されます。**SMS** エラーメッセージ（「ステータスレポート」の"SR"）は、MTAプロセスによって修飾されます。

また、アドレスが隔離された場合や、プロファイルがブラックリストに記載されている場合、配信準備中にメッセージを除外することもできます。Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**関連トピック:**

* [強制隔離について](../../sending/using/understanding-quarantine-management.md)
* [キャンペーンでのブラックリストの管理](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifying delivery failures for a message {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

あらかじめ用意されている専用レポートも利用できます。このレポートでは、配信中に発生する全体的なハードおよびソフトエラーおよびバウンスの自動処理について説明します。For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Delivery failure types and reasons {#delivery-failure-types-and-reasons}

配信に失敗すると、次の3つのタイプのエラーが発生します。

* **ハード**:「ハード」エラーは、無効なアドレスを示しています。これには、次のようにアドレスが無効であることを明示的に示すエラーメッセージが含まれます。「不明なユーザー」。
* **ソフト**:これは一時的なエラーであるか、分類できなかった次のような分類になります。「無効なドメイン」または「メールボックスの空き容量」。
* **無視**:これは、「不在」、または送信者のタイプが"postmaster"の場合など、一時的なエラーであることがわかっているエラーです。

配信エラーの考えられる理由は次のとおりです。

* **[!UICONTROL User unknown]** （ハードタイプ）:アドレスが存在しません。このプロファイルの配信は試行されません。
* **[!UICONTROL Quarantined address]** （ハードタイプ）:住所が強制隔離されました。
* **[!UICONTROL Unreachable]** （Soft/Hard type）:メッセージ配信チェーンでエラーが発生しました（SMTPリレーのインシデント、一時的にアクセスできないドメインなど）。プロバイダーから返されたエラーにより、アドレスは直接隔離に送信されるか、配信が再試行されます。このエラーは、強制隔離のステータスを正当化するエラーを受信するか、またはエラーの数が5に達するまで再度試行されます。
* **[!UICONTROL Address empty]** （ハードタイプ）:アドレスが定義されていません。
* **[!UICONTROL Mailbox full]** （ソフトタイプ）:このユーザーのメールボックスはいっぱいで、より多くのメッセージを受け入れることはできません。このアドレスは強制隔離リストから削除して、別の試みを行うことができます。30日後に自動的に削除されます。

   強制隔離されたアドレスのリストからアドレスを自動的に削除するには、**[!UICONTROL Database cleanup]** テクニカルワークフローを開始する必要があります。

* **[!UICONTROL Refused]** （Soft/Hard type）:セキュリティフィードバックがスパムレポートとして使用されているため、住所が強制隔離されました。プロバイダーから返されたエラーにより、アドレスは直接隔離に送信されるか、配信が再試行されます。このエラーは、強制隔離のステータスを正当化するエラーを受信するか、またはエラーの数が5に達するまで再度試行されます。
* **[!UICONTROL Duplicate]**:セグメントで既にアドレスが検出されています。
* **[!UICONTROL Not defined]** （ソフトタイプ）:エラーがまだ増分されていないので、アドレスは選定中です。

   このタイプのエラーは、サーバーから新しいエラーメッセージが送信されたときに発生します。は個別のエラーになる可能性がありますが、再度発生すると、エラーカウンターが増加し、技術チームに警告します。

* **[!UICONTROL Error ignored]**:アドレスがホワイトリストに格納され、任意のケースで電子メールが送信されます。
* **[!UICONTROL Blacklisted address]**:送信時にアドレスがブラックリストに記載されています。
* **[!UICONTROL Account disabled]** （Soft/Hard type）:インターネットアクセスプロバイダ（IAP）では、無操作状態が長い時間を検知すると、ユーザーのアカウントを閉じることができます。ユーザーのアドレスへの配信は不可能になります。The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. 受け取ったエラーによってアカウントが完全に非アクティブ化された場合は、直接強制隔離に送信されます。
* **[!UICONTROL Not connected]**:メッセージの送信時にプロファイルの携帯電話がオフになっているか、ネットワークに接続されていません。
* **[!UICONTROL Invalid domain]** （ソフトタイプ）:電子メールアドレスのドメインが正しくないか、存在しません。このプロファイルは、エラー数が5に達するまで再度ターゲットになります。この後、レコードは強制的に隔離ステータスに設定され、再試行は行われません。
* **[!UICONTROL Text too long]**:SMSメッセージ内の文字数が制限を超えています。For more on this, see [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**:SMSメッセージには、エンコードでサポートされていない1文字以上の文字が含まれています。&amp;For more on this, see [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Retries after a delivery temporary failure {#retries-after-a-delivery-temporary-failure}

**無視** 型の一時エラーが原因でメッセージが失敗した場合、配信期間中に再試行が実行されます。For more on the types of errors, see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

配信の期間を変更するには、配信または配信テンプレートのアドバンスパラメーターに移動し、対応するフィールドで目的の期間を指定します。The advanced delivery properties are presented in [this section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

デフォルトの設定では、1時間間隔で5回再試行し、4日間に1回再試行することができます。The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

配信は、送信された後（非同期エラー）、即座に失敗することがあります（同期エラー）。

* **同期エラー**:Adobe Campaign配信サーバーから連絡されたリモートサーバーがエラーメッセージを即座に返し、その配信はプロファイルのサーバーに送信できません。
* **非同期エラー**:バウンスメールまたはSRが受信サーバーから後で再送されました。非同期エラーは、配信が送信されてから1週間後に発生する可能性があります。

## Bounce mail qualification {#bounce-mail-qualification}

配信失敗エラーメッセージ（またはバウンス）はAdobe Campaignプラットフォームによって取得され、InMailプロセスによって修飾され、電子メール管理ルールのリストを充実させます。

このリストは管理者のみが使用でき、Adobe Campaignで使用されるすべてのルールを含み、配信エラーを確認できます。

To access it, click the **[!UICONTROL Adobe Campaign]** logo, at the top left, then select **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

バウンスには次の資格ステータスを含めることができます。

* **[!UICONTROL To qualify]**:バウンスメールは資格を満たす必要があります。資格設定は、プラットフォームの配信品質が正しく機能するために、配信品質チームが行う必要があります。資格がない限り、バウンスメールは電子メール処理ルールのリストを充実させるためには使用されません。
* **[!UICONTROL Keep]**:バウンスメールは資格があり、既存の電子メール処理ルールと比較してリストを充実させるために **、配信品質** ワークフローで使用されます。
* **[!UICONTROL Ignore]**:バウンスメールは資格を受けましたが、配信品質 **** ワークフローでの更新では使用されません。そのため、クライアントインスタンスに送信されません。

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Optimizing mail deliverability with double opt-in mechanism {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

電子メールを送信する際には、ダブルオプトインメカニズムがベストプラクティスです。これにより、プラットフォームを不正または無効な電子メールアドレスやスパムから保護し、スパムの苦情を防止できます。

訪問者の同意をキャンペーンデータベースに保存する前に、電子メールを送信して、訪問者の契約書を確認します。訪問者はオンラインランディングページに入力してから電子メールを受け取り、確認リンクをクリックして購読を終了する必要があります。

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
