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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 79%

---

# データモデルの概念{#data-model-concepts}

Adobe Campaign には、事前定義済みのデータモデルが付属します。このデータモデルは、既存のリソースに新しいリソースやエクステンションを追加できる[管理者](../../administration/using/users-management.md#functional-administrators)が変更できます。

>[!CAUTION]
>
>リソースの作成と変更は機密性の高い操作で、エキスパートユーザーによってのみ実行される必要があります。

Adobe Campaign のロゴからアクセスできる **[!UICONTROL Administration]**／**[!UICONTROL Development]** メニューでは、**カスタムリソース**&#x200B;の管理と&#x200B;**公開**、**診断ツールへのアクセス**&#x200B;をおこなうことができます。

Adobe Campaign が使用するデータは、様々なリソースを通じて定義されます。購入テーブルや製品テーブルなど、独自のカスタムリソースを作成することで提供される&#x200B;**データテンプレートをエンリッチメント**&#x200B;できます。

組み込みのリソース（キャンペーン、メール、オーディエンスなど）は変更できません。ただし、カスタムリソースを拡張して新しいフィールドを追加することはできます。

拡張フィールドは、組み込みフィールドと競合しないように、プレフィックスを付けて生成されます。

>[!NOTE]
>
>組み込みリソースのデータモデル表現については、[ このページ ](../../developing/using/datamodel-introduction.md) を参照してください。

また、作成したリソースに対応する画面で[ナビゲーションを設定](configuring-the-screen-definition.md)することもできます。

開発環境から実稼働環境へのカスタムリソースの&#x200B;**エクスポートとインポート**&#x200B;が可能です。詳しくは、この[ステップバイステップの使用例](../../automating/using/exporting-importing-custom-resources.md)を参照してください。

>[!CAUTION]
>
>**[!UICONTROL Administration]** の役割と **すべて [&#128279;](../../administration/using/users-management.md#functional-administrators) ユニットへのアクセス権を持つ機能  管理者** のみが、送信ログ、メッセージログ、トラッキングログ、除外またはサブスクリプションログにアクセスできます。 管理者以外のユーザーは、これらのログをターゲットにすることができますが、これはリンクされたテーブル（プロファイル、配信）から開始します。
