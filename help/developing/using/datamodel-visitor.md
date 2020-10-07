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
source-wordcount: '144'
ht-degree: 38%

---


# 訪問者(nms:訪問者)

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
        <td>コメント</td>
        <td>転送者のコメント</td>
        <td>文字列(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>created</td>
        <td>作成日時</td>
        <td>日付 </td>
        <td> </td>
    </tr>
    <tr>
        <td>createdBy (userBase)</td>
        <td>作成者</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>配信(配信)</td>
        <td>配信</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>最後の配信のID</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>説明</td>
        <td>文字列(512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>電子メール</td>
        <td>文字列(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>外部 ID</td>
        <td>文字列(64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>名</td>
        <td>文字列(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>転送 URL</td>
        <td>文字列(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>地理的単位</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>最終変更日</td>
        <td>日付 </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>姓</td>
        <td>文字列(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>変更者</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>組織単位</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>接触チャネル</td>
        <td>接触チャネル</td>
        <td>定義済みリスト（バイト） </td>
        <td>
            <ul>
            <li>未定義 — 未定義 — 0</li>
            <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>受信者(受信者)</td>
        <td>識別されたプロファイル</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>プロファイルID</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>転送者の E メール</td>
        <td>文字列(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>転送者の名</td>
        <td>文字列(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>転送者ID</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>転送者の姓</td>
        <td>文字列(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp(受信者)</td>
        <td>転送者</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>タイトル</td>
        <td>ラベル</td>
        <td>文字列(255)</td>
        <td> </td>
    </tr>
</table>

## フィルター

姓、名、電子メール(byText)</p>

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>テキスト</td>
        <td>文字列</td>
        </tr>
    </table>