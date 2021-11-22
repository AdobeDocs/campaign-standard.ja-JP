---
title: トランザクションメッセージの管理
description: API を使用してトランザクションメッセージを管理する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 3%

---

# トランザクションメッセージの管理 {#managing-transactional-messages}

トランザクションイベントを作成して公開したら、このイベントのトリガーを Web サイトに統合する必要があります。

>[!NOTE]
>
>イベントの設定について詳しくは、 [この節](../../channels/using/configuring-transactional-event.md).

例えば、顧客が買い物かごで商品を購入する前に Web サイトを離れたときに「買い物かごの放棄」イベントをトリガーするとします。 これをおこなうには、Web 開発者が REST トランザクションメッセージ API を使用する必要があります。

1. POSTメソッドに従ってリクエストを送信し、トリガー [トランザクションイベントの送信](#sending-a-transactional-event).
1. POSTリクエストへの応答にはプライマリキーが含まれ、1 つのGETリクエストを通じて 1 つ以上のリクエストを送信できます。 その後、 [イベントステータス](#transactional-event-status).

## トランザクションイベントの送信 {#sending-a-transactional-event}

トランザクションイベントは、次の URL 構造を持つPOSTリクエストを通じて送信されます。

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:個人の組織 ID。 [この節](../../api/using/must-read.md)を参照してください。

* **&lt;transactionalapi>**:トランザクションメッセージ API endPoints を参照してください。

   トランザクションメッセージ API エンドポイントの名前は、インスタンスの設定に応じて異なります。 値「mc」に続く個人の組織 ID が該当します。 組織 ID が「geometrixx」のGeometrixx会社の例を見てみましょう。 この場合、POSTリクエストは次のようになります。

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   トランザクションメッセージ API エンドポイントは、API プレビュー時にも表示されます。

* **&lt;eventid>**:送信するイベントのタイプ。 この ID は、イベント設定の作成時に生成されます ( [この節](../../channels/using/configuring-transactional-event.md#creating-an-event)) をクリックします。

### POSTリクエストヘッダー

リクエストには「Content-Type:application/json」ヘッダー。

例えば、文字セットを追加する必要があります **utf-8**. この値は、使用している REST アプリケーションによって異なります。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POSTリクエスト本文

イベントデータは、JSON イベント本文に含まれているPOSTです。 イベント構造は定義によって異なります。 リソース定義画面の API プレビューボタンには、リクエストのサンプルが表示されます。 [この節](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照してください。

イベントコンテンツに追加して、イベントにリンクされたトランザクションメッセージの送信を管理できます。次のオプションのパラメーターを使用できます。

* **有効期限** （オプション）:この日以降、トランザクションイベントの送信がキャンセルされます。
* **予定** （オプション）:この日以降、トランザクションイベントが処理され、トランザクションメッセージが送信されます。

>[!NOTE]
>
>「expiration」および「scheduled」パラメーターの値は、ISO 8601 形式に従います。 ISO 8601 では、日付と時刻を区切るための大文字「T」の使用を指定しています。 ただし、読みやすくするために、入力または出力から削除できます。

### POSTリクエストへの応答

POST応答は、作成時にトランザクションイベントのステータスを返します。 現在のステータス ( イベントプライマリ、イベントステータスなど ) を取得するには、POST応答で返されるイベントキーをGETリクエストで使用します。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***リクエストのサンプル***

POSTを送信するイベントリクエスト。

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

応答リクエストに対するPOST。

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

応答の「status」フィールドでは、イベントが処理されたかどうかを知ることができます。

* **保留中**:イベントは保留中 — イベントがトリガーされたときに、このステータスを処理します。
* **処理中**:イベントは配信待ちです。このイベントはメッセージに変換中で、メッセージは送信中です。
* **一時停止中**:イベントプロセスは一時停止中です。 処理は終了しますが、Adobe Campaignデータベースのキューに保持されます。 詳しくは、[この節](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication)を参照してください。
* **処理済み**:イベントは処理され、メッセージは正常に送信されました。
* **無視**:このイベントは配信で無視されました（通常、アドレスが強制隔離中の場合）。
* **deliveryFailed**:イベントの処理中に配信エラーが発生しました。
* **routingFailed**:ルーティングフェーズが失敗しました — これは、例えば、指定したイベントのタイプが見つからない場合などに発生する可能性があります。
* **古すぎる**:イベントは、処理が可能になる前に期限切れになりました。これは、例えば、送信が複数回失敗した場合（この結果、イベントが最新でなくなった場合）や、サーバーが過負荷になった後にイベントを処理できなくなった場合に発生します。
* **targetingFailed**:Campaign Standardは、メッセージのターゲティングに使用されているリンクのエンリッチメントに失敗しました。
