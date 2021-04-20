---
solution: Campaign Standard
product: campaign
title: APIアクセスの設定
description: Campaign StandardAPIへのアクセスを設定する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---


# API アクセスの設定 {#setting-up-api-access}

Adobe Campaign StandardAPIアクセスは、次の手順で設定します。 これらの各手順の詳細については、[AdobeIOドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!IMPORTANT]
>
>AdobeI/Oの証明書を管理するには、組織の<b>システム管理者</b>権限、または管理コンソールの[開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a>権限を持っていることを確認してください。

1. **デジタル証明書をお持ちであることを確認するか**、必要に応じて証明書を作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **AdobeI/O内でAdobe Campaign** サービスへの新しい統合を作成し、設定します。次に、資格情報が生成されます（APIキー、クライアントシークレット。.）。
1. **以前に生成した秘密鍵証明書** からJSON Web Token(JWT)を作成し、秘密鍵で署名します。JWTは、AdobeがIDを確認し、APIへのアクセスを許可するために必要なすべてのID情報とセキュリティ情報をエンコードします。
1. **POST要求を通じて、JWTをAccess** トークンと交換します。このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュリティで保護されたサービス間Adobe I/OAPIセッションを確立するには、Adobeサービスへのすべての要求をAuthorizationヘッダーに以下の情報を含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:これは個人の組織IDです。各インスタンスに対して1つの組織IDがAdobeによって提供されます。

   * &lt;organization> :実稼働インスタンス
   * &lt;organization-mkt-stage>:ステージインスタンス。

   組織IDの値を取得するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。 新しい統合を作成する際に、ライセンスリストでAdobe I/Oに取り込むこともできます(<a href="https://www.adobe.io/authentication.html">AdobeIOドキュメント</a>を参照)。

* **&lt;access_token>**:POSTリクエストを介してJSON Webトークンを交換する際に取得された個人アクセストークン。

* **&lt;api_key>**:個人のAPIキーを参照してください。Adobe Campaignサービスへの新しい統合を作成した後、Adobe I/Oで提供されます。

   ![代替テキスト](assets/tenant.png)

## トラブルシューティング

Adobe IOの統合中に、次のエラーが表示される場合：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


CNAMEパラメーターが正しく作成されているかどうかを確認するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。