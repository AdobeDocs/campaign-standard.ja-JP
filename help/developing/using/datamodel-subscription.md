---
title: DataModel
description: データモデルについて
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

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
        <td>E メール</td>
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
            <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
            <li>不明 — 不明 — 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>アーカイブされたイベントID</td>
        <td>整数 </td>
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

電子メール（電子メール）

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
        <td>列挙</td>
        </tr>
        <tr>
        <td>type</td>
        <td>文字列</td>
        </tr>
    </table>