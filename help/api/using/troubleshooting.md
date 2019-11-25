---
title: トラブルシューティング
description: キャンペーン標準APIに関連する一般的な問題について詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ab5725b326de2f1cb4c5d15d0d3c0303a6bf0f06

---


# トラブルシューティング {#troubleshooting}

* **Adobe.io Consoleに移動すると、次のエラーが表示されます。「Adobe I/Oコンソールは、エンタープライズアカウントのメンバーを選択する場合にのみ使用できます。 アクセス権が必要な場合は、システム管理者にお問い合わせください。」**

APIキーは、管理者のIMS組織に対してのみ作成できます。 このメッセージが表示され、APIキーを作成し、IMS組織の管理者の1人に問い合わせる場合。

* **Adobe.ioに対するリクエストを実行すると、{"error_code":"403023","message":"Profile is not valid"}が表示されます。**

つまり、特定のCampaign製品のIMSプロビジョニングに問題があります。imsチームが修正する必要があります。

詳細を取得するには、トークンを使用してIMS APIを呼び出し、IMSプロファイルがどのように表示されるかを確認します。Adobe.ioがリクエストをルーティングできるようにするには、URLに入力したのと同じorganization_idを持つprodCtxが必要です。
IMSプロビジョニングがない場合は、修正する必要があります。

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

このリクエストでIMSプロファイルを確認します。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

この応答では、ORGANIZATION_IDの値が最初のGETリクエストで同じである必要があります。

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

* **Adobe.ioにリクエストを行うと、{"code":500, "message":"Oops. 問題が発生しました。 URIを確認して、もう一度お試しください。"}**

Adobe.ioが無効なURIを宣言します。要求しているURIが有効でない可能性があります。 Adobe.ioでCampaignサービスを選択すると、考えられるorganization_idsのリストを含むピッカーが表示されます。 選択したものがURLに入力したものであることを確認する必要があります。

* **Adobe.ioに対する要求を行うと、{"error_code":"401013","message":"Oauth token is not valid"}が表示されます。**

トークンが無効（トークンの生成に使用された不適切なIMS呼び出し）か、トークンの有効期限が切れています。

* **作成後にプロファイルが表示されない**

インスタンスの設定に応じて、作成したプロファイルをorgUnitに関連付ける必要があ **ります**。 作成時にこのフィールドを追加する方法については、この節を参照 [してください](../../api/using/managing-profiles.md)。

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
