---
title: DataModel サブスクリプションイベント
description: データモデルについて詳しく見る
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
TQID: 'https://experienceleague.adobe.com/XssYu0sntbeCRq1uNe6MhztLtISXoJiOefIOnjqIaoQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 34%
---
# 購読イベント （nms:rtEvent）

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
        <td>ctx</td>
        <td>イベントコンテキスト</td>
        <td>項目 </td>
        <td> </td>
    </tr>
    <tr>
        <td>メール</td>
        <td>メール</td>
        <td>文字列（128）</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>メールフォーマット</td>
        <td>列挙（バイト） </td>
        <td>
            <ul>
            <li>テキスト – テキスト - 1</li>
            <li>HTML - html - 2</li>
            <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            <li>不明 – 不明 – 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>アーカイブされたイベント ID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>モバイル番号</td>
        <td>文字列（32）</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>文字列 </td>
        <td> </td>
    </tr>
</table>

## フィルター

電子メールによる送信（電子メール）

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

ステータスまたはタイプ別（byStatusOrType）

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
