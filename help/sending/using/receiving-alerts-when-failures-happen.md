---
title: エラー発生時のアラートの受信
seo-title: エラー発生時のアラートの受信
description: エラー発生時のアラートの受信
seo-description: アラート管理システムの使用方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: a3ab733a- e3db-4adc- b930- cd4064b6dc1c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: 0766bd57- c5f1-4f56- ac84- e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Receiving alerts when failures happen{#receiving-alerts-when-failures-happen}

## About delivery alerting {#about-delivery-alerting}

**配信の警告** 機能は、ユーザーグループが配信の実行に関する情報を含む通知を自動的に受信できるアラート管理システムです。

送信される通知には、デフォルトで次の条件に基づくレポートが含まれます。

* 配信失敗
* 準備に失敗した配信
* ソフトバウンスエラーの割合の配信配信
* ハードバウンスのエラー率の高い配信
* 保留中のステータスが通常よりも長い配信
* 低スループットの配信
* 配信中

アラートの受信者は、Adobe Campaignによって処理されている配信を監視し、実行時に問題が発生した場合に適切なアクションを実行できます。

これらの警告通知は、Adobe Campaignインターフェイスのダッシュボードによって定義される特定の警告条件に応じてカスタマイズできます。

>[!NOTE]
>
>通知通知は電子メールでのみ配信されます。

送信される通知には次のものがあります。

* A **[!UICONTROL Summary]** displaying the number of deliveries meeting the criteria that you defined and the label/color that you chose for each criterion.
* **[!UICONTROL Details]** 該当するダッシュボードに対して定義されているすべての配信条件と、各条件に対するすべての配信条件を一覧表示するセクション。

![](assets/delivery-alerting_notification.png)

## Delivery alerting dashboards {#delivery-alerting-dashboards}

### About delivery alerting dashboards {#about-delivery-alerting-dashboards}

通知の受信者を管理し、アラートの条件を定義し、アラートの履歴にアクセスするには、ダッシュボードを使用する必要があります。

>[!NOTE]
>
>To access and configure the dashboards and the alerting criteria, you must have administration rights or appear in the **Delivery supervisors** security group. Standardのユーザーは、Adobe Campaignインターフェイスでダッシュボードにアクセスできません。アラート通知のみを受信できます。For more on users and security in Adobe Campaign, see [Types of users](../../administration/using/types-of-users.md) and [About security groups](../../administration/using/managing-groups-and-users.md#about-security-groups).

Adobe Campaignインターフェイスでは、次のことができます。

* ダッシュボードを警告する配信を作成および管理します。See [Creating a delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard).
* 各ダッシュボードの配信に関する基準条件を定義および管理します。例えば、準備に失敗した配信や低スループットのみの配信に基づいてアラートを構築できます。See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
* 各ダッシュボードの条件パラメーターを変更します。See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
* 各ダッシュボードの受信者のグループを定義します。

   例えば、配信失敗の管理権限をユーザーに通知する場合などです。ただし、マーケティングユーザーが配信に関する情報を受信すると、ソフトバウンスの不正確なエラーとなります。したがって、2つの異なるダッシュボードを作成して、各受信者グループに必要な条件を定義する必要があります。

* 各ダッシュボードのすべての送信済みアラートの履歴にアクセスします。

   ダッシュボードを選択すると、このダッシュボードの最後に送信されたアラートがデフォルトで表示されます。送信されたアラートはすべて画面の左側に表示されます。Click an item in the **[!UICONTROL History]** list to access the corresponding alerts.

![](assets/delivery-alerting_dashboard.png)

### Creating a delivery alerting dashboard {#creating-a-delivery-alerting-dashboard}

特定の条件に基づいて通知を送信する場合は、複数のダッシュボードを使用する必要があります。新しいダッシュボードを作成するには:

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Select **[!UICONTROL Delivery alerting dashboards]** and click **[!UICONTROL Create]**.
1. **[!UICONTROL Enabled]** 現在のダッシュボードをアクティブにするには、該当のチェックボックスをオンにします。

   このオプションを無効にすると、このダッシュボードにリンクされている通知は送信されなくなります。このオプションはデフォルトで無効になっています。

   ![](assets/delivery-alerting_dashboard_general.png)

1. Select the group of recipients that you want to notify from the **[!UICONTROL Alert group]** drop-down list. To modify or create a group, see [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. **[!UICONTROL Delivery alerting criteria]** セクションから、をクリック **[!UICONTROL Create element]** して条件を追加します。See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
1. **[!UICONTROL Edit properties]** ボタンを選択します。**[!UICONTROL Criteria parameters]** タブで、条件の適用方法を定義します。See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

現在は、配信がこのダッシュボードで定義した条件を満たすたびに、指定したユーザグループに警告通知が送信されます。

## Delivery alerting criteria {#delivery-alerting-criteria}

### About alerting criteria {#about-alerting-criteria}

To access the delivery alerting criteria, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** and select **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

次の条件は、ダッシュボードの警告ダッシュボードで使用できます。

* **[!UICONTROL Deliveries failed]**:定義済みの範囲内でスケジュールされた配信で、ステータスが誤っている。
* **[!UICONTROL Deliveries with preparation failed]**:定義された範囲内で変更された配信で、準備手順（ターゲットの計算とコンテンツ生成）が失敗します。For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:定義済みの範囲内でスケジュールされた配信（ステータスが少なくとも **[!UICONTROL In progress]**、定義済みの割合よりも大きい）。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:定義された範囲内でスケジュールされた配信（ステータスが少なく **[!UICONTROL In progress]**&#x200B;とも直帰率の高い）。
* **[!UICONTROL Deliveries with long start pending]**:定義済みの範囲内でスケジュールされた配信で **[!UICONTROL Start pending]** 、定義された期間より長い状態で **[!UICONTROL Start pending]** 、メッセージがまだシステムによって考慮されていないことを意味します。
* **[!UICONTROL Deliveries with low throughput]**:定義された一連のメッセージのうち、定義された割合よりも少ない配信が開始され、定義された値よりも少ないスループットが得られます。
* **[!UICONTROL Deliveries in progress]**:定義済みの範囲内でスケジュールされた配信の **[!UICONTROL In progress]** 状態。

>[!NOTE]
>
>上記の条件に適用されるすべてのパラメーターにデフォルト値があります。These values can be changed in the **[!UICONTROL Criteria parameters]** tab of the delivery alerting dashboards. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).

You can select any item from the **[!UICONTROL Delivery alerting criteria]** list to access its details.

![](assets/delivery-alerting_criteria_definition.png)

各条件について、次の設定を定義できます。

* **[!UICONTROL Indicators to add in alerts]**&#x200B;を **[!UICONTROL Details]** 参照してください。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**&#x200B;とは、通知の概要の配信条件の横に表示されるラベルと色です。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:1つの配信に対して条件が満たされた場合、監視期間内に送信される通知ごとに繰り返されます。そうしないと、1回の配信のアラート条件によって1つのアラートのみが1つのアラートに送信されます。

   デフォルトでは、すべての条件の1日に1回このオプションが設定されます。

**関連トピック:**

* [ログの送信](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警告頻度](../../sending/using/receiving-alerts-when-failures-happen.md#alerting-frequency)
* [マーケティングアクティビティのアイコンとステータス](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creating a delivery alerting criterion {#creating-a-delivery-alerting-criterion}

ニーズに合わせて、新しい配信基準を作成できます。

For example, you can create a new criterion enabling to send a notification listing all deliveries with a **[!UICONTROL Finished]** status.

To do this, you first need to extend the **Delivery** resource and add a new filter allowing you to select only the deliveries with a **[!UICONTROL Finished]** status.

1. **Adobe Campaign** / **管理** / **開発** / **カスタムリソースに移動** し、をクリック **[!UICONTROL Create]**&#x200B;します。
1. Select **[!UICONTROL Extend an existing resource]**, select the **[!UICONTROL Delivery]** resource from the drop-down list and click **[!UICONTROL Create]** to edit it.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   For more on extending an existing resource, see [Define the resource](../../developing/using/creating-or-extending-the-resource.md).

1. **[!UICONTROL Delivery]** リソースでタブに **[!UICONTROL Filter definition]** 移動し、をクリック **[!UICONTROL Add an element]** してフィルターを作成します。

   ![](assets/delivery-alerting_new-filter.png)

1. Edit the new filter definition: in the **[!UICONTROL Filter definition]** window, drag and drop the **[!UICONTROL Status]** item into the workspace and select **[!UICONTROL Finished]** as the filter condition.

   ![](assets/delivery-alerting_filter-status.png)

   For more on creating and editing custom filters, see [Define filters](../../developing/using/configuring-filter-definition.md).

1. 変更を保存し、リソースを公開します。For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   フィルターが作成され、新しい配信条件で選択できるようになりました。

1. **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**&#x200B;に移動し、選択 **[!UICONTROL Delivery alerting criteria]** してクリック **[!UICONTROL Create]**&#x200B;します。
1. **[!UICONTROL Delivery filter applied by this criterion]** ドロップダウンリストで、作成したフィルターを選択します。

   ![](assets/delivery-alerting_cus-filter.png)

   条件の設定は、デフォルトの条件と同じ方法で定義できます。See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).

これらの条件を作成すると、他の条件と共に、ダッシュボードにアラートを追加できます。See [About delivery alerting dashboards](../../sending/using/receiving-alerts-when-failures-happen.md#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**関連トピック:**

[リソースの追加または拡張](../../developing/using/key-steps-of-adding-a-resource.md)

## Delivery alerting parameters {#delivery-alerting-parameters}

### Criteria parameters {#criteria-parameters}

In the **[!UICONTROL Criteria parameters]** tab of a [delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard), you can define the settings that apply to the criteria selected in this dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例えば、このフィールドに100と入力すると、ターゲットと100人以上の受信者の配信についてのみ通知が送信されます。このパラメーターはすべての条件に適用されます。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:現在時間の前後の時間数。この時間範囲に連絡日を持つ配信のみが考慮されます。このパラメーターはすべての条件に適用されます。デフォルトでは、このフィールドの値は24時間に設定されています。

   For more information on the contact date, see [About the scheduling](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**:指定した値よりも大きいバウンスエラーの割合を持つすべての配信に対して通知が送信されます。デフォルトでは、このフィールドの値は0.05（5%）に設定されています。

   For more on soft bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**:指定した値よりも大きい直帰率のエラーを持つすべての配信に対して通知が送信されます。デフォルトでは、このフィールドの値は0.05（5%）に設定されています。

   For more on hard bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:このフィールドで指定された期間より **[!UICONTROL Start pending]** 長い状態の配信がすべて送信され、 **[!UICONTROL Start pending]** そのメッセージがまだシステムによって考慮されていないことを意味します。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:指定した期間を **[!UICONTROL In progress]** 超える配信のみが **[!UICONTROL Deliveries with low throughput]** 、条件に応じて考慮されます。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:指定した割合より少ない処理されたメッセージに対する割合の配信のみが **[!UICONTROL Deliveries with low throughput]** 考慮されます。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:指定した値よりも少ないスループットの配信のみが **[!UICONTROL Deliveries with low throughput]** 考慮されます。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:指定した割合よりも大きい処理済みメッセージの割合を持つ配信のみが考慮されます。

### Alerting frequency {#alerting-frequency}

**[!UICONTROL Frequency of delivery alerting]** このオプションを使用すると、2つのアラートの条項間の遅延を定義できます。デフォルトでは、10分に設定されています。

You can change this setting through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

>[!NOTE]
>
>このオプションは、Adobe Campaignで定義されているすべてのダッシュボードに適用されます。ダッシュボードごとに特定の頻度を設定することはできません。

## Delivery alerting reasons {#delivery-alerting-reasons}

**配信の警告** 機能により、電子メールやダッシュボード経由で、配信の実行ステータスについて自動的に通知されるAdobe Campaignユーザーがすべて保持されます。

ここでは、通知通知を受信する際に、できることに関するいくつかのヒントを紹介します。

First of all, check the delivery's **Log** tab to view all information relating to the delivery and proofs. 赤と黄色のアイコンを使用すると、エラーや警告を識別できます。赤のアイコンは、配信が開始されないようにする重大なエラーを示します。

To view the history of every occurrence of a delivery, select the **[!UICONTROL Sending logs]** tab. 送信されたメッセージとそのステータスのリストが含まれます。There you can check the delivery status for each recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

配信のために満たす条件に従って警告通知を受信する理由をいくつか考えてみましょう。

* **[!UICONTROL Deliveries failed]**:この条件により、ステータスが誤っているすべての配信が通知されます。次のことが原因となります。

   * 配信サーバー（MTA、Message Transfer Agent）に関する問題
   * Adobe Campaign配信サーバーと受信サーバー間の接続タイムアウト
   * 配信品質の問題
   * 誤ったワークフロー
   ワークフローで配信がトリガーされた場合は、そのワークフローが正しく開始されているかどうかを確認してください。For more on this, see [Executing a workflow](../../automating/using/executing-a-workflow.md). それ以外の場合は、Adobe Campaign管理者と連絡して問題を解決してください。

* **[!UICONTROL Deliveries with preparation failed]**:次の場合、配信準備中にエラーが発生する可能性があります。

   * 配信に件名がありません。
   * パーソナライゼーションフィールドで構文が正しくありません。
   * ターゲットがありません。
   * 配信がサイズ制限を超えています。
   For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md). ただし、これらのエラーはメッセージの分析中に一般的に示されます。See [Control rules](../../administration/using/control-rules.md).

* The possible causes for a **[!UICONTROL Delivery with bad error ratio for soft bounces]** alert can be:

   * 受信者のサーバーがダウンしています。
   * 受信者のメールボックスがいっぱいです。
   For more information, check the **[!UICONTROL Exclusion logs]** and **[!UICONTROL Exclusion causes]** tabs of the delivery logs. [除外ログを参照](../../sending/using/monitoring-a-delivery.md#exclusion-logs)してください。

   The possible causes for a **[!UICONTROL Delivery with bad error ratio for hard bounces]** alert can be:

   * 受信者はブラックリストに登録されているため、連絡しなくても構いません。
   * 受信者の電子メールアドレスが存在しません。
   * 受信者のドメインが存在しません。
   * 受信者のサーバーが配信をブロックしています。
   ソフトおよびハードバウンドのエラーを回避するには、以下のベストプラクティスに従ってください。

   * 配信分析中にメッセージターゲットの一部を除外するようにフィルタータイポロジルールを構築します（隔離された受信者など）。See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * 定期的に顧客データベースを更新して、堅牢な隔離管理プロセスを維持します。See [About quarantines](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * 一般に、配信品質を向上させてください。See the Adobe Campaign v7 [Managing deliverability](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) detailed guide and contact your Adobe Campaign administrator for assistance.



* **[!UICONTROL Deliveries with long start pending]**:通常、MTA（Message Transfer Agent）レベルで問題が発生します。実行プロセスは、一部のリソースの可用性を待機しています。MTAが開始されていない可能性があります。

   **[!UICONTROL Deliveries with low throughput]**:これは、MTAが遅すぎるという配信品質の問題です。

   これらの問題について詳しくは、Adobe Campaign管理者にお問い合わせください。

**関連トピック:**

* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [強制隔離について](../../sending/using/understanding-quarantine-management.md)
* [キャンペーンでのブラックリストの管理](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

