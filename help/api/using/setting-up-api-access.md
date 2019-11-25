---
title: APIアクセスの設定
description: キャンペーン標準APIへのアクセスを設定する方法について説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# APIアクセスの設定 {#setting-up-api-access}

Adobe Campaign Standard APIアクセスは、次の手順で設定します。 これらの各手順について詳しくは、 [Adobe IOドキュメントを参照してください](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>Adobe IOで証明書を管理するには、組織のシステム管理者権限または管理コンソ <b>ールの開発者アカウン</b> トを持っている <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html"></a> ことを確認します。

1. **デジタル証明書があることを確認するか**、必要に応じて証明書を作成します。 次の手順では、証明書と共に提供される公開鍵と秘密鍵が必要です。
1. **Adobe IOでAdobe Campaign Serviceへの新しい統合を作成し** 、設定します。 その後、資格情報が生成されます（APIキー、クライアントシークレット…）。
1. **以前に生成した資格情報からJSON Web Token(JWT)** を作成し、秘密鍵で署名します。 JWTは、アドビがIDを確認し、APIへのアクセスを許可するために必要なIDとセキュリティ情報をすべてエンコードします。
1. **POSTリクエストを使用してJWTをアクセストークン** と交換します。 このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

安全なサービス間Adobe I/O APIセッションを確立するには、アドビサービスに対するすべての要求に以下の情報をAuthorizationヘッダーに含める必要があります。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;組織&gt;**:これは個人の組織IDで、各インスタンスに対してアドビから1つの組織IDが提供されます。

   * &lt;組織&gt;:実稼働インスタンス
   * &lt;ORGANIZATION-mkt-stage&gt;:ステージインスタンス。
   組織IDの値を取得するには、管理者またはアドビのテクニカルコンタクトに問い合わせてください。 また、新しい統合を作成する際にAdobe I/Oに取得することもできます( <a href="https://www.adobe.io/authentication.html">Adobe IOのドキュメントを参照</a>)。

* **&lt;ACCESS_TOKEN&gt;**:POSTリクエストを介してJSON webトークンを交換する際に取得された個人用アクセストークン。

* **&lt;API_KEY&gt;**:個人APIキーを参照してください。 Adobe Campaign Serviceへの新しい統合を作成した後、Adobe I/Oで提供されます。

   ![代替テキスト](assets/tenant.png)
