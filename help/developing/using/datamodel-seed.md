---
title: データモデルのシードメンバー
description: データモデルについて説明します
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 9b522c84-e296-47c7-9588-2e5ed08ab631
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 45%

---

# シードメンバー（nms:seedMember）

## オブジェクトの説明

<table>
               <tr>
                  <th>名前</th>
                  <th>ラベル</th>
                  <th>タイプ （長さ）</th>
                  <th>列挙値</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>メインリソース ID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>国（国）</td>
                  <td>国</td>
                  <td>リンク </td>
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
                  <td>降順</td>
                  <td>説明</td>
                  <td>文字列（512）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>メール</td>
                  <td>メール</td>
                  <td>文字列（128）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailRendering</td>
                  <td>メールのレンダリング</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>ファックス</td>
                  <td>文字列（32）</td>
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
                  <td>lastModified</td>
                  <td>最終変更日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>場所</td>
                  <td>場所</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>MARKETING CLOUDID</td>
                  <td>文字列（256）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>モバイルアプリケーション</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>モバイル</td>
                  <td>文字列（32）</td>
                  <td> </td>
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
                  <td>nms_recipient</td>
                  <td>プロファイル</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>イベント</td>
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
                  <td>電話</td>
                  <td>電話</td>
                  <td>文字列（32）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>配達確認</td>
                  <td>配達確認</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>プッシュ通知</td>
                  <td>文字列（255）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>登録トークン</td>
                  <td>文字列（256）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>サンプルデータ</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>SMS</td>
                  <td>モバイル</td>
                  <td>文字列（255）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink （状態）</td>
                  <td>状態</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetData</td>
                  <td>拡張</td>
                  <td>文字列 </td>
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
                  <td>テストプロファイル</td>
                  <td>文字列（255）</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>わな</td>
                  <td>トラップ</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
            </table>

## フィルター

イベントタイプ別（byEventType）

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>eventType</td>
        <td>文字列</td>
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
    </table>

用途別（byUsage）

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>わな</td>
        <td>ブール値</td>
        </tr>
        <tr>
        <td>emailRendering</td>
        <td>ブール値</td>
        </tr>
        <tr>
        <td>配達確認</td>
        <td>ブール値</td>
        </tr>
    </table>

テストプロファイル （プロファイル）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>seedMember</td>
    <td>リンク</td>
    </tr>
</table>
