---
solution: Campaign Standard
product: campaign
title: DataModel
description: データモデルについて
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 59%

---


# 購読解除イベント(nms:rtEvent)

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
                  <td>item</td>
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
                  <td>定義済みリスト</td>
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
        <td>定義済みリスト</td>
        </tr>
        <tr>
        <td>type</td>
        <td>文字列</td>
        </tr>
    </table>