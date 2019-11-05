---
title: エラー発生時のアラートの受信
description: アラート管理システムの使用方法を説明します。
page-status-flag: 非活性化の
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# エラー発生時のアラートの受信{#receiving-alerts-when-failures-happen}

## 配信アラートについて {#about-delivery-alerting}

配信ア **ラート機能は** 、ユーザーのグループが配信の実行に関する情報を含む通知を自動的に受け取れるようにするアラート管理システムです。

送信される通知には、デフォルトで次の条件に基づくレポートが含まれます。

* 配信失敗
* 準備に失敗した配信
* ソフトバウンスエラー率の悪い配信
* ハードバウンスエラー率の悪い配信
* 保留状態の配信が通常より長い
* 低スループットの配信
* 配信中

アラートの受信者は、Adobe Campaignで処理されている配信を監視し、アラートの実行に問題がある場合に適切な処置をとることができます。

これらの警告通知は、Adobe Campaignインターフェイスのダッシュボードで定義される特定の警告条件に応じてカスタマイズできます。

>[!NOTE]
>
>警告通知は電子メールでのみ配信されます。

送信される通知には、次の情報が含まれます。

* 定義 **[!UICONTROL Summary]** した条件を満たす配信数と、各条件で選択したラベル/色を表示するもの。
* 対応す **[!UICONTROL Details]** るダッシュボードに定義されたすべての配信条件と、各条件に対するすべての配信条件を一覧表示するセクション。

![](assets/delivery-alerting_notification.png)

## 配信警告ダッシュボード {#delivery-alerting-dashboards}

### 配信警告ダッシュボードについて {#about-delivery-alerting-dashboards}

通知の受信者を管理するには、アラート条件を定義し、アラートの履歴にアクセスするダッシュボードを使用する必要があります。

