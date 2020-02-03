---
title: 配信エラーの理解
description: Campaignで配信エラーを管理する方法を説明します。
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
source-git-commit: 3c45cbbb261f18252689d0fc4f332b9f45137c85

---


# 配信エラーの理解{#understanding-delivery-failures}

## 配信エラーについて {#about-delivery-failures}

配信をプロファイルに送信できない場合、リモートサーバーは自動的にエラーメッセージを送信します。このメッセージは、Adobe Campaignプラットフォームによって取得され、電子メールアドレスまたは電話番号を検疫するかどうかを決定します。 バウンスメ [ールの資格を参照してくださ](#bounce-mail-qualification)い。

>[!NOTE]
>
>**E メールメッセージ（「バウンス」）は inMail プロセスによって評価されます。****SMS エラーメッセージ（ステータスレポートを表す「SR」）は MTA プロセスによって評価されます。**

アドレスが強制隔離されているか、プロファイルがブラックリストに登録されている場合、配信準備の際にメッセージを除外することもできます。除外されたメッセージは、配信ダッシ **[!UICONTROL Exclusion logs]**ュボードのタブに表示されます(こ[の節を参照](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。

![](assets/exclusion_logs.png)

**関連トピック：**

* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [キャンペーンでのブラックリストの管理](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## メッセージの配信エラーの識別 {#identifying-delivery-failures-for-a-message}

配信が送信されると、タブ **[!UICONTROL Sending logs]**(この節を参照[)で各プロファイルの配信ステータスと、関連する失敗タイプおよび理由を表示できます(配信失敗タイプおよび理由](../../sending/using/monitoring-a-delivery.md#sending-logs)を参照[](#delivery-failure-types-and-reasons))。

![](assets/sending_logs.png)

そのまま使用できる専用のレポートも利用できます。 このレポートは、配信中に発生したハードエラーとソフトエラーの全体と、バウンスの自動処理の詳細を示します。 詳しくは、[この節](../../reporting/using/bounce-summary.md)を参照してください。

## 配信エラーのタイプと理由 {#delivery-failure-types-and-reasons}

配信に失敗した場合、次の3種類のエラーが発生します。

* **ハード**:「ハード」エラーは、無効なアドレスを示します。 これには、次のように、アドレスが無効であることを明示的に示すエラーメッセージが含まれます。&quot;不明なユーザー&quot;。
* **ソフト**:これは一時的なエラーであるか、次のように分類できなかった可能性があります。&quot;無効なドメイン&quot;または&quot;メールボックスがいっぱい&quot;です。
* **無視**:これは、「不在」や技術的なエラーなど、一時的なエラーであることがわかっているエラーです。例えば、送信者のタイプが「postmaster」の場合などです。

配信エラーの理由として考えられるものを以下に示します。

* **[!UICONTROL User unknown]**（ハードタイプ）:アドレスが存在しません。 このプロファイルに対する配信はこれ以上試行されません。
* **[!UICONTROL Quarantined address]**（ハードタイプ）:その住所は検疫に付された。
* **[!UICONTROL Unreachable]**（ソフト/ハードタイプ）:メッセージ配信チェーンでエラーが発生しました（SMTPリレーの問題、ドメインに一時的に到達できない状態など）。 プロバイダーから返されたエラーによると、アドレスは検疫に直接送信されるか、またはCampaignが検疫ステータスを正当化するエラーを受け取るか、エラー数が5に達するまで配信が再試行されます。
* **[!UICONTROL Address empty]**（ハードタイプ）:アドレスが定義されていません。
* **[!UICONTROL Mailbox full]**（ソフトタイプ）:このユーザーのメールボックスはいっぱいで、これ以上メッセージを受け付けられません。 このアドレスを強制隔離リストから削除して、再度試行できます。アドレスは、30 日後に自動的に削除されます。

   強制隔離されたアドレスのリストからアドレスを自動的に削除するには、**[!UICONTROL Database cleanup]**テクニカルワークフローを開始する必要があります。

* **[!UICONTROL Refused]**（ソフト/ハードタイプ）:このアドレスは、スパムレポートとしてのセキュリティフィードバックにより、検疫中に配置されました。 プロバイダーから返されたエラーによると、アドレスは検疫に直接送信されるか、またはCampaignが検疫ステータスを正当化するエラーを受け取るか、エラー数が5に達するまで配信が再試行されます。
* **[!UICONTROL Duplicate]**:このアドレスは既にセグメント化で検出されています。
* **[!UICONTROL Not defined]**（ソフトタイプ）:エラーがまだ増加していないので、アドレスは認定されます。

   このタイプのエラーは、サーバーが新しいエラーメッセージを送信すると発生します。単独のエラーである可能性もありますが、再度発生した場合はエラーカウンターがインクリメントされ、テクニカルチームに警告されます。

* **[!UICONTROL Error ignored]**:ホワイトリストにアドレスがあり、場合によっては電子メールが送信されます。
* **[!UICONTROL Blacklisted address]**:その住所は送信時にブラックリストに記載されていた。
* **[!UICONTROL Account disabled]**（ソフト/ハードタイプ）:インターネットアクセスプロバイダ(IAP)は、長時間操作が行われないことを検出した場合、ユーザーのアカウントを閉じることができます。その後、ユーザーの住所に配信することはできません。 「ソフト」(Soft)または「ハード」(Hard)タイプは、受け取ったエラーのタイプに応じて異なります。6か月間操作が行われなかったためにアカウントが一時的に無効になっていて、アクティブ化できる場合は、ステータスが割り当て**[!UICONTROL Erroneous]** られ、配信が再試行されます。 このエラーが受け取ったアカウントが恒久的に非アクティブ化されたことを知らせるものであれば、直接検疫に送信されます。
* **[!UICONTROL Not connected]**:メッセージの送信時に、プロファイルの携帯電話がオフになるか、ネットワークに接続されません。
* **[!UICONTROL Invalid domain]**（ソフトタイプ）:電子メールアドレスのドメインが正しくないか、存在しません。 このプロファイルは、エラーカウントが 5 にならない限り、再びターゲットになります。その後、レコードは強制隔離ステータスに設定され、以降は再試行されなくなります。
* **[!UICONTROL Text too long]**:smsメッセージの文字数が制限を超えています。 詳しくは、[SMS encoding, length, and transiterationを参照してください](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。
* **[!UICONTROL Character not supported by encoding]**:smsメッセージには、エンコードでサポートされていない1つ以上の文字が含まれています。 詳しくは、「文字表 — GSM標準」[を参照してください](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。

## 一時的な配信エラーの後の再試行 {#retries-after-a-delivery-temporary-failure}

無視タイプの一時的なエラーが原因でメッセージが失敗した場合 **** 、配信期間中に再試行が実行されます。 エラーのタイプについて詳しくは、「配信エラーのタ [イプと理由」を参照してください](#delivery-failure-types-and-reasons)。

配信の期間を変更するには、配信の高度なパラメーターまたは配信テンプレートにアクセスし、対応するフィールドで希望の期間を指定します。高度な配信プロパティについては、[この節](../../administration/using/configuring-email-channel.md#validity-period-parameters)で説明しています。

デフォルトの設定では、1 時間間隔で 5 回、その後 4 日間は 1 日に 1 回再試行されます。再試行の回数の変更は、グローバルに（アドビの技術管理者にお問い合わせください）、または配信または配信テンプレートごとに（[この節](../../administration/using/configuring-email-channel.md#sending-parameters)を参照）おこなうことができます。

## 同期エラーと非同期エラー {#synchronous-and-asynchronous-errors}

配信は、送信後すぐに失敗する（同期エラー）場合と、送信後すぐに失敗する（非同期エラー）場合があります。

* **同期エラー**:adobe Campaign配信サーバーが接続したリモートサーバーが直ちにエラーメッセージを返した場合、配信はプロファイルのサーバーに送信できません。
* **非同期エラー**:バウンスメールまたはSRが、受信サーバによって後で再送された。 非同期エラーは、配信の送信から 1 週間が経過するまで発生する可能性があります。

## バウンスメール強制隔離 {#bounce-mail-qualification}

配信エラーメッセージ（「SMTPバウンス応答」）は、Adobe Campaignプラットフォームによって取得され、データベースを使用して **Hard**、 **Soft**、 **Ignored** のいずれかに処理され **[!UICONTROL Delivery log qualification]**ます。

<!--Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)-->

このリストは管理者のみが利用でき、配信エラーの認定にAdobe Campaignで使用されるすべてのルールが含まれています。

アクセスするには、左上 **[!UICONTROL Adobe Campaign]**部のロゴをクリックし、を選択します**[!UICONTROL Administration > Channels > Email > Email processing rules]**。

詳しくは、[この節](../../administration/using/configuring-email-channel.md#email-processing-rules)を参照してください。

>[!IMPORTANT]
>
>拡張MTAにアップグレードすると、キャンペーンテーブルのバウンス **[!UICONTROL Message qualification]**条件は使用されなくなります。 同期配信の失敗エラーメッセージの場合、拡張MTAはバウンスのタイプと資格を決定し、その情報をCampaignに返します。 非同期バウンスは、inMailプロセスでも認定されます。
>
>Adobe Campaign拡張MTAについて詳しくは、このドキュメントを参照してく [ださい](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)。

バウンスには、次の資格ステータスを設定できます。

* **[!UICONTROL To qualify]**:バウンスメールは資格が必要です。 配信品質は、プラットフォームの配信品質が正しく機能するよう、配信品質チームが行う必要があります。 電子メール処理ルールのリストを拡充するためにバウンスメールが使用されない限り、このメールは使用されません。
* **[!UICONTROL Keep]**:バウンスメールは資格があり、配信品質ワークフローで**&#x200B;既存の電子メール処理ルールと比較し&#x200B;**、リストを強化するために使用されます。
* **[!UICONTROL Ignore]**:バウンスメールは認定されましたが、配信品質のワークフローのために**&#x200B;更新で使用されません&#x200B;**。 したがって、クライアントインスタンスには送信されません。

様々なバウンスと、それに関連するエラータイプなどの理由を表示するには、左上 **[!UICONTROL Adobe Campaign]**のロゴをクリックし、を選択しま**[!UICONTROL Administration > Channels > Quarantines > Message qualification]**&#x200B;す。

![](assets/qualification.png)

## ダブルオプトインメカニズムによるメール配信品質の最適化 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

電子メールを送信する際のベストプラクティスは、ダブルオプトインメカニズムです。 これは、間違った電子メールアドレスや無効な電子メールアドレス、スパムボットからプラットフォームを保護し、迷惑メールの可能性を防ぎます。

原則として、訪問者の契約を確認する電子メールを送信してから、「プロファイル」としてCampaignデータベースに保存します。訪問者がオンラインランディングページに入力し、電子メールを受け取り、確認リンクをクリックして購読を終了する必要があります。

詳しくは、[この節](../../channels/using/setting-up-a-double-opt-in-process.md)を参照してください。
