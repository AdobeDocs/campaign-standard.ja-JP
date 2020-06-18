---
title: ランディングページテンプレート
description: ランディングページテンプレートについての詳細。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 12%

---


# ランディングページテンプレートについて {#landing-page-templates}

キャンペーンには、一連の組み込みランディングページテンプレートが付属しています。

* **[!UICONTROL Acquisition]**: これは、キャンペーンデータベースのデータを取得および更新できるランディングページのデフォルトテンプレートです。
* **[!UICONTROL Subscription]**: このテンプレートは、購読をサービスにオファーする際に使用します。
* **[!UICONTROL Unsubscription]**: このテンプレートは、購読者に送信される電子メールからサービスにリンクして、このサービスの購読を取り消すことができます。
* **[!UICONTROL Block list]**: このテンプレートは、プロファイルがキャンペーンから連絡を受けたくない場合に使用します。 ブロックリスト管理について詳しくは、キャンペーンでのオプトインとオプトアウトにつ [いてを参照してください](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

これらのテンプレートは、新しいランディングページを作成する際にデフォルトで提案されます。

![](assets/lp_creation_1.png)

ランディングページテンプレートにアクセスするには、左上隅のAdobe Campaignロゴをクリックし、 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** /を選択し **[!UICONTROL Landing page templates]**&#x200B;ます。

>[!NOTE]
>
>組み込みのテンプレートを複製して、独自のテンプレートを作成することをお勧めします。 一部のパラメーターは、ランディングページテンプレートでのみ設定でき、ランディングページーで直接変更することはできません。

テンプレートを作成する場合、 タグに「**type**」属性を追加することをお勧めします。この情報はエディターによって処理され、Webアプリケーションの設定時に、データベースフィールドをフォームフィールドにリンクするのに役立ちます。

テンプレート内の HTML コードの例：

```
<input id="email" type="email" name="email"/>
```

&#39;type&#39;属性の正式なリストは、次のアドレスで入手できます。 [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)