>[!NOTE]
>
>ダッシュボードとアラート条件にアクセスして設定するには、管理権限を持っているか、配信スーパーバイザーのセキュリティグループに表 **示される** 必要があります。 標準ユーザーは、Adobe Campaignインターフェイスでダッシュボードにアクセスできません。 通知を受け取ることができるのは、アラート通知のみです。 Adobe Campaignのユーザーとセキュリティについて詳しくは、「ユーザーのタイプ」お [よび「セキュリティグループ](../../administration/using/users-management.md) 」 [を参照してください](../../administration/using/managing-groups-and-users.md#about-security-groups)。

Adobe Campaignインターフェイスから、次の操作を行うことができます。

* 配信アラートダッシュボードを作成し、管理します。 「配信アラ [ートダッシュボードの作成](#creating-a-delivery-alerting-dashboard)」を参照。
* 各ダッシュボードの配信アラート条件を定義し、管理します。 例えば、準備に失敗した配信やスループットが低い配信に基づいてアラートを作成できます。 「アラート [条件について](#about-alerting-criteria)」を参照。
* 各ダッシュボードの条件パラメータを変更します。 条件パラメ [ーターを参照してくださ](#criteria-parameters)い。
* 各ダッシュボードの受信者のグループを定義します。

   例えば、失敗した配信のみの管理権限を持つユーザーに通知するとします。 ただし、ソフトバウンス不良エラー率を持つ配信に関する情報をマーケティングユーザーに受け取ってもらいたい場合は、 したがって、2つの異なるダッシュボードを作成し、受信者の各グループに必要な条件を定義する必要があります。

* 各ダッシュボードの送信済みすべてのアラートの履歴にアクセスします。

   ダッシュボードを選択すると、このダッシュボードに対して最後に送信されたアラートがデフォルトで表示されます。 送信されたすべてのアラートが画面の左側に表示されます。 対応するアラートにアクセスするには、 **[!UICONTROL History]** リスト内のアイテムをクリックします。

![](assets/delivery-alerting_dashboard.png)

### 配信警告ダッシュボードの作成 {#creating-a-delivery-alerting-dashboard}

特定の条件に基づいて異なるユーザーグループに通知を送信する場合は、複数のダッシュボードを使用する必要があります。 新しいダッシュボードを作成するには：

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. を選択し、 **[!UICONTROL Delivery alerting dashboards]** をクリックしま **[!UICONTROL Create]**&#x200B;す。
1. 現在のダッシュボ **[!UICONTROL Enabled]** ードをアクティブにするには、このボックスをオンにします。

   このオプションを無効にすると、このダッシュボードにリンクされた通知は送信されなくなります。 このオプションはデフォルトでは無効です。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 通知する受信者のグループをドロップダウンリスト **[!UICONTROL Alert group]** から選択します。 グループを変更または作成するには、「セキュリティグ [ループの作成とユーザーの割り当て」を参照してくださ](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)い。
1. セクションで、 **[!UICONTROL Delivery alerting criteria]** をクリックして条 **[!UICONTROL Create element]** 件を追加します。 「アラート [条件について](#about-alerting-criteria)」を参照。
1. ボタンを選択 **[!UICONTROL Edit properties]** します。 タブで、 **[!UICONTROL Criteria parameters]** 条件の適用方法を定義します。 条件パラメ [ーターを参照してくださ](#criteria-parameters)い。
1. をクリック **[!UICONTROL Create]** して、ダッシュボードを保存します。

現在は、配信がこのダッシュボードで定義した条件を満たすたびに、指定したユーザーのグループに警告通知が送信されます。

## 配信アラート条件 {#delivery-alerting-criteria}

### アラート条件について {#about-alerting-criteria}

配信アラート条件にアクセスするには、/ **[!UICONTROL Administration]** &gt;に移動 **[!UICONTROL Channels]** し、 **[!UICONTROL Delivery alerting]** を選択しま **[!UICONTROL Delivery alerting criteria]**&#x200B;す。

![](assets/delivery-alerting_criteria.png)

配信警告ダッシュボードでは、次の条件を使用できます。

* **[!UICONTROL Deliveries failed]**:定義された範囲内でスケジュールされた配信で、ステータスが誤っている。
* **[!UICONTROL Deliveries with preparation failed]**:定義された範囲内で変更された配信で、準備手順（ターゲットの計算とコンテンツの生成）が失敗した場合。 詳しくは、「送信の準備」を [参照してください](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:少なくともステータスが定義済みの範囲内でスケジュールされた、ソフトバ **[!UICONTROL In progress]**&#x200B;ウンスエラー率が定義済みの割合を超える配信。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:定義された範囲内にスケジュールされた、少なくともステータスを持つ配信で、ハ **[!UICONTROL In progress]**&#x200B;ードバウンスエラー率が定義された割合を超えるもの。
* **[!UICONTROL Deliveries with long start pending]**:定義された範囲内でスケジュールされた配信。ステータスは、 **[!UICONTROL Start pending]** 定義された期間より長く、メッセージはシステムによってまだ考慮されていな **[!UICONTROL Start pending]** いことを意味します。
* **[!UICONTROL Deliveries with low throughput]**:定義された期間を超える配信が開始され、処理済みメッセージの定義された割合未満で、スループットが定義された値より低い。
* **[!UICONTROL Deliveries in progress]**:定義した範囲内にスケジュールされた、ステータスを持つす **[!UICONTROL In progress]** べての配信。

>[!NOTE]
>
>上記の条件に適用するすべてのパラメーターには、デフォルト値が設定されています。 これらの値は、配信警告ダッシュボ **[!UICONTROL Criteria parameters]** ードのタブで変更できます。 条件パラメ [ーターを参照してくださ](#criteria-parameters)い。

リストから任意の項目を選択して、その詳 **[!UICONTROL Delivery alerting criteria]** 細にアクセスできます。

![](assets/delivery-alerting_criteria_definition.png)

各条件に対して、次の設定を定義できます。

* **[!UICONTROL Indicators to add in alerts]**&#x200B;を指定します。つまり、選択した条件に対応する配信に対して、通 **[!UICONTROL Details]** 知のセクションに表示される列です。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**&#x200B;を指定します。つまり、通知の概要で配信条件の横に表示されるラベルと色を指定します。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:1回の配信に対して条件が満たされた場合、監視期間内に送信される各通知でその条件が繰り返されます。 それ以外の場合は、1回の配信に関するアラート条件別に、1日に1つのアラートのみが送信されます（最初のアラートの発生時）。

   デフォルトでは、このオプションはすべての条件に対して1日に1回設定されています。

**関連トピック：**

* [ログの送信](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [アラート頻度](#alerting-frequency)
* [マーケティングアクティビティのアイコンとステータス](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 配信アラート条件の作成 {#creating-a-delivery-alerting-criterion}

ニーズに合わせて新しい配信アラート条件を作成できます。

例えば、新しい条件を作成して、すべての配信のステータスを示す通知を送信でき **[!UICONTROL Finished]** ます。

これを行うには、まず配信リソースを拡張し **、新しいフィルターを追加して** 、ステータスの配信のみを選択できるようにする必要があ **[!UICONTROL Finished]** ります。

1. Adobe Campaign/管理/開発 **** /カス **タムリソース** / **ク********[!UICONTROL Create]**&#x200B;リックに移動します。
1. を選択 **[!UICONTROL Extend an existing resource]**&#x200B;し、ドロップダ **[!UICONTROL Delivery]** ウンリストからリソースを選択し、をクリック **[!UICONTROL Create]** して編集します。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   既存のリソースの拡張について詳しくは、「リソースの定 [義」を参照してください](../../developing/using/creating-or-extending-the-resource.md)。

1. リソース **[!UICONTROL Delivery]** で、タブに移動し、をク **[!UICONTROL Filter definition]** リックしてフ **[!UICONTROL Add an element]** ィルターを作成します。

   ![](assets/delivery-alerting_new-filter.png)

1. 新しいフィルター定義を編集します。ウィンドウ **[!UICONTROL Filter definition]** で、アイテムをワークスペースにド **[!UICONTROL Status]** ラッグ&amp;ドロップし、フィル **[!UICONTROL Finished]** ター条件として選択します。

   ![](assets/delivery-alerting_filter-status.png)

   カスタムフィルターの作成と編集について詳しくは、フィルターの定義を参 [照してくださ](../../developing/using/configuring-filter-definition.md)い。

1. 変更を保存し、リソースを発行します。 詳しくは、「カスタムリソースの公 [開」を参照してください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   フィルターが作成され、新しい配信アラート条件で選択できるようになりました。

1. /に移動し **[!UICONTROL Administration]** 、を選 **[!UICONTROL Channels]** 択し **[!UICONTROL Delivery alerting]**&#x200B;てをクリ **[!UICONTROL Delivery alerting criteria]** ックしま **[!UICONTROL Create]**&#x200B;す。
1. ドロップダ **[!UICONTROL Delivery filter applied by this criterion]** ウンリストで、作成したフィルターを選択します。

   ![](assets/delivery-alerting_cus-filter.png)

   既定の条件と同じ方法で条件の設定を定義できます。 「アラート [条件について](#about-alerting-criteria)」を参照。

これらの条件を作成すると、配信警告ダッシュボードおよび他の条件に追加できます。 「配信警告ダ [ッシュボードについて](#about-delivery-alerting-dashboards)」を参照してください。

![](assets/delivery-alerting_new-criterion.png)

**関連トピック：**

[リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)

## 配信警告パラメータ {#delivery-alerting-parameters}

### 条件パラメーター {#criteria-parameters}

配信アラートダ **[!UICONTROL Criteria parameters]** ッシュボ [ードのタブで](#creating-a-delivery-alerting-dashboard)、このダッシュボードで選択した条件に適用する設定を定義できます。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例えば、このフィールドに100と入力した場合、ターゲットが100人以上の配信に対してのみ通知が送信されます。 このパラメーターは、すべての条件に適用されます。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:現在の時刻の前後の時間数。 この時間範囲に連絡日を持つ配信のみが考慮されます。 このパラメーターは、すべての条件に適用されます。 デフォルトでは、このフィールドの値は24時間に設定されています。

   連絡日の詳細については、「スケジュールにつ [いて](../../sending/using/about-scheduling-messages.md)」を参照してください。

* **[!UICONTROL Maximum ratio of soft bounce errors]**:指定した値より大きいソフトバウンスエラー率を持つすべての配信に対して通知が送信されます。 デフォルトでは、このフィールドの値は0.05 (5%)に設定されています。

   ソフトバウンスエラーについて詳しくは、「バウンスメ [ールの資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 」と「配 [信失敗タイプのリスト](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)」を参照してください。

* **[!UICONTROL Maximum ratio of hard bounce errors]**:ハードバウンスエラー率が指定値より大きいすべての配信に対して通知が送信されます。 デフォルトでは、このフィールドの値は0.05 (5%)に設定されています。

   ハードバウンスエラーについて詳しくは、「バウンスメ [ールの資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 」と「配 [信失敗タイプのリスト](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)」を参照してください。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:このフィールドで指定した期間より長いステータスを持つすべての配信に対して、通知が送信されます。つまり、 **[!UICONTROL Start pending]****[!UICONTROL Start pending]** statusは、メッセージがシステムによってまだ考慮されていないことを意味します。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:指定した期間を超え **[!UICONTROL In progress]** る配信が開始された（ステータスの）場合のみ、条件が考慮さ **[!UICONTROL Deliveries with low throughput]** れます。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:処理済みメッセージの割合が指定した割合より低い配信のみが、条件に考慮され **[!UICONTROL Deliveries with low throughput]** ます。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:指定した値より低いスループットを持つ配信のみが基準に考慮され **[!UICONTROL Deliveries with low throughput]** ます。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:処理済みメッセージの割合が指定した割合を超える配信のみが考慮されます。

### アラート頻度 {#alerting-frequency}

このオ **[!UICONTROL Frequency of delivery alerting]** プションを使用して、2つのアラート送信間の遅延を定義できます。 デフォルトでは、10分に設定されています。

この設定は、//メニューから **[!UICONTROL Administration]** 変更で **[!UICONTROL Application settings]** き **[!UICONTROL Options]** ます。

>[!NOTE]
>
>このオプションは、Adobe Campaignで定義されているすべてのダッシュボードに適用されます。 各ダッシュボードに特定の頻度を設定することはできません。

## 配信アラートの理由 {#delivery-alerting-reasons}

配信アラ **ート機能を使用すると** 、Adobe Campaignの関与するすべてのユーザーに対して、電子メールおよびダッシュボードを介して配信の実行ステータスが自動的に通知されます。

配信通知を受け取ったら、実行できる操作に関するヒントを以下に示します。

まず、配信の「ログ」タブを確認し **て** 、配信と校正に関するすべての情報を表示します。 赤と黄色のアイコンを使用して、エラーや警告を識別できます。 赤いアイコンは、配信を開始できない重大なエラーを示します。

配信のすべてのオカレンスの履歴を表示するには、タブを選択 **[!UICONTROL Sending logs]** します。 送信メッセージとそのステータスのリストが含まれます。 各受信者（、など）の配信ステータ **[!UICONTROL Sent]**&#x200B;スを **[!UICONTROL Pending]**&#x200B;確 **[!UICONTROL Failed]**&#x200B;認できます。 詳しくは、「ログの送信」を参照し [てください](../../sending/using/monitoring-a-delivery.md#sending-logs)。

配信の条件に従ってアラート通知を受信する場合、考えられる理由を以下に示します。

* **[!UICONTROL Deliveries failed]**:この条件は、すべての配信のステータスを誤って知らせます。 次の原因が考えられます。

   * 配信サーバー(MTA、Message Transfer Agent)に関する問題
   * Adobe Campaign配信サーバーと受信側サーバー間の接続タイムアウト
   * 配信品質の問題
   * 誤ったワークフロー
   配信がワークフローでトリガーされた場合は、そのワークフローが正しく開始されているかどうかを確認します。 詳しくは、「ワークフローの実 [行」を参照してください](../../automating/using/executing-a-workflow.md)。 それ以外の場合は、Adobe Campaign管理者に問い合わせて問題を解決します。

* **[!UICONTROL Deliveries with preparation failed]**:配信の準備中に、次のような場合にエラーが発生する可能性があります。

   * 配信に件名がありません。
   * パーソナライゼーションフィールドに誤った構文があります。
   * ターゲットが見つかりません。
   * 配信がサイズ制限を超えています。
   詳しくは、「送信の準備」を [参照してください](../../sending/using/preparing-the-send.md)。 ただし、これらのエラーは通常、メッセージ分析中に発見されます。 制御ル [ールを参照](../../administration/using/control-rules.md)。

* アラートの原因として考えられ **[!UICONTROL Delivery with bad error ratio for soft bounces]** るのは、次のとおりです。

   * 受信者のサーバーがダウンしています。
   * 受信者のメールボックスがいっぱいです。
   詳しくは、配信ログのタ **[!UICONTROL Exclusion logs]** ブとタ **[!UICONTROL Exclusion causes]** ブを確認してください。 除外ロ [グを参照](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

   アラートの原因として考えられ **[!UICONTROL Delivery with bad error ratio for hard bounces]** るのは、次のとおりです。

   * 受信者はブラックリストに記載されています。つまり、受信者に連絡を取りたくなくなります。
   * 受信者の電子メールアドレスが存在しません。
   * 受信者のドメインが存在しません。
   * 受信者のサーバーが配信をブロックしています。
   ソフトバウンスとハードバウンスのエラーを回避するには、次のベストプラクティスに従ってください。

   * フィルタリングタイポロジルールを作成して、配信分析中にメッセージターゲットの一部（検疫済みの受信者など）を除外します。 See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * 適切な検疫管理プロセスを維持するために、顧客データベースを定期的に更新します。 「隔離につ [いて」を参照してくださ](../../sending/using/understanding-quarantine-management.md#about-quarantines)い。
   * 一般に、配信品質はできるだけ向上します。 『Adobe Campaign v7 [Managing deliveribility](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) 』詳細ガイドを参照し、Adobe Campaign管理者にお問い合わせください。



* **[!UICONTROL Deliveries with long start pending]**:通常、これは、MTA(Message Transfer Agent)レベルで問題があることを意味します。 実行プロセスが、リソースが使用可能になるのを待っています。MTA が開始されていない可能性があります。

   **[!UICONTROL Deliveries with low throughput]**:繰り返しますが、これは配信品質の問題で、MTAの速度が遅すぎます。

   これらの問題について詳しくは、Adobe Campaign管理者にお問い合わせください。

**関連トピック：**

* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [キャンペーンでのブラックリストの管理](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

