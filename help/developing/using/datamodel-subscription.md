---
title: データモデル購読イベント
description: データモデルについて説明します
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 34%

---

# 購読イベント （nms:rtEvent）

## オブジェクトの説明

<table>
    <tr>
        <th>名前</th>
        <th>ラベル</th>
        <th>タイプ （長さ）</th>
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
            <li>HTML- html - 2</li>
            <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
            <li>不明 – 不明 – 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>アーカイブしたイベント ID</td>
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

電子メールによる（byEmail）

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
        <td>定義済みリスト</td>
        </tr>
        <tr>
        <td>タイプ</td>
        <td>文字列</td>
        </tr>
    </table>
