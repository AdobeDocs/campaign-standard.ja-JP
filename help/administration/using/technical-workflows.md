---
title: テクニカルワークフロー
description: 技術ワークフローは、Adobe Campaignのバックグラウンド技術プロセスを処理し、プラットフォームの正しい動作を保証するために設計された、すぐに使えるワークフローです。
page-status-flag: 非活性化の
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# テクニカルワークフロー{#technical-workflows}

技術ワークフローは、Adobe Campaignと共にそのまま使用できます。 技術ワークフローとは、サーバー上で定期的に実行されるようにスケジュールされた操作またはジョブのことです。

データベースのメンテナンス操作、配信での追跡情報の利用、配信での暫定ジョブの更新を行うことができます。

機能管理者は、メニューの下の技術ワークフローにアクセス **[!UICONTROL Administration > Application settings > Workflows]** できます。

>[!NOTE]
>
>機能管理者は、技術ワークフローを再起動または一時停止し、プロパティと構造を変更できます。

![](assets/technical_workflows.png)

## テクニカルワークフローのリスト {#list-of-technical-workflows}

技術ワークフローは、Adobe Campaignのセルフトリガーによるバックグラウンドおよび技術プロセスを処理するために使用されます。

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
   <td> <span class="uicontrol">請求</span><br /> </td> 
   <td> <span class="uicontrol">請求</span><br /> </td> 
   <td> このワークフローは、システムアクティビティレポートを「請求」ユーザーに電子メールで送信します。 デフォルトでは、毎日午前1時に自動的に開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">データベースのクリーンアップ</span> <br /> </td> 
   <td> <span class="uicontrol">浄化</span><br /> </td> 
   <td> このワークフローは、データベースメンテナンスワークフローです。異なる統計とプロセスを実行し、定義された設定に従って古いデータをデータベースから削除します。 デフォルトでは、毎日午前4時に自動的に開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">予測</span><br /> </td> 
   <td> <span class="uicontrol">予測</span><br /> </td> 
   <td> このワークフローは、仮予測に保存された配信の分析（仮ログの作成）を実行します。 By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">共有オーディエンスをインポート</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> このワークフローは、Adobe Campaignに読み込まれたAdobe Experience cloudオーディエンスデータを同期します。 デフォルトでは、1時間ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">即時レポート共有</span><br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> このワークフローは、レポートの送信がスケジュールされるとすぐに開始されます。 レポートがPDFファイルに変換され、ターゲットの受信者に電子メールで送信されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Adobe AnalyticsとのKPI調整</span><br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span><br /> </td> 
   <td> このワークフローは、1日に1回ReportingサービスからKPIを取得し、Adobe Analyticsのデータと調整します。 必要に応じて差が押し出されます。 By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">NMACオプトアウトの管理</span><br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span><br /> </td> 
   <td> このワークフローは、モバイルデバイスの通知の購読解除を更新します。 デフォルトでは、午前1時から午前0時の間に6時間ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Message Center のローカルアーカイブ</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> このワークフローは、リアルタイムイベントを履歴テーブルにアーカイブします。 デフォルトでは、1時間ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">レポート集計</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span><br /> </td> 
   <td> このワークフローは、レポートで使用される集計を更新します。 デフォルトでは、午前2時に自動的に開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPIをAdobe Analyticsと共有</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> このワークフローは、Adobe Campaign StandardからAdobe Analyticsに15分ごとにKPIデータをプッシュします。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信の実行の更新</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> このワークフローは、配信の追跡を更新します。 デフォルトでは、10分ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信指標の更新</span><br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> このワークフローは、配信のKPI（主要業績評価指標）を更新します。 デフォルトでは、1時間ごとに開始されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">イベントステータスを更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> このワークフローでは、ステータスをイベントに属性付けできます。 <br /> 次のイベントステータスを使用できます。 <strong>保留</strong>:イベントがキューに入っています。 イベントにはまだメッセージテンプレートが割り当てられていません。<br /> <span class="uicontrol">配信保留</span> :イベントがキューにあり、メッセージテンプレートが割り当てられ、配信によって処理されています。<br /> <strong>送信</strong>:このステータスは配信ログからコピーされます。 配信が送信されたことを意味します。<br /> 配 <strong>信で無視</strong>:このステータスは配信ログからコピーされます。 配信が無視されたことを意味しています。<br /> 配 <strong>信失敗</strong>:このステータスは配信ログからコピーされます。 配信が失敗したことを意味しています。<br /> イベ <span class="uicontrol">ントが考慮されません</span> :イベントをメッセージテンプレートにリンクできませんでした。 イベントの処理はおこなわれません。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">配信品質の更新</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span><br /> </td> 
   <td> このワークフローでは、バウンスルールの資格ルールのリストと、プラットフォーム内のドメインとMXのリストを作成できます。 このワークフローは、HTTPSが開いている場合にのみ機能します。 デフォルトでは、午前2時に自動的に開始されます。<br /> </td> 
  </tr> 
 </tbody> 
</table>

