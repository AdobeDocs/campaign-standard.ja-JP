---
title: APIアクセスの設定
description: Campaign StandardAPIへのアクセスを設定する方法を説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# API アクセスの設定 {#setting-up-api-access}

Adobe Campaign StandardAPIアクセスは、次の手順で設定します。 これらの各手順については、 [AdobeIOドキュメントで詳しく説明しています](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!IMPORTANT]
>
>AdobeI/Oで証明書を管理するには、組織の <b>システム管理者</b> 権限または管理コンソールの [開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> があることを確認します。

1. **デジタル証明書をお持ちであることを確認するか**、必要に応じて証明書を作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **AdobeI/OのAdobe Campaignサービス** への新しい統合を作成し、設定します。 次に、資格情報が生成されます（APIキー、クライアントシークレット。.）。
1. **以前に生成した秘密鍵証明書からJSON Web Token(JWT)** を作成し、秘密鍵で署名します。 JWTは、AdobeがIDを確認し、APIへのアクセスを許可するために必要なすべてのID情報とセキュリティ情報をエンコードします。
1. **POSTリクエストを通じて、JWTをアクセストークン** と交換します。 このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュリティで保護されたサービス間AdobeI/O APIセッションを確立するには、Adobeサービスへのすべての要求を、次の情報をAuthorizationヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;組織>**:これは個人の組織IDです。各インスタンスに対して1つの組織IDがAdobeによって提供されます。

   * &lt;組織>:実稼働インスタンス
   * &lt;ORGANIZATION-mkt-stage>:ステージインスタンス。

   組織IDの値を取得するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。 新しい統合を作成する際に、AdobeI/Oに取得することもできます( <a href="https://www.adobe.io/authentication.html">AdobeI/Oのドキュメントを参照</a>)。

* **&lt;ACCESS_TOKEN>**:POSTリクエストを介してJSON Webトークンを交換する際に取得された個人アクセストークン。

* **&lt;API_KEY>**:個人のAPIキーを参照してください。 Adobe Campaignサービスへの新しい統合を作成した後、AdobeI/Oで提供されます。

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