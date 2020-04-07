---
title: エラー発生時のアラートの受信
description: アラート管理システムの使用方法を説明します。
page-status-flag: never-activated
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# エラー発生時のアラートの受信{#receiving-alerts-when-failures-happen}

## 配信警告 {#about-delivery-alerting}

配信 **警告機能は** 、配信の実行に関する情報を含む通知を、ユーザーのグループが自動的に受け取ることを可能にするアラート管理システムです。

送信される通知には、次の条件に基づくデフォルトのレポートが含まれます。

* 失敗した配信
* 配信の準備に失敗しました
* 配信のソフトバウンスエラー率が正しくありません
* 配信のハードバウンスエラー率が正しくありません
* 配信のステータスが通常より長い
* 配信のスループットが低い
* 配信の処理中

アラートの受信者は、Adobe Campaignが処理している配信を監視し、実行に問題がある場合に適切なアクションを実行できます。

これらのアラート通知は、Adobe Campaign・インタフェースのダッシュボードを介して定義される特定のアラート基準に応じてカスタマイズできます。

>[!NOTE]
>
>警告通知は電子メールでのみ配信されます。

送信される通知には、次が含まれます。

* 定義し **[!UICONTROL Summary]** た条件を満たす配信の数と、各条件で選択したラベル/色を表示します。
* 対応す **[!UICONTROL Details]** るダッシュボードに対して定義されたすべての配信条件と、各条件のすべての配信を一覧表示する節。

![](assets/delivery-alerting_notification.png)

## 配信警告ダッシュボード {#delivery-alerting-dashboards}

### 配信警告ダッシュボード {#about-delivery-alerting-dashboards}

通知の受信者を管理するには、アラート条件を定義し、アラートの履歴にアクセスする必要があります。ダッシュボードを使用します。

