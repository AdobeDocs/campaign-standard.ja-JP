---
title: データモデルの概念
seo-title: データモデルの概念
description: データモデルの概念
seo-description: Adobe Campaignのデータモデルと、その変更方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: about- custom- resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource， overview;EventCusResource、概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Data model concepts{#data-model-concepts}

Adobe Campaignには、事前定義済みのデータモデルが付属しています。This data model can be modified by [administrators](../../administration/using/users-management.md#functional-administrators) who are able to add new resources or extensions to existing resources.

>[!CAUTION]
>
>リソースの作成と変更は、エキスパートユーザーのみが実行する必要がある、機密性の高い操作です。

**[!UICONTROL Administration]** Adobe **[!UICONTROL Development]** Campaignロゴを使用してアクセスし、 **カスタムリソースを管理**&#x200B;し、それらを **公開** し、診断ツール **にアクセスすることができ**&#x200B;ます。

Adobe Campaignで使用されるデータは、様々なリソースによって定義されます。

You can **enrich the data template** that is provided by creating your own custom resources, such as purchase or product tables.

あらかじめ用意されているリソース（キャンペーン、電子メール、オーディエンスなど）は変更できません。ただし、カスタムリソースを拡張して新しいフィールドを追加できます。

>[!NOTE]
>
>You can find a datamodel representation for the out-of-the-box resources [here](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

You can also **configure the navigation** in the screens corresponding to the resource created.

拡張フィールドはプレフィックス付きで生成され、すぐに使用できるフィールドと競合しません。
