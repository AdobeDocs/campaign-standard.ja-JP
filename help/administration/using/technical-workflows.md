---
title: 技術ワークフロー
seo-title: 技術ワークフロー
description: 技術ワークフロー
seo-description: 技術ワークフローは、Adobe Campaignのバックグラウンド技術プロセスを処理するために設計された、あらかじめ用意されたワークフローで、プラットフォームの適切な動作を保証します。
page-status-flag: 常にアクティブ化されていない
uuid: 6e763dc1- e1d3-4d94- bc0b- ef5b1703d8e5
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: アプリケーション設定
discoiquuid: e9f147bd-6a5b-4b82- b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2541b6dadd005c74d6bb737a0e3692e63a5b85db

---


# Technical workflows{#technical-workflows}

技術ワークフローはAdobe Campaignであらかじめ提供されています。技術ワークフローは、サーバーに基づいて定期的に実行されるようにスケジュールされた操作またはジョブです。

データベースのメンテナンス操作を実行したり、配信の追跡情報を利用したり、配信の暫定ジョブを更新したりできます。

Functional administrators can access technical workflows under the **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>機能管理者は、技術的なワークフローを再起動または一時停止し、そのプロパティと構造を変更できます。

![](assets/technical_workflows.png)

## List of technical workflows {#list-of-technical-workflows}

技術ワークフローは、Adobe Campaignで自己トリガーのバックグラウンドおよび技術プロセスを処理するために使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>ラベル</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/Bテスト</span><br /> </td> 
   <td> <span class="uicontrol">abtesting</span><br /> </td> 
   <td> このワークフローでは、各バリアントのトラッキングログを分析します。A/Bテスト期間の終わりに、自動的に勝者のバリエーションが計算されます。By default, it is started every day.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">請求</span><br /> </td> 
   <td> <span class="uicontrol">請求</span><br /> </td> 
   <td> このワークフローでは、システムアクティビティレポートが「請求先」ユーザーに電子メールで送信されます。By default, it is automatically started every day at 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">データベースのクリーンアップ</span><br /> </td> 
   <td> <span class="uicontrol">クリーンアップ</span><br /> </td> 
   <td> このワークフローは、データベースの管理ワークフローです。これは異なる統計とプロセスを実行し、定義された設定に従ってデータベースから古いデータを削除します。By default, it is automatically started every day 4am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">予測</span><br /> </td> 
   <td> <span class="uicontrol">予測</span><br /> </td> 
   <td> このワークフローでは、暫定予測に保存された配信の分析を実行します（暫定ログの作成）。By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">共有オーディエンスのインポート</span><br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> このワークフローにより、Adobe CampaignでインポートされたAdobe Experience Cloudオーディエンスデータが同期されます。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時レポート共有</span><br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> このワークフローは、レポートの送信がスケジュールされるとすぐに開始されます。It converts your report into a pdf file then sends it in an email to the targeted recipients.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI紐付けとAdobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kp紐紐付け</span><br /> </td> 
   <td> このワークフローでは、レポートサービスからKPIを1日に1回取得し、Adobe Analyticsのデータに調整します。その後、必要に応じて差をプッシュします。By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">NMACオプトアウトの管理</span><br /> </td> 
   <td> <span class="uicontrol">mobileAPPOutputOutMgt</span><br /> </td> 
   <td> このワークフローは、モバイルデバイスで通知の購読を解除します。By default, it is started every 6 hours between 1am and midnight.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Message Centerローカルアーカイブ</span><br /> </td> 
   <td> <span class="uicontrol">McSync_ local</span><br /> </td> 
   <td> このワークフローでは、リアルタイムイベントを履歴テーブルにアーカイブします。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">レポートの集計</span><br /> </td> 
   <td> <span class="uicontrol">reportAggregations</span><br /> </td> 
   <td> このワークフローにより、レポートで使用される集計が更新されます。By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPIをAdobe Analyticsと共有</span><br /> </td> 
   <td> <span class="uicontrol">KpSharing</span><br /> </td> 
   <td> This workflow pushes KPI data every 15 minutes from Adobe Campaign Standard to Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信の更新の更新</span><br /> </td> 
   <td> <span class="uicontrol">UpdateDeliveryExecInfo</span><br /> </td> 
   <td> このワークフローにより、配信の追跡が更新されます。By default, it is started every 10 minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信インジケータの更新</span><br /> </td> 
   <td> <span class="uicontrol">UpdateDeliveryIndicators</span><br /> </td> 
   <td> このワークフローは、配信のKPI（主要業績評価指標）を更新します。By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">イベントステータスの更新</span><br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> このワークフローにより、ステータスをイベントに関連付けることができます。The following event statuses are available:<br /> <strong>Pending</strong>: The event is in a queue. まだメッセージテンプレートが割り当てられていません。<br /><span class="uicontrol">保留中の配信</span> :イベントがキューにあり、メッセージテンプレートが割り当てられており、配信によって処理中です。<br /><strong>送信</strong>済み:このステータスは配信ログからコピーされます。これは配信が送信されたことを意味します。<br /><strong>配信では無視</strong>:このステータスは配信ログからコピーされます。つまり、配信は無視されます。<br /><strong>配信失敗</strong>:このステータスは配信ログからコピーされます。これは、配信に失敗したことを意味します。<br /><span class="uicontrol">イベントは考慮</span> されません。イベントをメッセージテンプレートにリンクできませんでした。The event will not be processed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信品質の更新</span><br /> </td> 
   <td> <span class="uicontrol">DeliverabilityUpdate</span><br /> </td> 
   <td> このワークフローにより、バウンスルールの選定ルールのリストと、プラットフォーム内のドメインとMXのリストを作成できます。このワークフローは、HTTPSが開いている場合にのみ機能します。By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
 </tbody> 
</table>

