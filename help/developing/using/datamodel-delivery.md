---
title: DataModel配信
description: データモデルについて詳しく見る
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
TQID: https://experienceleague.adobe.com/zFUpmYKXJPF3cW-KGjKpdG1rbt3lv-5hsCjVugdSLA0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 730
ht-degree: 31%

---

# 配信（nms:delivery）

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
                  <td>高度な</td>
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
                  <td>添付</td>
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
                  <td>broadLogs</td>
                  <td>配信ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ビルトイン</td>
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
                        <li>Adobe Campaign - campaign - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                        <li>一括配信 – 一括配信 – 1</li>
                        <li>ミッドソーシング – ミッドソーシング - 4</li>
                        <li>説明 – 説明 – 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列（512）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>メールプレビュー</td>
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
                  <td>除外事項</td>
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
                        <li>継続 – 継続 – 1</li>
                        <li>Message Center - messageCenter - 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                        <li>Fax - fax - 4</li>
                        <li>モバイル （SMS） - SMS - 1</li>
                        <li>定期的なメール - emailRefresh - 30</li>
                        <li>ダイレクトメール – 紙 – 3</li>
                        <li>電話 – 電話 – 2</li>
                        <li>その他 – その他 – 120</li>
                        <li>定期的なSMS - smsRefresh - 31</li>
                        <li>モバイルアプリケーション - pushNotification - 40</li>
                        <li>トランザクション SMS - smsLightning - 61</li>
                        <li>電子メール – メール - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>jobLogs</td>
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
                        <li>進行中 – 開始 – 開始</li>
                        <li>編集 – エディション – エディション</li>
                        <li>完了 – 完了 – 完了</li>
                        <li>警告 – 警告 – 警告</li>
                        <li>エラー – エラー – エラー</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>master （deliveryBase）</td>
                  <td>マスター インスタンス</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
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
                        <li>Fax - fax - 4</li>
                        <li>モバイル （SMS） - SMS - 1</li>
                        <li>電子メール – メール - 0</li>
                        <li>電話 – 電話 – 2</li>
                        <li>ダイレクトメール – 紙 – 3</li>
                        <li>モバイルアプリケーション - pushNotification - 40</li>
                        <li>その他 – その他 – 120</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>標準 – 標準 – 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program （programBase）</td>
                  <td>プログラム</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>プルーフ</td>
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
                  <td>リソースバージョン</td>
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
                        <li>保留開始 – startPending - 51</li>
                        <li>配信準備完了 – 準備完了 – 45</li>
                        <li>再試行保留中 – retryPending - 61</li>
                        <li>再試行中 – retryInProgress - 62</li>
                        <li>失敗 – 失敗 – 87</li>
                        <li>進行中 – 開始 – 55</li>
                        <li>ターゲティング保留中 – targetPrepPending - 11</li>
                        <li>Personalization保留中 – messagePrepPending - 21</li>
                        <li>一時停止 – 一時停止 – 75</li>
                        <li>編集 – エディション - 0</li>
                        <li>終了 – 終了 – 95</li>
                        <li>進行中のカウント - targetSelection - 12</li>
                        <li>Message finalized - messageReady - 25</li>
                        <li>Personalizationまたはカウントに失敗しました – preparationError - 37</li>
                        <li>停止 – キャンセル - 85</li>
                        <li>進行中のPersonalization - messagePreparation - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>進行中の仲裁 – targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>目標</td>
                  <td>配信ターゲット母集団</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template （deliveryTemplateSummary）</td>
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
                  <td>trackingUrls</td>
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
                        <li>進行中 – 開始 – 開始</li>
                        <li>編集 – エディション – エディション</li>
                        <li>完了 – 完了 – 完了</li>
                        <li>警告 – 警告 – 警告</li>
                        <li>エラー – エラー – エラー</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
    <td>列挙</td>
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
    <td>列挙</td>
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
    <td>列挙</td>
    </tr>
</table>

名前またはラベル別（テキスト別）

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
    <td>都道府県</td>
    <td>列挙</td>
    </tr>
</table>

フォローアップメッセージ （showFollowup）

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

高度な配信を含める（詳細設定）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>高度な</td>
    <td>ブール値</td>
    </tr>
</table>

異種リストからの継続的な配信を含める（Continuousを使用）

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

プルーフを含める（FCPを使用）

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

特定の期間に計画（計画による）

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

特定の期間に存在する（カレンダー別）

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

すぐに使える機能を表示（showOob）

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
