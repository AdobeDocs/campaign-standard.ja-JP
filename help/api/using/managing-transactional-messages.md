---
solution: Campaign Standard
product: campaign
title: トランザクションメッセージの管理
description: APIを使用したトランザクションメッセージの管理方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---


# トランザクションメッセージの管理 {#managing-transactional-messages}

## トランザクションメッセージについて

トランザクションイベントを作成して公開した後は、このイベントのトリガーをWebサイトに組み込む必要があります。

>[!NOTE]
>
>イベントの設定については、[このセクション](../../channels/using/configuring-transactional-event.md)を参照してください。

例えば、「買い物かごの放棄」イベントを、顧客が買い物かごで商品を購入する前にWebサイトを離れたときにトリガーするとします。 これを行うには、Web開発者がRESTトランザクションメッセージAPIを使用する必要があります。

1. 開発者は、POST方式に従ってリクエストを送信し、トリガー方式はトランザクションイベント](#sending-a-transactional-event)の[送信を行います。
1. POST要求への応答にはプライマリキーが含まれ、開発者はGET要求を介して1つまたは複数の要求を送信できます。 これで、[イベントステータス](#transactional-event-status)を取得できます。

## トランザクションイベントの送信{#sending-a-transactional-event}

トランザクションイベントは、次のURL構造を持つPOSTリクエストを介して送信されます。

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:個人の組織ID。[こちらの節](../../api/using/must-read.md)を参照してください。

* **&lt;transactionalapi>**:トランザクションメッセージAPI endPoints

   トランザクションメッセージのAPIエンドポイントの名前は、インスタンスの設定に応じて異なります。 これは、値「mc」に続けて個人の組織IDが続く値に対応します。 組織IDとして「geometrixx」を使用したGeometrixx会社の例を見てみましょう。 この場合、POSTリクエストは次のようになります。

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (トランザクションメッセージのAPIエンドポイントは、APIプレビュー中も表示されます)。

* **&lt;eventid>**:送信するイベントの種類。このIDは、イベント設定の作成時に生成されます（[このセクション](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照）。

### POST要求ヘッダー

リクエストに「Content-Type:application/json&quot;ヘッダー。

**utf-8**&#x200B;のように、文字セットを追加する必要があります。 この値は、使用しているRESTアプリケーションに応じて異なります。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST要求機関

イベントデータはJSONPOSTの本文内に含まれます。 イベント構造は定義に応じて異なります。 リソース定義画面のAPIプレビューボタンには、リクエストのサンプルが表示されます。 [こちらの節](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照してください。

イベントにリンクされたトランザクションメッセージの送信を管理するために、イベントのコンテンツに次のオプションのパラメーターを追加できます。

* **expiration** （オプション）:この日以降、トランザクションイベントの送信はキャンセルされます。
* **scheduled** （オプション）:この日から、トランザクションイベントが処理され、トランザクションメッセージが送信されます。

>[!NOTE]
>
>「expiration」パラメーターと「scheduled」パラメーターの値は、ISO 8601形式に従います。 ISO 8601では、日付と時間を区切るために大文字の「T」を使用するよう指定しています。 ただし、読みやすさを高めるために、入力または出力から削除することはできます。

### POST要求への応答

POST応答は、作成時のトランザクションイベントステータスを返します。 現在のステータス(イベントデータ、イベントステータスなど)を取得するには、GETリクエストで、POSTの応答によって返されるプライマリキーを使用します。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***サンプルリクエスト***

イベントを送信するPOST要求です。

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

### トランザクションイベントの状態{#transactional-event-status}

この応答では、「status」フィールドを使用して、イベントが処理済みかどうかを確認できます。

* **保留中**:イベントは保留中です。イベントは、トリガーされたときにこのステータスを引き継ぎます。
* **処理**:イベントは配信待ちです。メッセージに変換中で、メッセージが送信中です。
* **一時停止**:イベントプロセスを一時停止中です。処理は行われなくなり、Adobe Campaignデータベースのキューに保存されます。 詳しくは、[こちらの節](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication)を参照してください。
* **処理済み**:イベントが処理され、メッセージが正常に送信されました。
* **ignored**:このイベントは配信によって無視されました。通常、アドレスが強制隔離の場合です。
* **deliveryFailed**:イベントの処理中に配信エラーが発生しました。
* **routingFailed**:ルーティングフェーズが失敗しました。これは、指定されたイベントの種類が見つからない場合などに発生する可能性があります。
* **tooOld**:イベントの有効期限が切れてから処理できました。これは、送信が複数回失敗した場合(イベントが最新の状態になりません)や、過負荷になった後にイベントを処理できなくなった場合など、様々な理由で発生します。
* **targetingFailed**:Campaign Standardは、メッセージのターゲット設定に使用されているリンクをエンリッチできませんでした。
