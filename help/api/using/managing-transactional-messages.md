---
title: トランザクションメッセージの管理
description: APIを使用してトランザクションメッセージを管理する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---

# トランザクションメッセージの管理 {#managing-transactional-messages}

## トランザクションメッセージについて

トランザクションイベントを作成して公開したら、このイベントのトリガーをWebサイトに統合する必要があります。

>[!NOTE]
>
>イベントの設定については、[この節](../../channels/using/configuring-transactional-event.md)で説明しています。

例えば、顧客が買い物かごで商品を購入する前にWebサイトを離れるたびに「買い物かごの放棄」イベントをトリガーするとします。 これをおこなうには、Web開発者がRESTトランザクションメッセージAPIを使用する必要があります。

1. 開発者は、POSTメソッドに従ってリクエストを送信し、トランザクションイベント](#sending-a-transactional-event)の送信をトリガーします。[
1. POSTリクエストへの応答にはプライマリキーが含まれ、開発者はGETリクエストを通じて1つ以上のリクエストを送信できます。 これにより、[イベントステータス](#transactional-event-status)を取得できます。

## トランザクションイベントの送信 {#sending-a-transactional-event}

トランザクションイベントは、次のURL構造を持つPOSTリクエストを通じて送信されます。

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:組織ID。[この節](../../api/using/must-read.md)を参照してください。

* **&lt;transactionalapi>**:トランザクションメッセージAPI endPoints

   トランザクションメッセージAPIエンドポイントの名前は、インスタンスの設定に応じて異なります。 これは、値「mc」に続く個人の組織IDに対応します。 組織IDが「geometrixx」のGeometrixx会社の例を見てみましょう。 その場合、POSTリクエストは次のようになります。

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   （トランザクションメッセージAPIエンドポイントは、APIプレビューでも表示されます）。

* **&lt;eventid>**:送信するイベントのタイプ。このIDは、イベント設定の作成時に生成されます（[この節](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照）。

### POSTリクエストヘッダー

リクエストには、「Content-Type:application/json」ヘッダー。

**utf-8**&#x200B;のように、文字セットを追加する必要があります。 この値は、使用しているRESTアプリケーションによって異なります。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POSTリクエスト本文

イベントデータは、JSONイベント本文にPOSTされます。 イベント構造は定義によって異なります。 リソース定義画面のAPIプレビューボタンには、リクエストのサンプルが表示されます。 [この節](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照してください。

イベントコンテンツに次のオプションパラメーターを追加して、イベントにリンクされたトランザクションメッセージの送信を管理できます。

* **有効期限** （オプション）:この日以降、トランザクションイベントの送信はキャンセルされます。
* **scheduled** （オプション）:この日以降、トランザクションイベントが処理され、トランザクションメッセージが送信されます。

>[!NOTE]
>
>「expiration」パラメーターと「scheduled」パラメーターの値は、ISO 8601形式に従います。 ISO 8601では、日付と時刻を区切る際に大文字の「T」を使用するように指定しています。 ただし、読みやすくするために、入力または出力から削除できます。

### POST要求への応答

POST応答は、作成時のトランザクションイベントステータスを返します。 現在のステータス(イベントGET、イベントステータスなど)を取得するには、POSTの応答で返されるプライマリキーをリクエストで使用します。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***リクエストのサンプル***

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

### トランザクションイベントのステータス {#transactional-event-status}

応答の「status」フィールドを使用すると、イベントが処理されたかどうかを知ることができます。

* **保留中**:イベントは保留中 — イベントがトリガーされたときに、このステータスを処理します。
* **処理**:イベントは配信待ち — メッセージに変換中で、メッセージの送信中です。
* **一時停止**:イベントプロセスは一時停止中です。処理は終了しますが、Adobe Campaignデータベースのキューに保持されます。 詳しくは、[この節](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication)を参照してください。
* **処理済み**:イベントは処理され、メッセージは正常に送信されました。
* **無視**:このイベントは配信で無視されました。通常、このイベントは、アドレスが強制隔離中の場合に発生します。
* **deliveryFailed**:イベントの処理中に配信エラーが発生しました。
* **routingFailed**:ルーティングフェーズが失敗しました — これは、例えば、指定されたイベントのタイプが見つからない場合などに発生する可能性があります。
* **tooOld**:イベントは、処理が可能になる前に期限切れになっています。これは、例えば、送信が複数回失敗した場合（この結果、イベントが最新でなくなった場合）や、サーバーが過負荷になった後でイベントを処理できない場合などに発生します。
* **targetingFailed**:Campaign Standardは、メッセージのターゲティングに使用されているリンクのエンリッチメントに失敗しました。
