---
title: ランディングページテンプレート
description: ランディングページテンプレートについて説明します。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 29d1badf-9ce3-470c-9bdc-169586d2e943
TQID: 'https://experienceleague.adobe.com/vJyIRO33IjK6o3--ekx-Iw9K-GcIZMViLz9wEr-kxY0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 93%
---
# ランディングページテンプレートについて {#landing-page-templates}

Campaign には、次の一連のランディングページテンプレートがビルトインされています。

* **[!UICONTROL Acquisition]**：ランディングページのデフォルトテンプレートで、これを使用すると、Campaign データベースのデータを取得および更新できます。
* **[!UICONTROL Subscription]**：サービスのサブスクリプションをオファーする場合に使用するテンプレートです。
* **[!UICONTROL Unsubscription]**：サービスの購読登録者に送信されたメールからリンクできるテンプレートで、これを使用して登録者がこのサービスを登録解除できます。
* **[!UICONTROL Denylist]**：プロファイルが Campagin からの配信の受信を中止する場合に使用するテンプレートです。 ブロックリストに加えるの管理について詳しくは、[Campaignでのオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)を参照してください。

これらのテンプレートは、新しいランディングページを作成する際にデフォルトで提示されます。

![](assets/lp_creation_1.png)

ランディングページテンプレートにアクセスするには、左上隅の Adobe Campaign ロゴをクリックし、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Landing page templates]**&#x200B;を選択します。

>[!NOTE]
>
>ビルトインのテンプレートを複製して、独自のテンプレートを作成することをお勧めします。 一部のパラメーターは、ランディングページテンプレートでのみ設定可能で、ランディングページでは直接変更できません。

テンプレートを作成する場合は、「**type**」属性をタグに追加することをお勧めします。 この情報はエディターで処理され、Web アプリケーションの設定時に、ユーザーがデータベースフィールドをフォームフィールドにリンクするのに役立ちます。

テンプレート内の HTML コードの例：

```
<input id="email" type="email" name="email"/>
```

「type」属性の正式なリストは、[https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp) で入手できます。
