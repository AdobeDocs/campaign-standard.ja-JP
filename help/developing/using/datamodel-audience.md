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
source-wordcount: '0'
ht-degree: 0%

---


# オーディエンス(nms:オーディエンス)

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
                  <td>aamMappingId</td>
                  <td>Audience ManagerマッピングID</td>
                  <td>文字列(100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>AMC データソース</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>プレビュー選択母集団</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>データスキーマ</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>行番号をIDとして使用する</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Count</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>カウント日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>作成日時</td>
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
                  <td>desc</td>
                  <td>説明</td>
                  <td>文字列(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>doNotPersist</td>
                  <td>このジョブを履歴化しない</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>中止前の最大エラー数</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>有効期限</td>
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
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Adobe Marketing Cloudオーディエンス</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソース</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>ログ</td>
                  <td>コレクション </td>
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
                  <td>rejectFilename</td>
                  <td>却下ファイル</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>共有オーディエンスの名前</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ソース</td>
                  <td>ソース</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>ソース ID</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>オーディエンス</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>タイプ</td>
                  <td>定義済みリスト（文字列） (100)</td>
                  <td>
                     <ul>
                        <li>クエリ-クエリ-クエリ</li>
                        <li>リスト-リスト-リスト</li>
                        <li>ファイル — ファイル — ファイル</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>where</td>
                  <td>クエリ定義</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ワークフロー（ワークフロー）</td>
                  <td>ワークフロー</td>
                  <td>link </td>
                  <td> </td>
               </tr>
            </table>

## フィルター

フィルタリングディメンション別(byFilteringResource)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>文字列</td>
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

タイプ別(byType)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>type</td>
    <td>定義済みリスト</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>文字列</td>
    </tr>
</table>