>[!NOTE]
>
>ダッシュボードと警告条件にアクセスして設定するには、管理権限を持っているか、 **配信スーパーバイザー** ・セキュリティ・グループに表示されます。 標準ユーザーは、ユーザーインターフェイスのダッシュボードにアクセスできません。 ユーザーは警告通知のみを受け取ることができます。 ユーザーとセキュリティのAdobe Campaignについて詳しくは、「ユーザーのタ [イプ」および「セキュリティ](../../administration/using/users-management.md) グループに [ついて」を参照してくださ](../../administration/using/managing-groups-and-users.md#about-security-groups)い。

Adobe Campaignインターフェイスから、次の操作を行えます。

* アラート配信の作成と管理 詳しくは、 [配信警告ダッシュボードの作成](#creating-a-delivery-alerting-dashboard)。
* 各配信のアラート条件を定義し、管理します。 例えば、準備に失敗した配信やスループットが低い配信に基づいてアラートを作成できます。 「アラート条 [件について](#about-alerting-criteria)」を参照。
* 各パラメーターの条件ダッシュボードを変更 条件パラメ [ーターを参照](#criteria-parameters)。
* 各ユーザーの受信者のグループを定義します。

   例えば、失敗したユーザーのみの管理権限を持つ配信に通知します。 ただし、マーケティングユーザーに、ソフトバウンスの不良配信の情報を受け取るように求めます。 したがって、2つの異なるダッシュボードを作成し、受信者の各グループに対して必要な条件を定義する必要があります。

* 各アラートの送信履歴にアクセスします。ダッシュボード

   ダッシュボードを選択すると、このオプションに対して最後に送信されたダッシュボードがデフォルトで表示されます。 送信されたすべてのアラートが画面の左側に表示されます。 対応するアラートにアクセスするには、 **[!UICONTROL History]** リスト内のアイテムをクリックします。

![](assets/delivery-alerting_dashboard.png)

### 警告配信の作成ダッシュボード {#creating-a-delivery-alerting-dashboard}

特定の条件に基づいて異なるユーザーグループに通知を送信する場合は、複数のユーザーを使用する必要があります。ダッシュボード 新しいダッシュボード

1. 移動 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. を選択し、 **[!UICONTROL Delivery alerting dashboards]** をクリックしま **[!UICONTROL Create]**&#x200B;す。
1. チェックボックスをオ **[!UICONTROL Enabled]** ンにして、現在のダッシュボードをアクティブ化します。

   このオプションを無効にすると、このオプションにリンクされたダッシュボードは送信されなくなります。 このオプションはデフォルトでは無効です。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 通知する受信者のグループをドロップダウン **[!UICONTROL Alert group]** リストで選択します。 グループを変更または作成する方法については、「セキュリ [ティグループの作成とユーザーの割り当て」を参照してくださ](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)い。
1. セクションで、 **[!UICONTROL Delivery alerting criteria]** をクリックして条 **[!UICONTROL Create element]** 件を追加します。 「アラート条 [件について](#about-alerting-criteria)」を参照。
1. ボタンを選択 **[!UICONTROL Edit properties]** します。 タブで、 **[!UICONTROL Criteria parameters]** 条件の適用方法を定義します。 条件パラメ [ーターを参照](#criteria-parameters)。
1. をクリック **[!UICONTROL Create]** して、ダッシュボードを保存します。

これで、配信がこのダッシュボードで定義した条件を満たすたびに、指定したユーザーのグループに警告通知が送信されます。

## 配信警告基準 {#delivery-alerting-criteria}

### アラート条件について {#about-alerting-criteria}

配信警告条件にアクセスするには、/ **[!UICONTROL Administration]** > **[!UICONTROL Channels]** に移動し **[!UICONTROL Delivery alerting]** 、を選択しま **[!UICONTROL Delivery alerting criteria]**&#x200B;す。

![](assets/delivery-alerting_criteria.png)

次の基準を、配信警告ダッシュボードで使用できます。

* **[!UICONTROL Deliveries failed]**:定義された範囲内で配信がスケジュールされ、ステータスが誤っている。
* **[!UICONTROL Deliveries with preparation failed]**:配信が定義された範囲内で変更され、準備手順(ターゲットの計算とコンテンツの生成)が失敗した場合。 詳しくは、送信の準備を参 [照してください](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:定義した範囲内でスケジュールされた配信。少なくとも、ステータスが **[!UICONTROL In progress]**&#x200B;あり、ソフトバウンスエラー率が定義した割合を超える場合。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:定義した範囲内でスケジュールされた配信。少なくともステータス **[!UICONTROL In progress]**&#x200B;を持ち、ハードバウンスエラー率が定義した割合を超える場合。
* **[!UICONTROL Deliveries with long start pending]**:定義された範囲内でスケジュールされた配信( **[!UICONTROL Start pending]** 定義された期間より長いステータス)。 **[!UICONTROL Start pending]** statusは、メッセージがシステムでまだ考慮されていないことを意味します。
* **[!UICONTROL Deliveries with low throughput]**:すべての配信が、定義された期間を超えて開始され、処理済みメッセージの定義された割合を下回り、スループットが定義された値より低い。
* **[!UICONTROL Deliveries in progress]**:定義された範囲内でスケジュールされた配信(ステータスを **[!UICONTROL In progress]** 含む)。

>[!NOTE]
>
>上記の条件に適用されるすべてのパラメーターには、デフォルト値が設定されています。 これらの値は、アラート配信の **[!UICONTROL Criteria parameters]** タブで変更できます。 条件パラメ [ーターを参照](#criteria-parameters)。

詳細にアクセスするには、アイテムをリストから **[!UICONTROL Delivery alerting criteria]** 選択します。

![](assets/delivery-alerting_criteria_definition.png)

各条件に対して、次の設定を定義できます。

* **[!UICONTROL Indicators to add in alerts]**(選択した条件に対応する配信の通知のセクション **[!UICONTROL Details]** に表示される列を意味)。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**&#x200B;を指定します。これは、通知の概要で、配信条件の横に表示されるラベルと色を意味します。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:1つの条件が満たされた場合、監視配信内に送信される各通知でその条件が繰り返されます。 そうでない場合、1つの配信のアラート条件別に、1日に1つのアラートのみが送信されます（最初の発生時）。

   デフォルトでは、このオプションはすべての条件に対して1日に1回設定されています。

**関連トピック：**

* [ログの送信](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [アラート頻度](#alerting-frequency)
* [マーケティングアクティビティのアイコンとステータス](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 配信警告基準の作成 {#creating-a-delivery-alerting-criterion}

ニーズに合わせて新しい配信アラート条件を作成できます。

例えば、新しい条件を作成して、ステータスを持つすべての配信を一覧表示する通知を送信で **[!UICONTROL Finished]** きます。

これを行うには、まず **配信** ・リソースを拡張し、新しいフィルタを追加して、ステータスのある配信のみを選択できるようにする必要があ **[!UICONTROL Finished]** ります。

1. **Adobe Campaign** /管理/開発 **/カスタ** ムリソ **ースに移動し、「クリ********[!UICONTROL Create]**&#x200B;ック」を選択します。
1. を選択 **[!UICONTROL Extend an existing resource]**&#x200B;し、ドロップダ **[!UICONTROL Delivery]** ウンリソースからリソースを選択し、をクリッ **[!UICONTROL Create]** クして編集します。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   既存のリソースの拡張について詳しくは、「リソースの定 [義」を参照してください](../../developing/using/creating-or-extending-the-resource.md)。

1. リソース **[!UICONTROL Delivery]** で、タブに移動し、をク **[!UICONTROL Filter definition]** リックしてフ **[!UICONTROL Add an element]** ィルターを作成します。

   ![](assets/delivery-alerting_new-filter.png)

1. 新しいフィルター定義を編集します。ウィンドウ **[!UICONTROL Filter definition]** で、項目をワークスペースにド **[!UICONTROL Status]** ラッグ&amp;ドロップし、フィル **[!UICONTROL Finished]** ター条件として選択します。

   ![](assets/delivery-alerting_filter-status.png)

   カスタムフィルターの作成と編集について詳しくは、 [フィルターの定義](../../developing/using/configuring-filter-definition.md)。

1. 変更を保存し、リソースを公開します。 詳しくは、「カスタムリソースの公 [開」を参照してください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   フィルタが作成され、新しいアラート条件で選択できるようになった配信。

1. //に移 **[!UICONTROL Administration]** 動し **[!UICONTROL Channels]** 、を選 **[!UICONTROL Delivery alerting]**&#x200B;択してをクリ **[!UICONTROL Delivery alerting criteria]** ックしま **[!UICONTROL Create]**&#x200B;す。
1. ドロップダウ **[!UICONTROL Delivery filter applied by this criterion]** ンリストで、作成したフィルターを選択します。

   ![](assets/delivery-alerting_cus-filter.png)

   デフォルトの条件と同様に、条件の設定を定義できます。 「アラート条 [件について](#about-alerting-criteria)」を参照。

これらの基準は、作成後、他の基準と同様に配信警告ダッシュボードに追加できます。 詳しくは、 [配信警告ダッシュボード](#about-delivery-alerting-dashboards)。

![](assets/delivery-alerting_new-criterion.png)

**関連トピック:**

[リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)

## 配信警告パラメータ {#delivery-alerting-parameters}

### 条件パラメーター {#criteria-parameters}

[ **[!UICONTROL Criteria parameters]** 配信警告 [ダッシュボード](#creating-a-delivery-alerting-dashboard)]タブで、このダッシュボードで選択した条件に適用する設定を定義できます。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例えば、このフィールドに100と入力した場合、ターゲットが100受信者以上の配信に対してのみ通知が送信されます。 このパラメーターは、すべての条件に適用されます。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:現在の時刻の前後の時間数。 この時間範囲の配信のみが考慮されます。 このパラメーターは、すべての条件に適用されます。 デフォルトでは、このフィールドの値は24時間に設定されています。

   連絡日の詳細については、「スケジュールについ [て」を参照してください](../../sending/using/about-scheduling-messages.md)。

* **[!UICONTROL Maximum ratio of soft bounce errors]**:指定した値より大きいソフトバウンスエラー率の配信すべてに対して通知が送信されます。 デフォルトでは、このフィールドの値は0.05 (5%)に設定されています。

   ソフトバウンスエラーについて詳しくは、バウンスメ [ールの資格と](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 、配信障害 [の種類のリストを参照してください](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Maximum ratio of hard bounce errors]**:ハードバウンスエラー率が指定値より大きいすべての配信に対して通知が送信されます。 デフォルトでは、このフィールドの値は0.05 (5%)に設定されています。

   ハードバウンスエラーについて詳しくは、「バウンスメ [ールの資格と](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 、配信障害の [リスト」を参照してください](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:このフィールドで指定した期間より長いステータスを持つす **[!UICONTROL Start pending]** べての配信に対して、通知が送信されます。つまり、 **[!UICONTROL Start pending]** statusは、メッセージがシステムによってまだ考慮されていないことを意味します。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:配信が指定された期間 **[!UICONTROL In progress]** を超えて開始された（ステータスの）場合のみ、条件が考慮さ **[!UICONTROL Deliveries with low throughput]** れます。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:処理された配信の割合が指定した割合より低い場合のみ、条件が考慮され **[!UICONTROL Deliveries with low throughput]** ます。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:配信のスループットが指定値より低い場合のみ、条件が考慮され **[!UICONTROL Deliveries with low throughput]** ます。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:処理された配信の割合が、指定した割合を超える場合にのみ考慮されます。

### アラート頻度 {#alerting-frequency}

このオプ **[!UICONTROL Frequency of delivery alerting]** ションを使用して、2つのアラート送信間の遅延を定義できます。 デフォルトでは、10分に設定されています。

この設定は、//メニューから **[!UICONTROL Administration]** 変更で **[!UICONTROL Application settings]** き **[!UICONTROL Options]** ます。

>[!NOTE]
>
>このオプションは、Adobe Campaignで定義されたすべてのダッシュボードに適用されます。 特定の頻度を設定することはできません。ダッシュボードごとに

## 配信警告の理由 {#delivery-alerting-reasons}

配信ア **ラート機能を使用すると** 、関与するすべてのAdobe Campaignユーザーに対して、電子メールやダッシュボード経由で配信の実行ステータスに関する通知が自動的に送信されます。

次に、配信警告通知を受け取ったら、実行できる操作に関するヒントを示します。

まず、配信の「 **Log** 」タブをチェックして、配信と配達確認に関するすべての情報を表示します。 赤と黄色のアイコンを使用して、エラーや警告を識別できます。 赤いアイコンは、重大なエラーが発生し、配信の起動を妨げていることを示します。

すべての表示の履歴を選択するには、配信のタブを選択 **[!UICONTROL Sending logs]** します。 送信されたメッセージのリストとそのステータスが含まれます。 各受信者（、など）の配信ステータスを確 **[!UICONTROL Sent]**&#x200B;認す **[!UICONTROL Pending]**&#x200B;るこ **[!UICONTROL Failed]**&#x200B;とができます。 詳しくは、ログの送信を参照し [てください](../../sending/using/monitoring-a-delivery.md#sending-logs)。

配信の条件に従ってアラート通知を受信する場合、考えられる理由を以下に示します。

* **[!UICONTROL Deliveries failed]**:この条件は、エラーのあるすべての配信を通知します。 次の原因が考えられます。

   * 配信サーバー(MTA、Message Transfer Agent)の問題
   * Adobe Campaign配信サーバと受信サーバとの接続タイムアウト
   * 配信品質の問題
   * 誤ったワークフロー
   ワークフローで配信がトリガーされる場合は、そのワークフローが正しく開始されているかどうかを確認します。 詳しくは、「ワークフローの実行」を [参照してください](../../automating/using/executing-a-workflow.md)。 それ以外の場合は、問題を解決するためにAdobe Campaign管理者に連絡してください。

* **[!UICONTROL Deliveries with preparation failed]**:次の場合、配信の準備中にエラーが発生します。

   * 配信に件名がありません。
   * 構文が正しくありません。パーソナライゼーションフィールド。
   * ターゲットがありません。
   * 配信がサイズ制限を超えています。
   詳しくは、送信の準備を参 [照してください](../../sending/using/preparing-the-send.md)。 ただし、これらのエラーは通常、メッセージの分析中に見つかります。 「制御ル [ール」を参照](../../sending/using/control-rules.md)。

* アラートの原因として考えら **[!UICONTROL Delivery with bad error ratio for soft bounces]** れるのは、次のとおりです。

   * 受信者のサーバーがダウンしている。
   * 受信者のメールボックスがいっぱいです。
   詳しくは、タブとタブを **[!UICONTROL Exclusion logs]** 確認し **[!UICONTROL Exclusion causes]** てください。配信ログ 除外ログ [を参照してください](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

   アラートの原因として考えら **[!UICONTROL Delivery with bad error ratio for hard bounces]** れるのは、次のとおりです。

   * 受信者は「ブラックリスト登録済み」です。つまり、もう連絡を取りたくないということです。
   * 受信者の電子メールアドレスが存在しません。
   * 受信者のドメインが存在しません。
   * 受信者のサーバーが配信をブロック。
   ソフトバウンスとハードバウンスのエラーを回避するには、次のベストプラクティスに従ってください。

   * フィルタリングタイポロジルールを作成し、隔離された受信者など、配信分析中にメッセージターゲットの一部を除外します。 See [Creating a filtering rule](../../sending/using/filtering-rules.md).
   * 顧客データベースを定期的に更新し、適切な強制隔離管理プロセスを維持します。 [強制隔離について](../../sending/using/understanding-quarantine-management.md#about-quarantines)を参照してください。
   * 一般に、配信品質はできるだけ向上します。 Adobe Campaignの配信品質の詳細 [なドキュメント](../../sending/using/about-deliverability.md) を参照し、Adobe Campaign管理者に問い合わせてください。



* **[!UICONTROL Deliveries with long start pending]**:通常、これは、MTA(Message Transfer Agent)レベルで問題があることを意味します。 実行プロセスが、リソースが使用可能になるのを待っています。MTA が開始されていない可能性があります。

   **[!UICONTROL Deliveries with low throughput]**:繰り返しますが、これは配信品質の問題で、MTAの処理速度が遅すぎることを意味します。

   これらの問題の詳細については、担当のAdobe Campaign管理者にお問い合わせください。

**関連トピック：**

* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [ブラックリストの管理キャンペーン](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

