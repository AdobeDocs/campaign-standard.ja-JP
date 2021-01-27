---
solution: Campaign Standard
product: campaign
title: フィルター
description: フィルタリング操作を実行する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---


# フィルター {#filtering}

## フィルターメタデータの取得

フィルターは各リソースで使用できます。 リソースに関連付けられたフィルターを特定するには、リソースメタデータに対してGET要求を実行する必要があります。 このリクエストは、特定のリソースに対してすべてのフィルターが定義されているURLを返します。 メタデータについて詳しくは、[この](../../api/using/metadata-mechanism.md)を参照してください。

フィルターのメタデータを特定し、その使用方法を決定するには、以前に返されたURLに対してGETリクエストを実行する必要があります。

<br/>

***サンプルリクエスト***

以下のサンプルペイロードでは、「プロファイル」リソースの「byText」フィルターメタデータを取得する方法を示します。 最初に、「プロファイル」リソースメタデータに対してGETリクエストを実行します。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

フィルターが記述されているURLを返します。

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

URLでGETリクエストを実行します。 プロファイルリソースのフィルターのリストと、各フィルターに関連付けられたメタデータを返します。

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## フィルターのメタデータ構造

各フィルターで同じメタデータ構造を使用できます。

* **@formType**&#x200B;と&#x200B;**@webPage**&#x200B;の各フィールドは技術的なフィールドです。
* **data**&#x200B;フィールドには、フィルターの使用方法に関するサンプルが表示されます。
* **metadata**&#x200B;ノードは、フィルターパラメーターを示します。
* **condition**&#x200B;ノードは、フィルターの目的を示します。 メタデータノードで説明されているフィルターパラメーターは、フィルター条件の作成に使用されます。 各フィルター条件に対して、**enabled**&#x200B;がtrueの場合、**expr**&#x200B;が適用されます。

<br/>

フィルターのメタデータ構造の例：

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## フィルターの使用

フィルタリングは、次のリクエストを使用して実行されます。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

単一のリクエストで複数のフィルターを組み合わせることができます。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***リクエストのサンプル***

* タイプが「email」の「service」リソースを取得するサンプルGETリクエスト。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* サンプルGETリクエストを作成し、
電子メールまたは姓のフィールド（byTextフィルターは、電子メールと姓の両方のフィールドを検索します）。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           }
           ...
       ],
       ...
   }
   ```

* タイプが「email」でラベルが「sport」のサービスリソースを取得するためのサンプルGETリクエスト。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   リクエストに対する応答。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## カスタムフィルター

カスタムフィルターを使用する場合は、Adobe Campaign Standardインターフェイスでカスタムフィルターを作成およびカスタマイズする必要があります。 カスタムフィルターは、既製のフィルターと同じ動作になります。

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

詳しくは、Campaign Standardのドキュメントを参照してください。

* [フィルター定義の設定](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [使用例：複合IDキーを使用してリソースを呼び出す](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html)。

<br/>

***サンプルリクエスト***

トランザクション量が100$以上の「プロファイル」リソースを取得するためのサンプルGETリクエスト。 「byAmount」フィルターは、最初にAdobe Campaign Standardインターフェイスで定義され、「Transaction」カスタムテーブルにリンクされています。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
