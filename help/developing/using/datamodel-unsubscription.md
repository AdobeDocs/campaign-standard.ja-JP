---
title: DataModel 購読解除イベント
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 58%

---

# 購読解除イベント (nms:rtEvent)

## オブジェクトの説明

<table>
               <tr>
                  <th>名前</th>
                  <th>読み取り専用</th>
                  <th>タイプ</th>
                  <th>必須</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>False</td>
                  <td>文字列</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>False</td>
                  <td>項目</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>電子メール</td>
                  <td>False</td>
                  <td>文字列</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>False</td>
                  <td>列挙</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>False</td>
                  <td>文字列</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>文字列</td>
                  <td>False</td>
               </tr>
            </table>

## フィルター

byEmail

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>電子メール</td>
    <td>文字列</td>
    </tr>
</table>

byStatusOrType

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>ステータス</td>
        <td>列挙</td>
        </tr>
        <tr>
        <td>タイプ</td>
        <td>文字列</td>
        </tr>
    </table>
