---
solution: Campaign Standard
product: campaign
title: トラブルシューティング
description: Campaign StandardAPIに関する一般的な問題について詳しく説明します。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: API
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---


# トラブルシューティング {#troubleshooting}

* **Adobe.ioコンソールに移動すると、次のエラーが表示されます。「Adobe I/Oコンソールは、エンタープライズアカウントのメンバーのみを選択できます。アクセス権を持つと思われる場合は、システム管理者に問い合わせてください。&quot;**

APIキーは、管理者のIMS組織に対してのみ作成できます。 このメッセージが表示され、APIキーを作成する場合に、IMS組織の管理者の1人に問い合わせる必要があるとします。

* **AdobeIoに対する要求を行うと、{&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;プロファイルが無効です&quot;}が表示されます。**

つまり、特定のキャンペーン製品のIMSプロビジョニングに問題があります。IMSチームが修正する必要があります。

詳細を取得するには、トークンを使用してIMS APIを呼び出し、IMSプロファイルがどのように表示されるかを確認します。prodCtxが必要です。このprodCtxでは、organization_idが、Adobe.ioがリクエストをルーティングできるように、URLに入力したものと同じです。
IMSプロビジョニングが見つからない場合は、修正する必要があります。

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

このリクエストでIMSプロファイルを確認してください。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

この応答では、最初のGETリクエストでORGANIZATION_ID値が同じである必要があります。

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

* **Adobe.ioに対するリクエストを行うと、{&quot;code&quot;:500, &quot;message&quot;:&quot;Oops.エラーが発生しました。URIを確認して、もう一度お試しください。&quot;}**

Adobe.ioが無効なURIを宣言します。要求しているURIが有効でない可能性が高い。 Adobe.ioで、キャンペーンサービスを選択すると、考えられるorganization_idsのリストを持つ選択が表示されます。 選択したものがURLに入力したものであることを確認する必要があります。

* **Adobe.ioへの要求を行うと、{&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}が表示されます。**

トークンが無効（トークンの生成に使用された不適切なIMS呼び出し）か、トークンの有効期限が切れています。

* **創造後にプロファイルが見えない**

インスタンスの設定に応じて、作成したプロファイルを&#x200B;**orgUnit**&#x200B;に関連付ける必要があります。 作成時にこのフィールドを追加する方法を理解するには、[このセクション](../../api/using/creating-profiles.md)を参照してください。

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
