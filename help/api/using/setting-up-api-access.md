---
title: APIアクセスの設定
description: Campaign StandardAPIへのアクセスを設定する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# API アクセスの設定 {#setting-up-api-access}

Adobe Campaign Standard APIアクセスは、以下の手順で設定します。 これらの各手順については、[AdobeIOのドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)で詳しく説明しています。

>[!IMPORTANT]
>
>AdobeI/Oで証明書を管理するには、組織の<b>システム管理者</b>権限、またはAdmin Consoleの[開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a>権限を持っている必要があります。

1. **電子証明書があることを確認する**&#x200B;か、必要に応じて作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe Campaign** Serviceとの新しい統合をAdobeI/Oで作成し、設定します。資格情報が生成されます（APIキー、クライアント秘密鍵など）。
1. **以前に生成された資格情報からJSON Webトークン(JWT)** を作成し、秘密鍵で署名します。JWTは、IDを検証し、APIへのアクセス権を付与するためにAdobeで必要な、すべてのIDおよびセキュリティ情報をエンコードします。
1. **JWTをアクセストークンと交換するには、** POSTリクエストを使用します。このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュアなサービス間Adobe I/OAPIセッションを確立するには、Adobe サービスへのすべてのリクエストに以下の情報をAuthorizationヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:これは個人の組織IDで、各インスタンスに対してAdobeが提供するIDは1つです。

   * &lt;organization> :実稼動インスタンス
   * &lt;organization-mkt-stage>:ステージインスタンスを作成します。

   組織IDの値を取得するには、管理者または担当のAdobe技術担当者を参照してください。 また、新しい統合を作成する際に、ライセンスリストでAdobe I/Oに取り込むこともできます(<a href="https://www.adobe.io/authentication.html">AdobeIOのドキュメント</a>を参照)。

* **&lt;access_token>**:POSTリクエストを通じてJSON Webトークンを交換する際に取得された個人用アクセストークン。

* **&lt;api_key>**:個人用APIキー。Adobe Campaign Serviceへの新しい統合を作成した後、Adobe I/Oで提供されます。

   ![代替テキスト](assets/tenant.png)

## トラブルシューティング

Adobe I/O統合中に、次のエラーが表示される場合：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


CNAMEパラメーターが正しく作成されているかどうかを確認するには、管理者またはAdobeの技術担当者に問い合わせてください。
