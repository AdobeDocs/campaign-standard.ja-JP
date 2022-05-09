---
title: DataModel Service
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 45%

---

# サービス (nms:service)

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
                  <td>cusPrice</td>
                  <td>価格</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列 (512)</td>
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
                  <td>履歴</td>
                  <td>購読履歴</td>
                  <td>コレクション </td>
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
                  <td>limitedDuration</td>
                  <td>期間限定</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日付</td>
                  <td>日付 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>チャネル</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>Mobile(SMS) - sms - 1</li>
                        <li>電子メール — 電子メール — 0</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mode</td>
                  <td>モード</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>バイラル — 1</li>
                        <li>ニュースレター — ニュースレター — 0</li>
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
                  <td>publicLabel</td>
                  <td>サービスラベル</td>
                  <td>文字列 (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>開始日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>サブスクリプションランディングページ</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>購読の確認</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>購読</td>
                  <td>購読</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>ターゲティングディメンション</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (service)</td>
                  <td>サービステンプレート</td>
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
                  <td>サービス</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>購読解除ランディングページ</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>購読解除の確認</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>有効期間</td>
                  <td>数値 </td>
                  <td> </td>
               </tr>
            </table>

## フィルター

指定した期間 (byPlanning) に使用可能

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

ターゲティングリソース別 (byTargetResource)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>targetResource</td>
<td>文字列</td>
</tr>
</table>
