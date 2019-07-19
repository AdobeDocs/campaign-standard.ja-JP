---
title: フィルタールール
seo-title: フィルタールール
description: フィルタールール
seo-description: フィルタールールを使用して、メッセージのオーディエンスを絞り込むことができます。
page-status-flag: 常にアクティブ化されていない
uuid: ed3eea62-3a47-4318- ae22- d82aa857448f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: working- with- typography- rules
discoiquuid: 7ddaf36c-74e6-4501- b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Filtering rules{#filtering-rules}

フィルタールールを使用すると、特定の数の電子メールを送信済みの隔離されたプロファイルやプロファイルなど、クエリで定義された条件に従ってメッセージターゲットの一部を除外できます。

例えば、ニュースレター購読者をフィルターして、18歳未満の購読者がコミュニケーションを受け取らないようにすることができます。

## Creating a filtering rule {#creating-a-filtering-rule}

1. **すべての通信チャネルに適用できるフィルター** タイポロジルールを作成します。

   ![](assets/typology_create-rule.png)

1. **[!UICONTROL Filtering criteria]** タブで **[!UICONTROL Subscription]** 、カテゴリ内の購読を選択します。

   ![](assets/typology_create-rule-subscription.png)

1. In the **[!UICONTROL Explorer]** tab of the query editor, drag and drop the **[!UICONTROL Subscriber]** node into the main part of the screen.

   ![](assets/typology_create-rule-subscriber.png)

1. Select the **[!UICONTROL Age]** field and define the filtering conditions so that the age of the subscribers is 18 or above.

   ![](assets/typology_create-rule-age.png)

1. **[!UICONTROL Typologies]** タブで、このルールをタイポロジにリンクします。

   ![](assets/typology_create-rule-typology.png)

1. 使用する配信テンプレートで、対象の誤字が選択されていることを確認してください。

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >To access the delivery templates, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** in the navigation menu, which can be accessed via the Adobe Campaign logo.

このルールがメッセージで使用されると、未成年者とみなされる購読者は自動的に除外されます。

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

送信するメッセージに応じて、フィルタリングルールの適用性を制限できます。

1. In the typology rule's **[!UICONTROL Application criteria]** tab, uncheck the **[!UICONTROL Apply the rule on all deliveries]** option, which is enabled by default.

   ![](assets/typology_limit.png)

1. クエリエディターを使用して、フィルターを定義します。例えば、ラベルが特定の単語で始まるメッセージまたは特定のレターがIDに含まれているメッセージのみにルールを適用できます。

   ![](assets/typology_limit-rule.png)

この場合、ルールは定義された条件に対応するメッセージにのみ適用されます。

## Default deliverability exclusion rules {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). 電子メール分析では、これらのルールは、受信者の電子メールアドレスと、配信品質インスタンスで管理される暗号化されたグローバル抑制リストに含まれているドメイン名またはドメイン名を比較します。一致がある場合、その受信者にメッセージは送信されません。

これは、悪意のあるアクティビティ（特にスパムの使用）のためブラックリストに記載されていることを防ぐためです。例えば、Webフォームの1つを介してスパムをサブスクライブするためにスパムトラッピングが使用されている場合、そのスパムに対して確認用の電子メールが自動的に送信され、これにより自動的にブラックリストに記載されます。

>[!NOTE]
>
>グローバル抑制リストに含まれるアドレスとドメイン名は非表示になります。除外された受信者数のみが配信分析ログに表示されます。

