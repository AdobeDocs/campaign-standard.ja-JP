---
title: ランディングページテンプレート
description: 詳しくは、テンプレートに関するランディングページを参照してください。
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# ランディングページテンプレートについて {#landing-page-templates}

キャンペーンには、一連の組み込みテンプレートが付属しています。ランディングページテンプレート：

* **[!UICONTROL Acquisition]**:これは、データベースのデフォルトのランディングページで、データを取得および更新できるキャンペーンです。
* **[!UICONTROL Subscription]**:このテンプレートは、サービスへのオファー購読に使用します。
* **[!UICONTROL Unsubscription]**:このテンプレートは、購読者がサービスを購読解除できるように、購読者に送信する電子メールからリンクできます。
* **[!UICONTROL Blacklist]**:このテンプレートは、プロファイルが連絡を取りたくない場合に使用します。キャンペーン。 ブラックリストの詳細については、「オプトイ [ンとオプトアウトのキャンペーン](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)」を参照してください。

これらのテンプレートは、新しいテンプレートを作成する際にデフォルトで提案されるランディングページです。

![](assets/lp_creation_1.png)

ランディングページテンプレートにアクセスするには、左上隅のAdobe Campaignロゴをクリックし、/ **[!UICONTROL Resources]** を選択 **[!UICONTROL Templates]** しま **[!UICONTROL Landing page templates]**&#x200B;す。

>[!NOTE]
>
>組み込みのテンプレートを複製して、独自のテンプレートを作成することをお勧めします。 一部のパラメーターは、ランディングページテンプレートでのみ設定でき、パラメーター内で直接変更することはできないランディングページーもあります。

テンプレートを作成する場合、 タグに「**type**」属性を追加することをお勧めします。この情報はエディターによって処理され、Webアプリケーションの設定時にデータベースフィールドをフォームフィールドにリンクするのに役立ちます。

テンプレート内の HTML コードの例：

```
<input id="email" type="email" name="email"/>
```

&#39;type&#39;属性の公式リストは、次のアドレスで入手できます。https://www.w3schools.com/tags/att_input_type.asp [](https://www.w3schools.com/tags/att_input_type.asp)