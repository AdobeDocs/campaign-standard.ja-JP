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
source-wordcount: '77'
ht-degree: 32%

---


# 購読イベント(nms:rtEvent)

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
        <td>ctx</td>
        <td>イベントコンテキスト</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>電子メール</td>
        <td>文字列(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>E メールフォーマット</td>
        <td>定義済みリスト（バイト） </td>
        <td>
            <ul>
            <li>テキスト — テキスト — 1</li>
            <li>HTML - html - 2</li>
            <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
            <li>不明 — 不明 — 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>アーカイブ済みイベントID</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>モバイル番号</td>
        <td>string (32)</td>
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

電子メール別（電子メール別）

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

ステータスまたはタイプ別(byStatusOrType)

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