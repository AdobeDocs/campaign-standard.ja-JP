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
source-wordcount: '53'
ht-degree: 60%

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