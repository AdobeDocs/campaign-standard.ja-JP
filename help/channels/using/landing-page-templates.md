---
solution: Campaign Standard
product: campaign
title: ランディングページテンプレート
description: ランディングページテンプレートについて説明します。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ランディングページテンプレートについて {#landing-page-templates}

Campaign には、次の一連のランディングページテンプレートが用意されています。

* **[!UICONTROL Acquisition]**：ランディングページのデフォルトテンプレートで、これを使用すると、Campaign データベースのデータを取得および更新できます。
* **[!UICONTROL Subscription]**：サービスのサブスクリプションをオファーする場合に使用するテンプレートです。
* **[!UICONTROL Unsubscription]**：サービスの購読登録者に送信された E メールからリンクできるテンプレートで、これを使用して登録者がこのサービスを登録解除できます。
* **[!UICONTROL Denylist]**：プロファイルが Campagin からの配信の受信を中止する場合に使用するテンプレートです。キャンペーン管理について詳しくは、[オプトインとオプトアウトについての](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)を参照してください。

これらのテンプレートは、新しいランディングページを作成する際にデフォルトで提示されます。

![](assets/lp_creation_1.png)

ランディングページテンプレートにアクセスするには、左上隅の Adobe Campaign ロゴをクリックし、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Landing page templates]**&#x200B;を選択します。

>[!NOTE]
>
>組み込みのテンプレートを複製して、独自のテンプレートを作成することをお勧めします。一部のパラメーターは、ランディングページテンプレートでのみ設定可能で、ランディングページでは直接変更できません。

テンプレートを作成する場合は、「**type**」属性をタグに追加することをお勧めします。この情報はエディターで処理され、Web アプリケーションの設定時に、ユーザーがデータベースフィールドをフォームフィールドにリンクするのに役立ちます。

テンプレート内の HTML コードの例：

```
<input id="email" type="email" name="email"/>
```

「type」属性の正式なリストは、[https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp) で入手できます。

