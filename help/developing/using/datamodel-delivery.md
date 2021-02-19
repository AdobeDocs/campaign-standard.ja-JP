---
solution: Campaign Standard
product: campaign
title: DataModel
description: データモデルについて
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 26%

---


# 配信(nms:配信)

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
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>メインリソースID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B テスト</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advanced</td>
                  <td>詳細配信</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>詳細設定パラメーター</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Adobe Experience Manager内容</td>
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
                  <td>警告の種類</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>attachment</td>
                  <td>添付ファイル</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>ブランド</td>
                  <td>link </td>
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
                  <td>組み込みアプリケーションオブジェクト</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>キャンペーン(campaignBase)</td>
                  <td>キャンペーン</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Adobe Experience Manager勘定</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>commands</td>
                  <td>コマンド</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>content</td>
                  <td>コンテンツ</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>コンテンツソース</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager- aem - 1</li>
                        <li>Adobe Campaign-キャンペーン- 0</li>
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
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>配信モード</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>バルク配信 — バルク — 1</li>
                        <li>ミッドソーシング- midSourcing - 4</li>
                        <li>説明 — 説明 — 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>外部 — 外部 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Routing</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>電子メールプレビュー</td>
                  <td>item </td>
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
                  <td>執行</td>
                  <td>配信実行パラメーター</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>実行タイプ</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>一意 — oneTime - 0</li>
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
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>添付ファイルを追加</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icon</td>
                  <td>アイコン</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>トランザクション用電子メール — emailLightning - 60</li>
                        <li>ファックス — FAX - 4</li>
                        <li>モバイル(SMS) - sms - 1</li>
                        <li>定期的な電子メール — emailRefresh - 30</li>
                        <li>ダイレクトメール — 用紙 — 3</li>
                        <li>電話 — 電話 — 2</li>
                        <li>その他 — その他 — 120</li>
                        <li>定期的なSMS - smsRefresh - 31</li>
                        <li>モバイルアプリケーション — pushNotification - 40</li>
                        <li>トランザクションSMS - smsLightning - 61</li>
                        <li>電子メール — 電子メール — 0</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソース</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>マスター</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>テンプレート</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>反復</td>
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
                  <td>kpi</td>
                  <td>指標</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>ラベル</td>
                  <td>文字列(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>最終変更日時</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>実行ステータス</td>
                  <td>定義済みリスト（文字列） (255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 開始 — 開始</li>
                        <li>編集 — エディション — エディション</li>
                        <li>終了 — 終了 — 終了</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>エラー — エラー — エラー</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>E メールヘッダーのパラメーター</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日付</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>マッピング(deliveryMapping)</td>
                  <td>ターゲットマッピング</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>マスターインスタンス</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>マスター指標</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>チャネル</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>ファックス — FAX - 4</li>
                        <li>モバイル(SMS) - sms - 1</li>
                        <li>電子メール — 電子メール — 0</li>
                        <li>電話 — 電話 — 2</li>
                        <li>ダイレクトメール — 用紙 — 3</li>
                        <li>モバイルアプリケーション — pushNotification - 40</li>
                        <li>その他 — その他 — 120</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>変更者</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>文字列(64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>オファー管理</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>組織単位</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent(deliveryBase)</td>
                  <td>親配信</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>優先度</td>
                  <td>配信の優先順位</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>高 — 高 — 20</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>標準 — 標準 — 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>プログラム(programBase)</td>
                  <td>プログラム</td>
                  <td>link </td>
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
                  <td>プッシュ通知プレビュー</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>PushNotificationパラメーター</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>リアルタイムレポート</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>リソースのバージョン</td>
                  <td>文字列(255)</td>
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
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>スケジュール</td>
                  <td>配信のスケジュール</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>SMS パラメーター</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>SMSプレビュー</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>ステータス</td>
                  <td>定義済みリスト（バイト） </td>
                  <td>
                     <ul>
                        <li>保留中の開始- startPending - 51</li>
                        <li>配信準備完了 — 準備完了 — 45</li>
                        <li>再試行保留中 — retryPending - 61</li>
                        <li>再試行中 — retryInProgress - 62</li>
                        <li>失敗 — 失敗 — 87</li>
                        <li>進行中 — 開始済み — 55</li>
                        <li>ターゲット設定の保留中 — targetPrepPending - 11</li>
                        <li>パーソナライゼーション保留 — messagePrepPending - 21</li>
                        <li>一時停止 — 一時停止 — 75</li>
                        <li>編集中 — エディション — 0</li>
                        <li>終了 — 終了 — 95</li>
                        <li>カウント中 — targetSelection - 12</li>
                        <li>メッセージが確定されました — messageReady - 25</li>
                        <li>パーソナライゼーションまたはカウントに失敗しました — preparationError - 37</li>
                        <li>停止 — キャンセル済 — 85</li>
                        <li>パーソナライゼーションが進行中 — messagePreparation - 22</li>
                        <li>ターゲット準備完了 — targetReady - 15</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>調停中 — targetArbitation - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>ターゲット</td>
                  <td>配信ターゲット母集団</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>配信テンプレート</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>配信サムネール</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>配信</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>トラッキングパラメーター</td>
                  <td>item </td>
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
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイポロジ（タイポロジベース）</td>
                  <td>タイポロジ</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>ターゲティングワークフロー</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>ワークフローの状態</td>
                  <td>定義済みリスト（文字列） (255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 開始 — 開始</li>
                        <li>編集 — エディション — エディション</li>
                        <li>終了 — 終了 — 終了</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>エラー — エラー — エラー</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## フィルター

チャネルタイプ別(byChannel)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>チャネル</td>
    <td>定義済みリスト</td>
    </tr>
</table>

実行タイプ別(byExecutionType)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>定義済みリスト</td>
    </tr>
</table>

論理ステータス(byLogicalStatus)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>state</td>
    <td>定義済みリスト</td>
    </tr>
</table>

名前またはラベル別(byText)

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

期間別(ByStartPeriod)

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

発行ステータス別(byPublicationStatus)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>定義済みリスト</td>
    </tr>
</table>

ステータス別(byState)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>state</td>
    <td>定義済みリスト</td>
    </tr>
</table>

フォローアップメッセージ(showFollowup)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>フォローアップ</td>
    <td>boolean</td>
    </tr>
</table>

高度な配信を含める(withAdvanced)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>advanced</td>
    <td>boolean</td>
    </tr>
</table>

異種リストからの連続配信を含める（連続）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>boolean</td>
    </tr>
</table>

配達確認を含める（FCPを含む）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>（FCPを使用）</td>
    <td>boolean</td>
    </tr>
</table>

指定期間中に計画(byPlanning)

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

特定の期間(byCalendar)に存在する

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

標準搭載の状態で表示(showOob)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>オーブ</td>
    <td>boolean</td>
    </tr>
</table>