---
title: トランザクションメッセージの管理
description: APIを使用してトランザクションメッセージを管理する方法について説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d54f036c394db7abdba805ea2c21436c0ef5212c

---


# トランザクションメッセージの管理 {#managing-transactional-messages}

## トランザクションメッセージについて

イベントを作成したら、このイベントのトリガーをWebサイトに統合する必要があります。

>[!NOTE]
>
>イベントの作成と公開は、キャンペーンのドキュメ <a href="https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html">ントに記載されます</a>。

例えば、顧客が買い物かごに製品を購入する前にWebサイトを離れるたびに「買い物かごの放棄」イベントをトリガーするとします。 これを行うには、Web開発者がREST Transactional Messages APIを使用する必要があります。

1. 開発者は、POSTメソッドに従ってリクエストを送信し、トランザクションイベ [ントの送信をトリガーします](#sending-a-transactional-event)。
1. POSTリクエストへの応答にはプライマリキーが含まれ、開発者はGETリクエストを使用して1つ以上のリクエストを送信できます。 これにより、彼はイベントの状態を取得 [できます](#transactional-event-status)。

## トランザクションイベントの送信 {#sending-a-transactional-event}

トランザクションイベントは、次のURL構造を持つPOSTリクエストを介して送信されます。

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;組織>**:個人の組織ID。 [この節](../../api/using/must-read.md)を参照してください。

* **&lt;transactionalAPI>**:トランザクションメッセージAPI endPoints。

   トランザクションメッセージAPIエンドポイントの名前は、インスタンスの設定によって異なります。 これは、値「mc」に続けて個人の組織IDが続く値に対応します。 組織IDとして「geometrixx」を持つGeometrixx社の例を見てみましょう。 この場合、POSTリクエストは次のようになります。

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   （トランザクションメッセージAPIエンドポイントは、APIプレビュー時にも表示されます）。

* **&lt;eventID>**:送信するイベントのタイプ。 このIDは、イベント定義の作成時に生成されます。 Refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### POST要求ヘッダー

リクエストに「Content-Type:application/json」ヘッダーに置き換えます。

文字セット(例えば、 **utf-8)を追加する必要があります**。 この値は、使用しているRESTアプリケーションによって異なります。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST要求本文

イベントデータはJSON POST本文内に含まれます。 イベント構造は定義によって異なります。 リソース定義画面のAPIプレビューボタンには、リクエストのサンプルが表示されます。 Refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

イベントコンテンツに次のオプションのパラメーターを追加して、イベントにリンクされたトランザクションメッセージの送信を管理できます。

* **expiration** （オプション）:この日以降、トランザクションイベントの送信はキャンセルされます。
* **scheduled** （オプション）:この日から、トランザクションイベントが処理され、トランザクションメッセージが送信されます。

>[!NOTE]
>
>「expiration」パラメーターと「scheduled」パラメーターの値は、ISO 8601形式に従います。 ISO 8601では、日付と時間を区切るために大文字の「T」を使用するように指定しています。 ただし、読みやすさを向上させるために、入力または出力から削除することができます。

### POSTリクエストへの応答

POST応答は、作成時のトランザクションイベントステータスを返します。 現在のステータス（イベントデータ、イベントステータスなど）を取得するには、GETリクエストでPOST応答によって返されるプライマリキーを使用します。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***サンプルリクエスト&#x200B;***

POSTリクエストを送信します。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

POSTリクエストへの応答。

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### トランザクションイベントの状態 {#transactional-event-status}

この応答では、「status」フィールドを使用して、イベントが処理されたかどうかを知ることができます。

* **保留中**:イベントが保留中 — イベントがトリガーされたときに、このステータスが発生します。
* **処理**:イベントは配信待ちです。このイベントはメッセージに変換され、メッセージが送信されています。
* **一時停止**:イベントプロセスを一時停止中です。 処理は行われず、Adobe Campaignデータベースのキューに保存されます。 For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **処理済**:イベントが処理され、メッセージが正常に送信されました。
* **ignored**:このイベントは、通常、住所が検疫中の場合に、配信によって無視されました。
* **deliveryFailed**:イベントの処理中に配信エラーが発生しました。
* **routingFailed**:ルーティングフェーズが失敗しました。これは、例えば、指定されたイベントのタイプが見つからない場合に発生する可能性があります。
* **tooOld**:イベントの有効期限が切れてから処理できるようになりました。これは、送信が複数回失敗した場合（この結果、イベントが最新ではなくなった場合）や、過負荷になった後でサーバーがイベントを処理できない場合など、様々な理由で発生します。
* **targetingFailed**:キャンペーン標準で、メッセージのターゲット設定に使用されているリンクのエンリッチに失敗しました。
