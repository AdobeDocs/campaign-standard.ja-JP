---
title: 配信エラーの理解
description: Campaignを使用して配信エラーを管理する方法を説明します。
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
source-git-commit: bee7ea0f1728da2a96c1f225b91b13a7903be660

---


# 配信エラーの理解{#understanding-delivery-failures}

## 配信エラーについて {#about-delivery-failures}

配信がプロファイルに送信できない場合、リモートサーバーはエラーメッセージを自動的に送信します。このメッセージは、Adobe Campaignプラットフォームによって取得され、電子メールアドレスまたは電話番号を検疫するかどうかを判断する資格があります。 「バウンス [メールの資格](#bounce-mail-qualification)」を参照。

>[!NOTE]
>
>**E メールメッセージ（「バウンス」）は inMail プロセスによって評価されます。****SMS エラーメッセージ（ステータスレポートを表す「SR」）は MTA プロセスによって評価されます。**

アドレスが強制隔離されているか、プロファイルがブラックリストに登録されている場合、配信準備の際にメッセージを除外することもできます。除外されたメッセージは、配信ダッシュボ **[!UICONTROL Exclusion logs]** ードのタブに表示されます(こ [の節を参照](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。

![](assets/exclusion_logs.png)

**関連トピック：**

* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [キャンペーンでのブラックリストの管理](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## メッセージの配信エラーの識別 {#identifying-delivery-failures-for-a-message}

配信が送信されると、タブ **[!UICONTROL Sending logs]** (この節を参 [照](../../sending/using/monitoring-a-delivery.md#sending-logs))では、各プロファイルの配信ステータスと、関連する失敗タイプおよび理由(配信失敗タイプおよび理由を [参照](#delivery-failure-types-and-reasons))を表示できます。

![](assets/sending_logs.png)

すぐに使用できる専用のレポートも利用できます。 このレポートは、配信中に発生したハードエラーとソフトエラーの全体と、バウンスの自動処理の詳細を示します。 詳しくは、[この節](../../reporting/using/bounce-summary.md)を参照してください。

## 配信エラーのタイプと理由 {#delivery-failure-types-and-reasons}

配信に失敗した場合、次の3種類のエラーが発生します。

* **ハード**:「ハード」エラーは、無効なアドレスを示します。 これには、次のような、アドレスが無効であることを明示的に示すエラーメッセージが含まれます。&quot;不明なユーザー&quot;。
* **ソフト**:これは一時的なエラー、または分類できなかった次のようなエラーである可能性があります。&quot;無効なドメイン&quot;または&quot;メールボックスがいっぱい&quot;です。
* **無視**:これは、「不在」や技術的なエラーなど、一時的なエラーであることがわかっているエラーです。例えば、送信者のタイプが「ポストマスター」の場合などです。

配信エラーの理由として考えられるものを以下に示します。

* **[!UICONTROL User unknown]** （ハードタイプ）:アドレスが存在しません。 このプロファイルに対する配信はこれ以上試行されません。
* **[!UICONTROL Quarantined address]** （ハードタイプ）:住所が検疫に付された。
* **[!UICONTROL Unreachable]** （ソフト/ハードタイプ）:メッセージ配信チェーンでエラーが発生しました（ドメインが一時的に到達不能な場合など）。 プロバイダーから返されたエラーによると、アドレスは検疫に直接送信されるか、または配信は、検疫ステータスを正当化するエラーがキャンペーンで受信されるか、エラー数が5に達するまで再試行されます。
* **[!UICONTROL Address empty]** （ハードタイプ）:アドレスが定義されていません。
* **[!UICONTROL Mailbox full]** （ソフトタイプ）:このユーザーのメールボックスはいっぱいで、これ以上メッセージを受け付けることができません。 このアドレスを強制隔離リストから削除して、再度試行できます。アドレスは、30 日後に自動的に削除されます。

   強制隔離されたアドレスのリストからアドレスを自動的に削除するには、**[!UICONTROL Database cleanup]** テクニカルワークフローを開始する必要があります。

* **[!UICONTROL Refused]** （ソフト/ハードタイプ）:このアドレスは、スパムレポートとしてのセキュリティフィードバックにより、検疫に含まれています。 プロバイダーから返されたエラーによると、アドレスは検疫に直接送信されるか、または配信は、検疫ステータスを正当化するエラーがキャンペーンで受信されるか、エラー数が5に達するまで再試行されます。
* **[!UICONTROL Duplicate]**:このアドレスは既にセグメントで検出されています。
* **[!UICONTROL Not defined]** （ソフトタイプ）:エラーがまだ増加していないので、アドレスは認定されます。

   このタイプのエラーは、サーバーが新しいエラーメッセージを送信すると発生します。単独のエラーである可能性もありますが、再度発生した場合はエラーカウンターがインクリメントされ、テクニカルチームに警告されます。

* **[!UICONTROL Error ignored]**:このアドレスはホワイトリストに含まれており、どのような場合でも電子メールが送信されます。
* **[!UICONTROL Blacklisted address]**:送信時に住所がブラックリストに載っていた
* **[!UICONTROL Account disabled]** （ソフト/ハードタイプ）:インターネットアクセスプロバイダ(IAP)は、長時間の無操作状態を検出した場合、ユーザーのアカウントを閉じることができます。その後、ユーザーの住所に配信することはできません。 「ソフト」(Soft)または「ハード」(Hard)タイプは、受け取ったエラーのタイプに応じて異なります。6か月間操作が行われなかったためにアカウントが一時的に無効になっている場合でも、アクティブ化できると、ステータスが割り当て **[!UICONTROL Erroneous]** られ、配信が再試行されます。 このアカウントが恒久的に非アクティブ化されていることを示すエラーが表示された場合は、直接検疫に送信されます。
* **[!UICONTROL Not connected]**:メッセージの送信時に、プロファイルの携帯電話がオフになるか、ネットワークに接続されません。
* **[!UICONTROL Invalid domain]** （ソフトタイプ）:電子メールアドレスのドメインが正しくないか、存在しません。 このプロファイルは、エラーカウントが 5 にならない限り、再びターゲットになります。その後、レコードは強制隔離ステータスに設定され、以降は再試行されなくなります。
* **[!UICONTROL Text too long]**:smsメッセージの文字数が制限を超えています。 詳しくは、 [SMSのエンコーディング、長さ、読み込みを参照してください](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。
* **[!UICONTROL Character not supported by encoding]**:smsメッセージに、エンコーディングでサポートされていない1つ以上の文字が含まれています。 詳しくは、「文字表 — GSM標準」を [参照してください](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。

## 一時的な配信エラーの後の再試行 {#retries-after-a-delivery-temporary-failure}

「 **Ignored** 」タイプの一時的なエラーが原因でメッセージが失敗した場合は、配信中に再試行が実行されます。 エラーのタイプについて詳しくは、「配信エラーのタ [イプと理由」を参照してください](#delivery-failure-types-and-reasons)。

配信の期間を変更するには、配信の高度なパラメーターまたは配信テンプレートにアクセスし、対応するフィールドで希望の期間を指定します。高度な配信プロパティについては、[この節](../../administration/using/configuring-email-channel.md#validity-period-parameters)で説明しています。

デフォルトの設定では、1 時間間隔で 5 回、その後 4 日間は 1 日に 1 回再試行されます。再試行の回数の変更は、グローバルに（アドビの技術管理者にお問い合わせください）、または配信または配信テンプレートごとに（[この節](../../administration/using/configuring-email-channel.md#sending-parameters)を参照）おこなうことができます。

## 同期エラーと非同期エラー {#synchronous-and-asynchronous-errors}

配信は、送信後すぐに（同期エラー）失敗するか、後で（非同期エラー）失敗する可能性があります。

* **同期エラー**:adobe Campaign配信サーバーが接続したリモートサーバーが直ちにエラーメッセージを返した場合、その配信はプロファイルのサーバーに送信できません。
* **非同期エラー**:バウンスメールまたはSRが、受信サーバによって後で再送信された。 非同期エラーは、配信の送信から 1 週間が経過するまで発生する可能性があります。

## バウンスメール強制隔離 {#bounce-mail-qualification}

<!--Delivery failure error messages (or "SMTP bounce responses") are picked up by the Adobe Campaign platform and then processed and qualified as **Hard**, **Soft**, or **Ignored** using the **[!UICONTROL Delivery log qualification]** database.

//Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)

This list is available to administrators only and contains all the rules used by Adobe Campaign to qualify delivery failures.-->

>[!IMPORTANT]
>
>拡張MTAにアップグレードすると、キャンペーン表のバウンス **[!UICONTROL Message qualification]** 条件は使用されなくなります。

同期配信の失敗エラーメッセージの場合、拡張MTAはバウンスのタイプと資格を決定し、その情報をCampaignに返します。 Adobe Campaign拡張MTAについて詳しくは、このドキュメントを参照してく [ださい](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)。

非同期バウンスは、inMailプロセスでもルールを通じて認定さ **[!UICONTROL Inbound email]** れます。 これらのルールにアクセスするに **[!UICONTROL Adobe Campaign]** は、左上のロゴをクリックし、を選択 **[!UICONTROL Administration > Channels > Email > Email processing rules]** して選択しま **[!UICONTROL Bounce mails]**&#x200B;す。 For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## ダブルオプトインメカニズムによるメール配信品質の最適化 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

電子メールを送信する際のベストプラクティスは、ダブルオプトインメカニズムです。 これは、間違ったまたは無効な電子メールアドレスやスパンボットからプラットフォームを保護し、迷惑メールの可能性を防ぎます。

原則として、訪問者の契約を確認する電子メールを送信してから、「プロファイル」としてCampaignデータベースに保存します。訪問者がオンラインランディングページに入力し、電子メールを受信したら、確認リンクをクリックして購読を終了する必要があります。

詳しくは、[この節](../../channels/using/setting-up-a-double-opt-in-process.md)を参照してください。
