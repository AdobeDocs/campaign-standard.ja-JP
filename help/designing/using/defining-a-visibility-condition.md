---
title: 表示条件の定義
seo-title: 表示条件の定義
description: 表示条件の定義
seo-description: 特定の条件が考慮されている場合にのみ、Webページ要素を表示します。
page-status-flag: 常にアクティブ化されていない
uuid: 224005ba- ef09-4790- b2f0-30ed74cfa32d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: 定義条件コンテンツ
discoiquuid: c12125a7- a1cf-4bc1- a138-57ff74974024
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining a visibility condition{#defining-a-visibility-condition}

表示条件は、任意の要素に対して指定できます。条件が満たされた場合にのみ表示されます。

To add a visibility condition, select a block and enter the condition to be respected in the **[!UICONTROL Visibility condition]** field of its settings.

![](assets/delivery_content_5.png)

このオプションは、次の要素でのみ使用できます。ADDRESS、BROWQUEMTE、CENTER、DIR、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

The expression editor is presented in the [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) section.

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). デフォルトでは、すべてのフィールドが表示されます。

>[!NOTE]
>
>動的コンテンツのあるサブ要素または既に動的コンテンツを構成するブロックを含むブロックに対しては、条件を定義できません。ドロップダウンリストのような非表示の動的ブロックは編集できません。

