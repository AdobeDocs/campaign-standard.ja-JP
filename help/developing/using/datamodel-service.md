---
title: DataModel
description: データモデルについて
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# サービス(nms:service)

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
                  <td>メインリソースID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>組み込みアプリケーションオブジェクト</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>作成済み</td>
                  <td>日付 </td>
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
                  <td>文字列(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>終了日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理的単位</td>
                  <td>link </td>
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
                  <td>外部リソース</td>
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
                  <td>label</td>
                  <td>ラベル</td>
                  <td>文字列(128)</td>
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
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日付</td>
                  <td>date (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>チャネル</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>モバイル(SMS) -sms - 1</li>
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
                        <li>クチコミ — 1</li>
                        <li>ニュースレター — 0</li>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>組織単位</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>サービスラベル</td>
                  <td>文字列(128)</td>
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
                  <td>購読のランディングページ</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>購読の確認</td>
                  <td>link </td>
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
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template （サービス）</td>
                  <td>サービステンプレート</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>サムネイル</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>サービス</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>購読解除ランディングページ</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>購読解除の確認</td>
                  <td>link </td>
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
                  <td>number </td>
                  <td> </td>
               </tr>
            </table>

## フィルター

所定の期間(Planning)に使用可能

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

チャネルタイプ別（チャネル別）

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
</table>

リソースをターゲット設定する(byTargetResource)

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