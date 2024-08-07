---
title: テクニカルワークフロー
description: テクニカルワークフローの詳細情報
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: f87795ee2378a1e9e1b393c6cce002bcb70178b8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 75%

---

# テクニカルワークフロー{#technical-workflows}

テクニカルワークフローは、Adobe Campaign に標準搭載されています。テクニカルワークフローは、サーバー上で定期的に実行されるようにスケジュールされた処理またはジョブです。

データベースの保守作業を実行し、配信の追跡情報を利用して、配信上の仮ジョブを更新できます。

機能管理者は、**[!UICONTROL Administration > Application settings > Workflows]** メニューからテクニカルワークフローにアクセスできます。

>[!NOTE]
>
>機能管理者は、テクニカルワークフローを再起動または一時停止したり、プロパティと構造を変更することができます。

![](assets/technical_workflows.png)

## テクニカルワークフローのリスト {#list-of-technical-workflows}

テクニカルワークフローは、Adobe Campaign でセルフトリガーのバックグラウンドプロセスと技術的プロセスの処理に使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>ラベル</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B テスト</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> このワークフローは、各バリアントのトラッキングログを分析します。A/B テスト期間の終了時に、最も効果が高いバリアントを自動的に計算します。デフォルトでは、毎日実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">請求</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> システムアクティビティレポートを「請求」ユーザーにメールで送信します。デフォルトでは、毎日午前 1 時に自動的に実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> 配信テンプレートからヘッダーをコピー </span> <br /> </td> 
   <td> <span class="uicontrol">smtpHeaderupdate</span> <br /> </td> 
   <td> このワークフローは、メール配信テンプレート用に設定された SMTP ヘッダーを、テンプレート以外の対応する子配信にコピーします。 このワークフローでピックアップされるのは、メールマーケティング配信のみです。 SMTP ヘッダーは、トランザクション配信と配達確認配信にはコピーされません。 <br> このワークフローは定期的に実行されません。 ユーザーが使用ごとに開始する必要があります。 <!--So it'not really a technical workflow like all workflows on this page, because it's not run automatically - TBC--> <br> インスタンスに大量の配信がある場合は、<strong> アプリケーション設定 </strong> の NmsCleanup_DeliveryPurgeDelay オプションを更新できます。 任意のテンプレートの SMTP ヘッダーに変更を加えた場合は、変更後にワークフローを再実行して、修正したヘッダーがテンプレート以外の配信にコピーされるようにする必要があります。<a href="data-retention.md#deliveries"> 詳細情報 </a>
   <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">データベースのクリーンアップ</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> このワークフローは、データベースのメンテナンスワークフローです。各種の統計とプロセスを実行し、定義された設定に従って、古いデータをデータベースから削除します。デフォルトでは、毎日午前 4 時に自動的に実行されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">共有オーディエンスのインポート</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> このワークフローは、Adobe Campaign にインポートされた Adobe Experience Cloud オーディエンスデータを同期します。デフォルトでは、1 時間ごとに実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時レポート共有</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> このワークフローは、レポートの送信がスケジュールされるとすぐに実行されます。レポートは PDF ファイルに変換され、ターゲットの受信者にメールで送信されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI と Adobe Analytics との紐付け</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> このワークフローは、レポートサービスから KPI を 1 日 1 回取得し、Adobe Analytics のデータと紐付けます。必要に応じて差異がプッシュされます。デフォルトでは、毎週月曜日の午前 4 時にトリガーされます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Message Center のローカルアーカイブ</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> このワークフローは、リアルタイムイベントを履歴テーブルにアーカイブします。デフォルトでは、1 時間ごとに実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">レポート集計</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> レポートで使用される集計を更新します。デフォルトでは、午前 2 時に自動的に実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI を Adobe Analytics と共有</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> このワークフローは、KPI データを Adobe Campaign Standard から Adobe Analytics に 15 分ごとにプッシュします。<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Launch と同期</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> このワークフローでは、Adobe Campaign Standardに読み込まれたタグモバイルプロパティを同期します。 これは 15 分ごとに実行されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol"> トラッキングログの回復 </span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> このワークフローでは、Adobe Campaign Standardに読み込まれたタグモバイルプロパティを同期します。 これは 15 分ごとに実行されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol"> トラッキングログの復元 </span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> このワークフローは、失われたトラッキングログを復元します。 このテクニカルワークフローは特定のコンテキストで使用され、Adobe内部での使用のみに制限されます。 <br> デフォルトでは、10 分ごとに開始されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">配信実行情報の更新</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> このワークフローは、broadlog とトラッキングログをローカルデータベースにコピーします。 デフォルトでは、10 分ごとに実行されます。<br/> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">配信インジケーターの更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> このワークフローは、配信の KPI（主要業績評価指標）を更新します。デフォルトでは、1 時間ごとに実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">イベントステータスを更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> このワークフローでは、ステータスをイベントに関連付けることができます。次のイベントステータスを使用できます。<br /> <strong>保留</strong>：イベントはキューに入っています。イベントにはまだメッセージテンプレートが割り当てられていません。<br /><span class="uicontrol">配信待ち</span>：イベントはキューに入っていて、メッセージテンプレートが割り当てられ、配信による処理中です。<br /><strong>送信済み</strong>：このステータスは配信ログからコピーされます。これは配信が送信されたことを意味しています。<br /><strong>配信で無視</strong>：このステータスは配信ログからコピーされます。これは配信が無視されたことを意味しています。<br /><strong>配信に失敗</strong>：このステータスは配信ログからコピーされます。これは配信が失敗したことを意味しています。<br /><span class="uicontrol">処理不可なイベント</span>：イベントをメッセージテンプレートにリンクすることができませんでした。イベントの処理はおこなわれません。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信品質の更新</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> バウンスルールの選定ルールのリスト、ドメインのリスト、プラットフォームの MX のリストを作成できます。このワークフローは、HTTPS が開かれている場合にのみ機能します。デフォルトでは、午前 2 時に自動的に実行されます。<br /> </td> 
  </tr> 
 </tbody> 
</table>
