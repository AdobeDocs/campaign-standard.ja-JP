---
title: API のトラブルシューティング
description: Campaign StandardAPI に関する一般的な問題の詳細
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: b65bf28565c25072c6a95cebdb999ce38a2e2e1a
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---

# API のトラブルシューティング {#troubleshooting}

* **Adobe.io コンソールに移動すると、次のエラーが表示されます。「Adobe I/Oコンソールは、エンタープライズアカウントのメンバーを選択する場合にのみ使用できます。 アクセス権が必要な場合は、システム管理者にお問い合わせください。」**

API キーは、自分が管理している組織に対してのみ作成できます。 このメッセージが表示され、API キーを作成して組織の管理者に問い合わせたい場合。

* **Adobe.io に対してリクエストを実行すると、{&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;Profile is not valid&quot;} が表示されます。**

つまり、特定の Campaign 製品の IMS プロビジョニングに問題があり、IMS チームが修正する必要があります。

詳細を取得するには、トークンで IMS API を呼び出して IMS プロファイルがどのように表示されるかを確認します。リクエストをルーティングするには、URL に指定したAdobe.io と同じ prodCtx が必要です。
見つからない場合は、IMS プロビジョニングを修正する必要があります。

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

次のエラーを返します。

```
{"error_code":"403023","message":"Profile is not valid"}
```

このリクエストで IMS プロファイルを確認します。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

応答では、 ORGANIZATION_ID の値は最初のGETリクエストと同じである必要があります。

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Adobe.io に対してリクエストを行うと、{&quot;code&quot;:500, &quot;message&quot;:&quot;Oops が表示されます。 エラーが発生しました. URI を確認し、再度お試しください。&quot;}**

Adobe.io が無効な URI を宣言します。要求している URI が無効な可能性が高くなります。 Adobe.io で Campaign サービスを選択すると、選択ツールに選択可能な organization_ids のリストが表示されます。 選択したものが、URL に配置したものであることを確認する必要があります。

* **Adobe.io に対してリクエストを行うと、{&quot;error_code&quot;:&quot;401013&quot;、&quot;message&quot;:&quot;OAuth token is not valid&quot;} が表示されます。**

トークンが無効（トークンの生成に使用される不適切な IMS 呼び出し）か、トークンの有効期限が切れています。

* **作成後、自分のプロファイルが表示されない**

インスタンスの設定に応じて、作成したプロファイルを **orgUnit**. このフィールドを作成に追加する方法については、 [この節](../../api/using/creating-profiles-api.md).

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
