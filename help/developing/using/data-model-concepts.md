---
title: データモデルの概念
description: Adobe Campaign データモデルとその変更方法について説明します。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 6e9e016a-473b-4a51-8bd6-c23c7b3d3610
TQID: https://experienceleague.adobe.com/jOKJ64oRWaLCf7C9V8ZTbrtSphd4cJrGLlyw0K4sFB8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 79%

---

# データモデルの概念{#data-model-concepts}

Adobe Campaign には、事前定義済みのデータモデルが付属します。 このデータモデルは、既存のリソースに新しいリソースやエクステンションを追加できる[管理者](../../administration/using/users-management.md#functional-administrators)が変更できます。

>[!CAUTION]
>
>リソースの作成と変更は機密性の高い操作で、エキスパートユーザーによってのみ実行される必要があります。

Adobe Campaign のロゴからアクセスできる **[!UICONTROL Administration]**／**[!UICONTROL Development]** メニューでは、**カスタムリソース**&#x200B;の管理と&#x200B;**公開**、**診断ツールへのアクセス**&#x200B;をおこなうことができます。

Adobe Campaign が使用するデータは、様々なリソースを通じて定義されます。 購入テーブルや製品テーブルなど、独自のカスタムリソースを作成することで提供される&#x200B;**データテンプレートをエンリッチメント**&#x200B;できます。

ビルトインのリソース（キャンペーン、メール、オーディエンスなど）は変更できません。 ただし、カスタムリソースを拡張して新しいフィールドを追加することはできます。

拡張フィールドは、ビルトインのフィールドと競合しないように、接頭辞を付けて生成されます。

>[!NOTE]
>
>組み込みリソースのデータモデル表現は、[このページ &#x200B;](../../developing/using/datamodel-introduction.md)にあります。

また、作成したリソースに対応する画面で[ナビゲーションを設定](configuring-the-screen-definition.md)することもできます。

開発環境から本番環境へのカスタムリソースの&#x200B;**エクスポートとインポート**&#x200B;が可能です。 詳しくは、この[ステップバイステップの使用例](../../automating/using/exporting-importing-custom-resources.md)を参照してください。

>[!CAUTION]
>
>**[!UICONTROL Administration]**&#x200B;の役割と&#x200B;**すべての** ユニットへのアクセス権を持つ機能的な[管理者](../../administration/using/users-management.md#functional-administrators)のみが、送信ログ、メッセージログ、トラッキングログ、除外ログまたはサブスクリプションログにアクセスできます。 管理者以外のユーザーは、これらのログをターゲットにできますが、リンクされたテーブル（プロファイル、配信）から開始します。
