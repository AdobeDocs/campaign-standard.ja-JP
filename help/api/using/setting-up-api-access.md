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

Adobe Campaign Standard API アクセスは、以下の手順で設定します。 これらの各手順について詳しくは、 [AdobeIO ドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>AdobeI/O で証明書を管理するには、 <b>システム管理者</b> 組織または [開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> Admin Console

1. **電子証明書を持っていることを確認します**&#x200B;または必要に応じて作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe Campaign Service への新しい統合の作成** AdobeI/O で設定します。 資格情報が生成されます（API キー、クライアント秘密鍵。.）。
1. **JSON Web トークン (JWT) の作成** 以前に生成された資格情報から、秘密鍵で署名します。 JWT は、ID を検証し、API へのアクセス権を付与するためにAdobeが必要とするすべての ID およびセキュリティ情報をエンコードします。
1. **アクセストークンとの JWT の交換** POST このアクセストークンは、API リクエストの各ヘッダーで使用する必要があります。

セキュアなサービス間Adobe I/OAPI セッションを確立するには、Adobe サービスへのすべてのリクエストに、以下の情報を Authorization ヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:これは個人の組織 ID で、各インスタンスに対してAdobeが提供する ID は 1 つです。

   * &lt;organization> :本番インスタンス
   * &lt;organization-mkt-stage>:ステージインスタンス

   組織 ID 値を取得するには、管理者または担当のAdobe技術担当者にお問い合わせください。 また、新しい統合を作成する際に、Adobe I/Oに取得することもできます ( <a href="https://www.adobe.io/authentication.html">AdobeIO ドキュメント</a>) をクリックします。

* **&lt;access_token>**:個人用アクセストークン。POSTリクエストを通じて JSON Web トークンを交換する際に取得されました。

* **&lt;api_key>**:個人用 API キー。 Adobe Campaign Service への新しい統合を作成した後、Adobe I/Oで提供されます。

   ![代替テキスト](assets/tenant.png)

## トラブルシューティング

Adobe IO 統合中に、次のエラーが表示される場合：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


管理者または担当のAdobe技術担当者に問い合わせて、CNAME パラメーターが正しく作成されているかどうかを確認します。
