---
title: DataModel プログラム
description: データモデルについて詳しく見る
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
TQID: https://experienceleague.adobe.com/zo3wFxqwI6LIHn4Uolv9oipkW17maikqcO4zExmYQxM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 41%

---

# プログラム （nms:program）

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
                  <td>ビルトイン</td>
                  <td>アプリケーションのビルトインオブジェクト</td>
                  <td>ブール値 </td>
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
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列（512）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>終了</td>
                  <td>終了日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit （geoUnitBase）</td>
                  <td>地理的単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソース</td>
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
                  <td>orgUnit （orgUnitBase）</td>
                  <td>組織単位</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>親（programBase）</td>
                  <td>親プログラム</td>
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
                        <li>開始 – 開始 – 1</li>
                        <li>編集 – エディション - 0</li>
                        <li>終了 – 終了 – 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>テンプレート（プログラム）</td>
                  <td>プログラムテンプレート</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>サムネイル</td>
                  <td>文字列（255）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>プログラム</td>
                  <td>文字列（255）</td>
                  <td> </td>
               </tr>
            </table>

## フィルター

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

サブプログラムを含める（withParent）

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>ブール値</td>
        </tr>
    </table>

対象となる親のみ（対象となる親）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>プログラム</td>
    <td>リンク</td>
    </tr>
</table>

特定の期間に計画（計画別）

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
