---
title: API アクセスの設定
description: Campaign Standard APIへのアクセスを設定する方法について説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 9%
---
# API アクセスの設定 {#setting-up-api-access}

Adobe Campaign Standard API アクセスは、次の手順で設定します。 これらの各手順について詳しくは、[Adobe Developer ドキュメント ](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!IMPORTANT]
>
>[Adobe Developer](https://developer.adobe.com/)で証明書を管理するには、組織の&#x200B;**システム管理者**&#x200B;権限、またはAdmin Consoleの[開発者アカウント ](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)権限があることを確認してください。

1. **電子証明書があるかどうかを確認するか、必要に応じて電子証明書を作成します**。 証明書で提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe Developer](https://developer.adobe.com/)の[Adobe Campaign Service**&#x200B;への新しい統合を作成し、設定します。 次に、資格情報が生成されます（API キー、クライアントシークレット…）。
1. **以前に生成した資格情報からJSON Web トークン （JWT）**&#x200B;を作成し、秘密鍵で署名します。 JWTは、AdobeがIDを検証し、APIへのアクセス権を付与するために必要なすべてのIDおよびセキュリティ情報をエンコードします。

   >[!IMPORTANT]
   >
   >JWT（JSON web トークン）は、現在非推奨（廃止予定）の段階で、OAuth に置き換えられています。 移行は、Campaignの今後のリリース内で段階的に実行されます。 サービスアカウント （JWT）資格情報は非推奨とマークされています。2025年1月27日まで引き続き機能します。 したがって、2025年1月27日（PT）より前に新しいOAuth サーバー間資格情報を使用するには、アプリケーションまたは統合を移行する必要があります。 OAuth認証をお勧めします。 JWT認証からOAuth認証に移行するためのすべての要素は、次のページにあります。
   >* [移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [実装](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [非推奨のJWT FAQ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

1. **POST リクエストを通じてJWTをアクセストークン**&#x200B;と交換します。 このアクセストークンは、API リクエストの各ヘッダーで使用する必要があります。

セキュアなサービス間Adobe I/O API セッションを確立するには、Adobe サービスへのあらゆるリクエストに以下の情報をAuthorization ヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>**：これはあなたの個人組織IDです。Adobeによって、インスタンスごとに1つの組織IDが提供されます。

  * &lt;ORGANIZATION>：本番インスタンス、
  * &lt;ORGANIZATION-mkt-stage>: ステージインスタンス。

  組織IDの値を取得するには、管理者またはAdobeの技術担当者を参照してください。 新しい統合を作成する際に、ライセンスの一覧からAdobe I/Oに取り込むこともできます（<a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer ドキュメント </a>を参照）。

* **&lt;ACCESS_TOKEN>**: POST リクエストを通じてJSON Web トークンを交換する際に取得した個人アクセストークン。

* **&lt;API_KEY>**：個人のAPI キー。 Adobe Campaign Serviceへの新しい統合を作成した後、Adobe I/Oで提供されます。

  ![alt text](assets/tenant.png)

## トラブルシューティング

AdobeIO統合中に、次のエラーが表示される場合：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


CNAME パラメーターが正しく作成されているかどうかを確認するには、管理者またはAdobeの技術担当者を参照してください。
