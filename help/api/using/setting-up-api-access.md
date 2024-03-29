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
source-git-commit: 7ca7e9bd9541a4db708565e65e2ff87e44393238
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 11%

---

# API アクセスの設定 {#setting-up-api-access}

Adobe Campaign Standard API アクセスは、以下の手順で設定します。 これらの各手順について詳しくは、 [Adobe Developerドキュメント](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>で証明書を管理するには [Adobe Developer](https://developer.adobe.com/)を設定し、 **システム管理者** 組織または [開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html) Admin Console。

1. **電子証明書を持っていることを確認します**&#x200B;または必要に応じて作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe Campaign Service への新しい統合の作成** in [Adobe Developer](https://developer.adobe.com/) をクリックし、設定します。 資格情報が生成されます（API キー、クライアント秘密鍵。.）。
1. **JSON Web トークン (JWT) の作成** 以前に生成された資格情報から、秘密鍵で署名します。 JWT は、ID を検証し、API へのアクセス権を付与するためにAdobeが必要とするすべての ID およびセキュリティ情報をエンコードします。

   >[!AVAILABILITY]
   >
   >JWT（JSON web トークン）は、現在非推奨（廃止予定）の段階で、OAuth に置き換えられています。トランジションは、Campaign の今後のリリース内で段階的に実行され、ドキュメントはこれらの更新を反映して更新されます。

1. **アクセストークンとの JWT の交換** POST要求 このアクセストークンは、API リクエストの各ヘッダーで使用する必要があります。

セキュアなサービス間Adobe I/OAPI セッションを確立するには、Adobe サービスへのすべてのリクエストに、以下の情報を Authorization ヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**：これは個人の組織 ID です。各インスタンスに対してAdobeが提供する ID は 1 つです。

   * &lt;organization> ：実稼動インスタンス。
   * &lt;organization-mkt-stage>：ステージインスタンス。

  組織 ID 値を取得するには、管理者または担当のAdobe技術担当者にお問い合わせください。 また、新しい統合を作成する際に、Adobe I/Oに取得することもできます ( <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developerドキュメント</a>) をクリックします。

* **&lt;access_token>**:POSTリクエストを通じて JSON Web トークンを交換する際に取得された、個人用アクセストークン。

* **&lt;api_key>**：個人用 API キー。 Adobe Campaign Service への新しい統合を作成した後、Adobe I/Oで提供されます。

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
