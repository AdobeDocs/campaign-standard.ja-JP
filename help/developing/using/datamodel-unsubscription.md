---
title: DataModel購読解除イベント
description: データモデルについて詳しく見る
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
TQID: https://experienceleague.adobe.com/VuhZ3s5VTH3MFPuqzr18GBMmyaPxD2uQEdJAsMIOlf0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 54
ht-degree: 61%

---

# 購読解除イベント （nms:rtEvent）

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
                  <td>メール</td>
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
    <td>メール</td>
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
