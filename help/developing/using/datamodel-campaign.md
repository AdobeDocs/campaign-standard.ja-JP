---
title: データモデルキャンペーン
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a63fe730-a6b2-4ae0-93da-9f8ee7824c9f
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 42%

---

# キャンペーン (nms:campaign)

## オブジェクトの説明

<table>
               <tr>
                  <th>名前</th>
                  <th>ラベル</th>
                  <th>タイプ（長さ）</th>
                  <th>列挙値</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>メインリソース ID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>アクティビティ</td>
                  <td>アクティビティ</td>
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
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列 (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>duration</td>
                  <td>キャンペーン期間</td>
                  <td>番号 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>終了</td>
                  <td>終了日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理的単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソースです</td>
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
                  <td>label</td>
                  <td>ラベル</td>
                  <td>文字列 (128)</td>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>組織単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>プログラム (programBase)</td>
                  <td>プログラム</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>リアルタイムレポート</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>開始日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ステータス</td>
                  <td>ステータス</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>開始済み — 開始 — 1</li>
                        <li>編集 — エディション — 0</li>
                        <li>完了 — 終了 — 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>テンプレート（キャンペーン）</td>
                  <td>キャンペーンテンプレート</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>サムネイル</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>キャンペーン</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
            </table>

## フィルター

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
</table>

期間別（期間別）

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

指定した期間に計画済 (byPlanning)

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

指定された期間 (byCalendar) に存在

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
