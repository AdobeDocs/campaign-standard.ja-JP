---
title: API アクセスの設定
description: Campaign StandardAPI へのアクセスを設定する方法を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# API アクセスの設定 {#setting-up-api-access}

Adobe Campaign Standard API アクセスは、以下の手順で設定します。 これらの各手順については、[AdobeIO のドキュメント ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) で詳しく説明しています。

>[!IMPORTANT]
>
>AdobeI/O で証明書を管理するには、組織の <b> システム管理者 </b> 権限、またはAdmin Consoleの [ 開発者アカウント ](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> 権限を持っている必要があります。

1. **電子証明書があることを確認する**&#x200B;か、必要に応じて作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe Campaign** Service との新しい統合をAdobeIO で作成し、設定します。資格情報が生成されます（API キー、クライアント秘密鍵など）。
1. **以前に生成した資格情報から JSON Web トークン (JWT)** を作成し、秘密鍵で署名します。JWT は、ID を検証し、API へのアクセス権を付与するためにAdobeで必要なすべての ID およびセキュリティ情報をエンコードします。
1. **JWT をアクセストークンと交換するには、** POSTリクエストを使用します。このアクセストークンは、API リクエストの各ヘッダーで使用する必要があります。

安全なサービス間Adobe I/OAPI セッションを確立するには、Adobe サービスへのすべてのリクエストに以下の情報を Authorization ヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:これは個人の組織 ID で、各インスタンスに対してAdobeが提供する ID は 1 つです。

   * &lt;organization> :実稼動インスタンス
   * &lt;organization-mkt-stage>:ステージインスタンスを作成します。

   組織 ID 値を取得するには、管理者または担当のAdobeの技術担当者を参照してください。 新しい統合を作成する際に、Adobe I/Oに取り込むこともできます (<a href="https://www.adobe.io/authentication.html">AdobeIO のドキュメント </a> を参照 )。

* **&lt;access_token>**:POST要求で JSON Web トークンを交換したときに取得された個人用アクセストークン。

* **&lt;api_key>**:個人用 API キー。Adobe Campaign Service への新しい統合を作成した後、Adobe I/Oで提供されます。

   ![代替テキスト](assets/tenant.png)

## トラブルシューティング

Adobe I/O 統合中に、次のエラーが表示される場合：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


管理者または担当のAdobeの技術担当者に問い合わせて、CNAME パラメーターが正しく作成されたかどうかを確認します。
