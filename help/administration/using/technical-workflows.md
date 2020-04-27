---
title: テクニカルワークフロー
description: テクニカルワークフロー は、標準搭載のワークフローで、Adobe Campaignのバックグラウンド技術プロセスを処理し、プラットフォームの正しい動作を保証します。
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# テクニカルワークフロー{#technical-workflows}

テクニカルワークフローはすぐに配信され、Adobe Campaign。 テクニカルワークフローとは、サーバー上で定期的に実行されるようにスケジュールされた操作またはジョブのことです。

データベースのメンテナンス操作を実行し、配信の追跡情報を利用して、配信の暫定ジョブを更新できます。

機能管理者は、メニューのテクニカルワークフローにアクセスで **[!UICONTROL Administration > Application settings > Workflows]** きます。

>[!NOTE]
>
>機能管理者は、テクニカルワークフローを再起動または一時停止し、プロパティと構造を変更できます。

![](assets/technical_workflows.png)

## テクニカルワークフローのリスト {#list-of-technical-workflows}

テクニカルワークフローは、セルフトリガーのバックグラウンドおよび技術的なプロセスをAdobe Campaignで処理します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>ラベル</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/Bテスト</span><br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> このワークフローは、各バリアントのトラッキングログを分析します。 A/Bテスト期間の終わりに、勝者のバリアントが自動的に計算されます。 デフォルトでは、毎日開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">請求</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> このワークフローは、システムアクティビティレポートを電子メールで「請求」ユーザーに送信します。 デフォルトでは、毎日午前1時に自動的に開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">データベースのクリーンアップ</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> このワークフローは、データベースのメンテナンスワークフローです。異なる統計とプロセスを実行し、定義された設定に従って古いデータをデータベースから削除します。 デフォルトでは、毎日午前4時に自動的に開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">予測</span><br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> このワークフローは、仮予測に格納された配信の分析（仮ログの作成）を実行します。 By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">共有オーディエンスをインポート</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience：</span> <br /> </td> 
   <td> このワークフローは、読み込まれたAdobe Experience CloudオーディエンスデータをAdobe Campaignします。 デフォルトでは、毎時開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">インスタントレポートの共有</span> (Instant Report Sharing) <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> このワークフローは、レポートの送信がスケジュールされるとすぐに開始されます。 レポートがPDFファイルに変換され、ターゲットのユーザーに電子メールで送信されます。受信者<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Adobe AnalyticsとのKPIの調整</span><br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span><br /> </td> 
   <td> このワークフローは、KPIを1日1回レポートサービスから取得し、Adobe Analyticsのデータと調整します。 必要に応じて、差が押し出されます。 By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">NMACオプトアウトの管理</span><br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> このワークフローは、購読解除をモバイルデバイスの通知に更新します。 デフォルトでは、午前1時から午前0時の間に6時間ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Message Center のローカルアーカイブ</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> このワークフローは、リアルタイムイベントを履歴テーブルにアーカイブします。 デフォルトでは、毎時開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">レポート集計</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> このワークフローは、レポートで使用される集計を更新します。 デフォルトでは、午前2時に自動的に開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPIをAdobe Analyticsと共有</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> このワークフローは、KPIデータをAdobe StandardからAdobe Analyticsに15分ごとにAdobe Campaignします。<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">起動と同期</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> このワークフローは、Adobe Standardで読み込まれたAdobe LaunchモバイルプロパティをAdobe Campaignします。 15分ごとに開始されます。<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">更新配信の実行</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> このワークフローは、配信の追跡を更新します。 デフォルトでは、10分ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信指標の更新</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> このワークフローは、配信のKPI（主要業績評価指標）を更新します。 デフォルトでは、毎時開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">イベントステータスを更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> このワークフローを使用すると、ステータスをワークフローに属性付けすることができます。イベント 次のイベントステータスを使用できます。<br /><strong>保留</strong>:イベントはキューに入っています。 イベントにはまだメッセージテンプレートが割り当てられていません。<br /> 保留 <span class="uicontrol">配信</span> :イベントはキューにあり、メッセージテンプレートが割り当てられ、メッセージによって処理されています。配信<br /> 送 <strong>信</strong>:このステータスは、配信ログからコピーされます。 それは配信が送られた。<br /> 無視 <strong>配信</strong>:このステータスは、配信ログからコピーされます。 配信が無視されたことを意味しています。<br /> <strong>配信</strong>:このステータスは、配信ログからコピーされます。 配信が失敗したことを意味しています。<br /> <span class="uicontrol">イベントが考慮されない</span> :イベントをメッセージテンプレートにリンクできませんでした。 イベントの処理はおこなわれません。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信品質の更新</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> このワークフローを使用すると、バウンスルールの資格ルールのリストと、プラットフォーム内のドメインとMXのリストを作成できます。 このワークフローは、HTTPSが開いている場合にのみ機能します。 デフォルトでは、午前2時に自動的に開始されます。<br /> </td> 
  </tr> 
 </tbody> 
</table>

