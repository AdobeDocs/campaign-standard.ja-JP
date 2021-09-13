---
title: DataModel
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
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
        <td>電子メール</td>
        <td>メール</td>
        <td>文字列(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>E メールフォーマット</td>
        <td>列挙（バイト） </td>
        <td>
            <ul>
            <li>テキスト — テキスト — 1</li>
            <li>HTML - html - 2</li>
            <li>無効な値 — __無効な値__ - __無効な値__</li>
            <li>不明 — 不明 — 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>アーカイブ済みイベントID</td>
        <td>整数 </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>モバイル番号</td>
        <td>文字列(32)</td>
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

電子メール(byEmail)

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

ステータスまたはタイプ(byStatusOrType)

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
        <td>type</td>
        <td>文字列</td>
        </tr>
    </table>
