---
title: データモデルの概念
description: Adobe Campaign データモデルとその変更方法について説明します。
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
translation-type: ht
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401
workflow-type: ht
source-wordcount: '207'
ht-degree: 100%

---


# データモデルの概念{#data-model-concepts}

Adobe Campaign には、事前定義済みのデータモデルが付属します。このデータモデルは、既存のリソースに新しいリソースやエクステンションを追加できる[管理者](../../administration/using/users-management.md#functional-administrators)が変更できます。

>[!CAUTION]
>
>リソースの作成と変更は機密性の高い操作で、エキスパートユーザーによってのみ実行される必要があります。

Adobe Campaign のロゴからアクセスできる **[!UICONTROL Administration]**／**[!UICONTROL Development]** メニューでは、**カスタムリソース**&#x200B;の管理と&#x200B;**公開**、**診断ツールへのアクセス**&#x200B;をおこなうことができます。

Adobe Campaign が使用するデータは、様々なリソースを通じて定義されます。購入テーブルや製品テーブルなど、独自のカスタムリソースを作成することで提供される&#x200B;**データテンプレートをエンリッチメント**&#x200B;できます。

組み込みのリソース（キャンペーン、E メール、オーディエンスなど）は変更できません。ただし、カスタムリソースを拡張して新しいフィールドを追加することはできます。

拡張フィールドは、組み込みフィールドと競合しないように、プレフィックスを付けて生成されます。

>[!NOTE]
>
>[このページ](../../developing/using/datamodel-introduction.md)では、組み込みリソースのデータモデル表示域を参照できます。

また、作成したリソースに対応する画面で[ナビゲーションを設定](configuring-the-screen-definition.md)することもできます。

開発環境から実稼働環境へのカスタムリソースの&#x200B;**エクスポートとインポート**&#x200B;が可能です。詳しくは、この[ステップバイステップの使用例](../../automating/using/exporting-importing-custom-resources.md)を参照してください。
