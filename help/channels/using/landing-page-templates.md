---
title: ランディングページテンプレート
description: ランディングページテンプレートの詳細。
page-status-flag: 非活性化の
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: レメイト
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ランディングページテンプレートについて {#landing-page-templates}

Campaignには、一連のランディングページテンプレートが組み込まれています。

* **[!UICONTROL Acquisition]**:これはランディングページのデフォルトのテンプレートで、Campaignデータベースのデータを取得および更新できます。
* **[!UICONTROL Subscription]**:このテンプレートは、サービスの購読を提供するために使用します。
* **[!UICONTROL Unsubscription]**:このテンプレートは、購読者がこのサービスを登録解除できるように、サービスの購読者に送信する電子メールからリンクできます。
* **[!UICONTROL Blacklist]**:このテンプレートは、プロファイルがキャンペーンから連絡を受けたくない場合に使用します。 ブラックリストの詳細については、「Campaignでのオ [プトインとオプトアウトについて」を参照してください](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

これらのテンプレートは、新しいランディングページを作成する際にデフォルトで提案されます。

![](assets/lp_creation_1.png)

ランディングページテンプレートにアクセスするには、左上隅にあるAdobe Campaignロゴをクリックし、//を **[!UICONTROL Resources]** 選択 **[!UICONTROL Templates]** しま **[!UICONTROL Landing page templates]**&#x200B;す。

>[!NOTE]
>
>組み込みのテンプレートを複製して、独自のテンプレートを作成することをお勧めします。 一部のパラメータはランディングページテンプレートでのみ設定でき、ランディングページで直接変更することはできません。

When building a template, we recommend adding a **'type'** attribute to tags. この情報はエディターによって処理され、Webアプリケーションの設定時にデータベースフィールドをフォームフィールドにリンクするのに役立ちます。

テンプレート内の HTML コードの例：

```
<input id="email" type="email" name="email"/>
```

「type」属性の公式リストは、次のアドレスで入手できます。http://www.w3schools.com/tags/att_input_type.asp [](http://www.w3schools.com/tags/att_input_type.asp)