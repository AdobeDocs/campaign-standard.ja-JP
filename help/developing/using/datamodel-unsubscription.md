---
title: DataModel
description: データモデルについて
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
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
                  <td>いいえ</td>
                  <td>文字列</td>
                  <td>いいえ</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>いいえ</td>
                  <td>item</td>
                  <td>いいえ</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>いいえ</td>
                  <td>文字列</td>
                  <td>いいえ</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>いいえ</td>
                  <td>定義済みリスト</td>
                  <td>いいえ</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>いいえ</td>
                  <td>文字列</td>
                  <td>いいえ</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>はい</td>
                  <td>文字列</td>
                  <td>いいえ</td>
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
    <td>email</td>
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