---
title: DataModel Audience
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 43%

---

# オーディエンス (nms:audience)

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
                  <td>aamMappingId</td>
                  <td>Audience Managerマッピング ID</td>
                  <td>文字列 (100)</td>
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
                  <td>選択した母集団をプレビュー</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>データスキーマ</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>行番号を ID として使用</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Count</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>カウント日</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>項目 </td>
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
                  <td>doNotPersist</td>
                  <td>このジョブを履歴化しない</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>中止前の最大エラー数</td>
                  <td>整数 </td>
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
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Adobe Marketing Cloudオーディエンス</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソースです</td>
                  <td>ブール値 </td>
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
                  <td>rejectFilename</td>
                  <td>却下ファイル</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>共有オーディエンスの名前</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ソース</td>
                  <td>ソース</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>ソース ID</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>オーディエンス</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>タイプ</td>
                  <td>タイプ</td>
                  <td>enumeration（文字列） (100)</td>
                  <td>
                     <ul>
                        <li>クエリ — クエリ — クエリ</li>
                        <li>リスト — リスト — リスト</li>
                        <li>ファイル — ファイル — ファイル</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>場所</td>
                  <td>クエリ定義</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ワークフロー（ワークフロー）</td>
                  <td>ワークフロー</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
            </table>

## フィルター

ディメンションのフィルタリング (byFilteringResource)

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

タイプ別 (byType)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>タイプ</td>
    <td>列挙</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>文字列</td>
    </tr>
</table>
