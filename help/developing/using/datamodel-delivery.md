---
title: DataModel 配信
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 33%

---

# 配信 (nms:delivery)

## オブジェクトの説明

<table>
               <tr>
                  <th>名前</th>
                  <th>ラベル</th>
                  <th>タイプ（長さ）</th>
                  <th>列挙値</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>配達確認</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>メインリソース ID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B テスト</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>詳細</td>
                  <td>高度な配信</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>詳細設定パラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Adobe Experience Managerコンテンツ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>警告メッセージ</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>警告タイプ</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>添付</td>
                  <td>添付ファイル</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ブランディング (brandingBase)</td>
                  <td>ブランド</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>配信ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>アプリケーションのビルトインオブジェクト</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>キャンペーン (campaignBase)</td>
                  <td>キャンペーン</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Adobe Experience Managerアカウント</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>コマンド</td>
                  <td>コマンド</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>content</td>
                  <td>コンテンツ</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>コンテンツソース</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign — キャンペーン — 0</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>リソースタイプ</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>作成日時</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>作成者</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>配信モード</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>一括配信 — 一括 — 1</li>
                        <li>ミッドソーシング — midSourcing - 4</li>
                        <li>説明 — 説明 — 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>外部 — 外部 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>ルーティング</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列 (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>E メールのプレビュー</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>除外ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>除外</td>
                  <td>除外の原因</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>実行</td>
                  <td>配信実行パラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>実行タイプ</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>ユニーク — oneTime - 0</li>
                        <li>連続 — 連続 — 1</li>
                        <li>Message Center - messageCenter - 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>ForecastLog</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理的単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>添付ファイルを追加</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>アイコン</td>
                  <td>アイコン</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>トランザクションメール — emailLightning - 60</li>
                        <li>FAX - FAX - 4</li>
                        <li>モバイル (SMS) - sms - 1</li>
                        <li>繰り返し E メール — emailRefresh - 30</li>
                        <li>ダイレクトメール — 紙 — 3</li>
                        <li>電話 — 電話 — 2</li>
                        <li>その他 — 120</li>
                        <li>繰り返し送信 SMS - smsRefresh - 31</li>
                        <li>モバイルアプリケーション — pushNotification - 40</li>
                        <li>トランザクション SMS - smsLightning - 61</li>
                        <li>電子メール — 電子メール — 0</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソースです</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>マスター</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>テンプレート</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>繰り返し</td>
                  <td>配信</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ジョブ</td>
                  <td>ジョブ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpis</td>
                  <td>指標</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>ラベル</td>
                  <td>文字列 (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>最終変更日</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>実行ステータス</td>
                  <td>enumeration（文字列） (255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 開始 — 開始済み</li>
                        <li>編集 — エディション — エディション</li>
                        <li>完了 — 完了 — 終了</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>エラー — エラー — エラー</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>E メールヘッダーのパラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日付</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>マッピング (deliveryMapping)</td>
                  <td>ターゲットマッピング</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>マスター (deliveryBase)</td>
                  <td>マスターインスタンス</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>マスター指標</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>チャネル</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>FAX - FAX - 4</li>
                        <li>モバイル (SMS) - sms - 1</li>
                        <li>電子メール — 電子メール — 0</li>
                        <li>電話 — 電話 — 2</li>
                        <li>ダイレクトメール — 紙 — 3</li>
                        <li>モバイルアプリケーション — pushNotification - 40</li>
                        <li>その他 — 120</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>変更者</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>文字列 (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>オファー管理</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>組織単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>親 (deliveryBase)</td>
                  <td>親配信</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>優先度</td>
                  <td>配信の優先順位</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>高 — 高 — 20</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>標準 — 標準 — 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>プログラム (programBase)</td>
                  <td>プログラム</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>配達確認</td>
                  <td>配達確認</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>プッシュ通知のプレビュー</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>PushNotification パラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>リアルタイムレポート</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>リソースのバージョン</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>リボンメッセージ</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>シナリオ</td>
                  <td>配信テンプレートのパラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>スケジューリング</td>
                  <td>配信のスケジュール</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>SMS パラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>SMS プレビュー</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>ステータス</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>開始保留中 — startPending - 51</li>
                        <li>配信準備完了 — 準備完了 — 45</li>
                        <li>再試行待ち — retryPending - 61</li>
                        <li>再試行中 — retryInProgress - 62</li>
                        <li>失敗 — 失敗 — 87</li>
                        <li>処理中 — 開始 — 55</li>
                        <li>ターゲティングを保留中 — targetPrepPending - 11</li>
                        <li>パーソナライゼーション保留中 — messagePrepPending - 21</li>
                        <li>一時停止 — 一時停止 — 75</li>
                        <li>編集 — エディション — 0</li>
                        <li>完了 — 完了 — 95</li>
                        <li>カウント中 — targetSelection - 12</li>
                        <li>確定されたメッセージ — messageReady - 25</li>
                        <li>パーソナライゼーションまたはカウントに失敗しました — preparationError - 37</li>
                        <li>停止 — キャンセル — 85</li>
                        <li>パーソナライゼーション中 — messagePreparation - 22</li>
                        <li>ターゲット準備完了 — targetReady - 15</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>判別中 — targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>ターゲット</td>
                  <td>配信ターゲット母集団</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>配信テンプレート</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>配信のサムネール</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>配信</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>トラッキングパラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>トラッキングログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>トラッキングされる URL</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>トランザクションメッセージのパラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイポロジ (typologyBase)</td>
                  <td>タイポロジ</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ワークフロー (workflowBase)</td>
                  <td>ターゲティングワークフロー</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>ワークフローステータス</td>
                  <td>enumeration（文字列） (255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 開始 — 開始済み</li>
                        <li>編集 — エディション — エディション</li>
                        <li>完了 — 完了 — 終了</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>エラー — エラー — エラー</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## フィルター

チャネルタイプ別 (byChannel)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>チャネル</td>
    <td>列挙</td>
    </tr>
</table>

実行タイプ別 (byExecutionType)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>列挙</td>
    </tr>
</table>

論理ステータス別 (byLogicalStatus)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>state</td>
    <td>列挙</td>
    </tr>
</table>

名前別またはラベル別（テキスト別）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>テキスト</td>
    <td>文字列</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>文字列</td>
    </tr>
</table>

期間別（期間別）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>文字列</td>
    </tr>
</table>

期間別 (byStartPeriod)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>文字列</td>
    </tr>
</table>

公開ステータス別 (byPublicationStatus)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>列挙</td>
    </tr>
</table>

ステータス別（状態別）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>state</td>
    <td>列挙</td>
    </tr>
</table>

フォローアップメッセージ (showFollowup)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>フォローアップ</td>
    <td>ブール値</td>
    </tr>
</table>

高度な配信を含める（詳細設定を使用）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>詳細</td>
    <td>ブール値</td>
    </tr>
</table>

異種のリスト (withContinuous) からの連続配信を含める

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>ブール値</td>
    </tr>
</table>

配達確認を含める（FCP を使用）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>FCP を使用</td>
    <td>ブール値</td>
    </tr>
</table>

指定した期間 (byPlanning) に計画済み

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

指定された期間 (byCalendar) に存在

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

標準で表示 (showOob)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>大きな</td>
    <td>ブール値</td>
    </tr>
</table>
