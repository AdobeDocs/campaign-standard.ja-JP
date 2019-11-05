---
title: データモデルの概念
description: Adobe Campaignデータモデルとその変更方法について説明します。
page-status-flag: 非活性化の
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# データモデルの概念{#data-model-concepts}

Adobe Campaignには、事前定義されたデータモデルが付属しています。 このデータモデルは、既存のリソースに [新しいリソース](../../administration/using/users-management.md#functional-administrators) や拡張機能を追加できる管理者が変更できます。

>[!CAUTION]
>
>リソースの作成と変更は機密性の高い操作で、エキスパートユーザーのみが実行する必要があります。

Adobe Campaignロゴを介してアクセスする **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **&gt;**（メニュー）を使用すると、カスタムリソースの管理 **、発行** 、診断ツ ****&#x200B;ールへのアクセスが可能です。

Adobe Campaignで使用されるデータは、様々なリソースを通じて定義されます。

独自のカス **タムリソース(購入表や製品表** )を作成することで提供されるデータテンプレートを拡張できます。

そのまま使用できるリソース（キャンペーン、電子メール、オーディエンスなど）は変更できません。 ただし、カスタムリソースを拡張して新しいフィールドを追加することはできます。

>[!NOTE]
>
>あらかじめ用意されているリソースのデータモデル表現は、こちらで確認で [きます](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html)。

また、作成したリソ **ースに対応する画面で** 、ナビゲーションを設定することもできます。

拡張機能フィールドは、あらかじめ用意されているフィールドと競合しないように、プレフィックス付きで生成されます。
