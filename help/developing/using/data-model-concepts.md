---
title: データモデルの概念
description: Adobe Campaignデータモデルとその変更方法を説明します。
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# データモデルの概念{#data-model-concepts}

Adobe Campaignには、事前定義されたデータモデルが付属しています。 このデータモデルは、既存のリソースに [新しい](../../administration/using/users-management.md#functional-administrators) 、または拡張機能を追加できる管理者が変更できます。

>[!CAUTION]
>
>リソースの作成と変更は、機密性の高い操作で、エキスパートユーザーのみが実行する必要があります。

Adobe Campaign **[!UICONTROL Administration]** のロゴを **[!UICONTROL Development]** 介してアクセスする>メニューを使用すると、カスタムリソースの管理、公開 ******、診断ツールへのアク******&#x200B;セスが可能です。

Adobe Campaignが使用するデータは、様々なリソースを通じて定義されます。 独自のカス **タムリソース(購入表** 、製品表など)を作成することで提供されるデータテンプレートを拡張できます。

組み込みリソース(キャンペーン、電子メール、オーディエンスなど)は変更できません。 ただし、カスタムリソースを拡張して新しいフィールドを追加することはできます。

拡張フィールドは、組み込みフィールドと競合しないように、プレフィックス付きで生成されます。

>[!NOTE]
>
>このページには、組み込みリソースのデータモデル表現が表 [示されます](../../developing/using/datamodel-introduction.md)。

また、作成したリ [ソースに対応する](configuring-the-screen-definition.md) 画面でナビゲーションを設定することもできます。

カスタムリソースの書き **出しや読み込みは** 、例えば開発から実稼働環境へと行えます。 詳しくは、この使用例 [を参照してください](../../automating/using/exporting-importing-custom-resources.md)。
