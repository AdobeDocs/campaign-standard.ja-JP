---
title: データモデル配信
description: データモデルについて説明します
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 29%

---

# 配信（nms:delivery）

## オブジェクトの説明

<table>
               <tr>
                  <th>名前</th>
                  <th>ラベル</th>
                  <th>タイプ （長さ）</th>
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
                  <td>アドバンス配信</td>
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
                  <td>Adobe Experience Manager コンテンツ</td>
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
                  <td>attachment</td>
                  <td>添付ファイル</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ブランディング （brandingBase）</td>
                  <td>ブランド</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLog</td>
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
                  <td>campaign （campaignBase）</td>
                  <td>キャンペーン</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount （extAccountAEMBase）</td>
                  <td>Adobe Experience Manager アカウント</td>
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
                  <td>コンテンツ</td>
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
                        <li>Adobe Campaign- キャンペーン - 0</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
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
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy （userBase）</td>
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
                        <li>一括配信 – 一括 – 1</li>
                        <li>ミッドソーシング – ミッドソーシング - 4</li>
                        <li>説明 – 説明 – 2</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                        <li>外部 – 外部 – 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider （extAccountBase）</td>
                  <td>ルーティング</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>降順</td>
                  <td>説明</td>
                  <td>文字列（512）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>メールのプレビュー</td>
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
                  <td>除外数</td>
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
                        <li>一意 – oneTime - 0</li>
                        <li>連続 – 連続 – 1</li>
                        <li>Message Center - messageCenter - 2</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
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
                  <td>geoUnit （geoUnitBase）</td>
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
                        <li>トランザクションメール - emailLightning - 60</li>
                        <li>FAX 番号 – 4</li>
                        <li>モバイル （SMS） - sms - 1</li>
                        <li>繰り返しメール - emailRefresh - 30</li>
                        <li>ダイレクトメール – 紙 – 3</li>
                        <li>電話 – 電話 – 2</li>
                        <li>その他 – その他 – 120</li>
                        <li>繰り返し SMS - smsRefresh - 31</li>
                        <li>モバイルアプリケーション - pushNotification - 40</li>
                        <li>トランザクション SMS - smsLightning - 61</li>
                        <li>電子メール – 電子メール - 0</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソース</td>
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
                  <td>jobLog</td>
                  <td>ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpi</td>
                  <td>指標</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ラベル</td>
                  <td>ラベル</td>
                  <td>文字列（128）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>最終変更日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>実行ステータス</td>
                  <td>列挙（文字列） （255）</td>
                  <td>
                     <ul>
                        <li>処理中 – 開始 – 開始</li>
                        <li>編集 – エディション – エディション</li>
                        <li>完了 – 完了 – 完了</li>
                        <li>警告 – 警告 – 警告</li>
                        <li>エラー – エラー – エラー</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>メールヘッダーのパラメーター</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日付</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>マッピング（deliveryMapping）</td>
                  <td>ターゲットマッピング</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>マスター（deliveryBase）</td>
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
                        <li>FAX 番号 – 4</li>
                        <li>モバイル （SMS） - sms - 1</li>
                        <li>電子メール – 電子メール - 0</li>
                        <li>電話 – 電話 – 2</li>
                        <li>ダイレクトメール – 紙 – 3</li>
                        <li>モバイルアプリケーション - pushNotification - 40</li>
                        <li>その他 – その他 – 120</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy （userBase）</td>
                  <td>変更者</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>文字列（64）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>オファー管理</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit （orgUnitBase）</td>
                  <td>組織単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>親（deliveryBase）</td>
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
                        <li>高 – 高 – 20</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                        <li>法線 – 法線 – 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>プログラム（programBase）</td>
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
                  <td>文字列（255）</td>
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
                  <td>スケジュール</td>
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
                  <td>都道府県</td>
                  <td>ステータス</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>開始保留中 – startPending - 51</li>
                        <li>配信準備完了 – 準備完了 – 45</li>
                        <li>再試行待ち – retryPending - 61</li>
                        <li>再試行中 – retryInProgress - 62</li>
                        <li>失敗 – 失敗 – 87</li>
                        <li>処理中 – 開始 – 55</li>
                        <li>ターゲティング保留中 – targetPrepPending - 11</li>
                        <li>Personalization保留中 – messagePrepPending - 21</li>
                        <li>一時停止 – 一時停止 – 75</li>
                        <li>編集中 – エディション - 0</li>
                        <li>終了 – 終了 – 95</li>
                        <li>カウント中 – targetSelection - 12</li>
                        <li>メッセージが最終処理されました – messageReady - 25</li>
                        <li>Personalizationまたはカウントに失敗しました – preparationError - 37</li>
                        <li>中止 – 取り消し – 85</li>
                        <li>Personalization中 – messagePreparation - 22</li>
                        <li>ターゲット準備完了 – targetReady - 15</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                        <li>判別中 – targetArbitration - 13</li>
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
                  <td>テンプレート（deliveryTemplateSummary）</td>
                  <td>配信テンプレート</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>配信サムネール</td>
                  <td>文字列（255）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>配信</td>
                  <td>文字列（255）</td>
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
                  <td>trackingUrl</td>
                  <td>トラッキングする URL</td>
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
                  <td>タイポロジ （typologyBase）</td>
                  <td>タイポロジ</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ワークフロー（workflowBase）</td>
                  <td>ターゲティングワークフロー</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>ワークフローステータス</td>
                  <td>列挙（文字列） （255）</td>
                  <td>
                     <ul>
                        <li>処理中 – 開始 – 開始</li>
                        <li>編集 – エディション – エディション</li>
                        <li>完了 – 完了 – 完了</li>
                        <li>警告 – 警告 – 警告</li>
                        <li>エラー – エラー – エラー</li>
                        <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## フィルター

チャネルタイプ別（byChannel）

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

実行タイプ別（byExecutionType）

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

論理ステータス別（byLogicalStatus）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>都道府県</td>
    <td>定義済みリスト</td>
    </tr>
</table>

名前またはラベル （byText）

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

期間別（byPeriod）

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

期間別（byStartPeriod）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日付</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>文字列</td>
    </tr>
</table>

公開ステータス別（byPublicationStatus）

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

ステータス別（byState）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>都道府県</td>
    <td>定義済みリスト</td>
    </tr>
</table>

フォローアップメッセージ（showFolloup）

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

高度な配信を含める（withAdvanced）

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

異機種リストからの連続配信を含める（withContinuous）

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
    <td>withFCP</td>
    <td>ブール値</td>
    </tr>
</table>

指定された期間に予定される（byPlanning）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日付</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日付</td>
    </tr>
</table>

指定された期間に存在（byCalendar）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日付</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日付</td>
    </tr>
</table>

標準で表示（showOob）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>ブール値</td>
    </tr>
</table>
