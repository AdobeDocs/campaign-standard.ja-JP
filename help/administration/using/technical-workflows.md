---
title: テクニカルワークフロー
description: テクニカルワークフローの詳細を説明します
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 93%

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
   <td> <span class="uicontrol">データベースのクリーンアップ</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> このワークフローは、データベースのメンテナンスワークフローです。各種の統計とプロセスを実行し、定義された設定に従って、古いデータをデータベースから削除します。デフォルトでは、毎日午前 4 時に自動的に実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">予測</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> このワークフローは、暫定予測に保存されている配信の分析を実行します（暫定ログの作成）。デフォルトでは、毎週月曜日の午前 1 時に実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">共有オーディエンスのインポート</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> このワークフローは、Adobe Campaign にインポートされた Adobe Experience Cloud オーディエンスデータを同期します。デフォルトでは、1 時間ごとに実行されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時レポート共有</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> このワークフローは、レポートの送信がスケジュールされるとすぐに実行されます。レポートは PDF ファイルに変換され、ターゲットの受信者に電子メールで送信されます。<br /> </td> 
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
   <td> このワークフローは、Adobe Campaign Standard にインポートした Adobe Experience Platform Launch のモバイルプロパティを同期します。これは 15 分ごとに実行されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">トラッキングログの復元</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> このワークフローは、Adobe Campaign Standard にインポートした Adobe Experience Platform Launch のモバイルプロパティを同期します。これは 15 分ごとに実行されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">トラッキングログを復元</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> このワークフローは、失われたトラッキングログを復元します。 このテクニカルワークフローは、特定のコンテキストで使用され、Adobe内部での使用のみに制限されます。 <br>デフォルトでは、10 分ごとに実行されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">配信実行情報の更新</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> このワークフローは、broadLog とトラッキングログをローカルデータベースにコピーします。 デフォルトでは、10 分ごとに実行されます。<br/> </td> 
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
