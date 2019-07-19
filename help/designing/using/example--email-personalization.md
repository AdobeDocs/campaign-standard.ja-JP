---
title: 「例:電子メールのパーソナライゼーション」
seo-title: 「例:電子メールのパーソナライゼーション」
description: 「例:電子メールのパーソナライゼーション」
seo-description: 動的なコンテンツとプロファイルの年齢に従って、動的なコンテンツとテキストを持つ電子メールの例をご覧ください。
page-status-flag: 常にアクティブ化されていない
uuid: 3d30213c-474f-4e5f-8688-9260ea2e2583
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: personalizing- content
discoiquuid: d1b618ac- a842-41e8-9ba6-7a50f7315b02
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Example: Email personalization{#example-email-personalization}

この例では、マーケティングサービスチームのメンバーが、特別なオファーのみがあることをクライアントに通知する電子メールを作成しました。チームメンバーは、クライアントの年齢に従って電子メールをパーソナライズすることを決定しました。18才から27才までのお客様は、異なる画像を含む電子メールを受け取り、27歳より古いクライアントが受信したものにスローガンを送信します。

電子メールは次のように作成されます。

* 動的コンテンツは画像に適用され、動的コンテンツは年齢の範囲に従って設定されます。

   ![](assets/delivery_content_43.png)

   Adding and configuring dynamic content is detailed in the [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md) section.

* パーソナライゼーションフィールドと動的コンテンツは、テキストに適用されます。プロファイルの年齢の範囲に応じて、電子メールはプロファイルの最初の名前またはプロファイルのタイトルと姓のいずれかで始まります。

   ![](assets/delivery_content_44.png)

   Adding and configuring the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

## Configuring images {#configuring-images}

この例では、画像に適用される動的コンテンツは次のように設定されます。

**18~27歳のターゲットにするには:**

1. Select the dynamic content in the **[!UICONTROL Properties]** palette and click the **[!UICONTROL Edit]** button.

   ![](assets/delivery_content_48.png)

1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.

   ![](assets/delivery_content_49.png)

1. **「次よりも大きい」または「等しい** 」演算子を選択し、 **18** と入力して18より **前の** 式を作成します。

   ![](assets/delivery_content_50.png)

1. **[!UICONTROL Age]** 新しい条件を追加します。

   **「次より小さい」または「等しい** 」演算子を選択し、値フィールドで27を指定して、27より **前の** 式を作成します。

   ![](assets/delivery_content_51.png)

1. 変更を確認します。

**27歳以上のプロファイルをターゲットにするには:**

1. パレットから動的コンテンツを選択し、編集します。
1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.
1. **"greater than** 」演算子を追加し、値フィールドに27と入力して、27より **前の** 式を作成します。

   ![](assets/delivery_content_52.png)

1. 変更を確認します。

動的なコンテンツが正しく設定されている。

## Configuring text {#configuring-text}

この例では、テキストに適用される動的コンテンツは次のように設定されます。

**18~27才のプロファイルをターゲットにするには:**

1. 目的の構造コンポーネントを選択し、動的コンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット設定式を設定します。Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. In the list that appears, select the **[!UICONTROL First name]** field and confirm.

   ![](assets/delivery_content_54.png)

1. パーソナライゼーションフィールドは、選択した動的コンテンツに完全に挿入されます。

**27歳以上のプロファイルをターゲットにするには:**

1. 目的の構造コンポーネントを選択し、動的コンテンツを追加します。
1. 動的コンテンツを編集し、ターゲット設定式を設定します。Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.
1. Select **[!UICONTROL Title]** from the drop-down list.
1. Proceed similarly to add the **[!UICONTROL Last name]** field.

   ![](assets/delivery_content_56.png)

パーソナライゼーションフィールドは、選択した動的コンテンツに完全に挿入されるようになりました。

## Previewing emails {#previewing-emails}

Previewing allows you to check that the personalization fields and the dynamic contents are configured correctly before sending the **[!UICONTROL Proofs]**. プレビュー中に、電子メールターゲットに対応する異なるテストプロファイルを選択できます。

テストプロファイルがない場合、デフォルトで表示される電子メールは次のとおりです。

![](assets/delivery_content_45.png)

電子メールには、スローガンにパーソナライゼーションフィールドが含まれておらず、デフォルトの画像が使用されます。

最初のテストプロファイルは、18~27の間に古くなったクライアントに対応します。このプロファイルを選択すると、次の電子メールが表示されます。

![](assets/delivery_content_46.png)

18~27年前の式に対応するパーソナライゼーションフィールド、具体的にはプロファイルの最初の名前が正しく設定され、画像もプロファイルに従って変更されます。

2つ目のプロファイルは、27を超えるクライアントに対応し、次の電子メールを生成します。

![](assets/delivery_content_47.png)

動的コンテンツに基づいて画像が変更され、表示されるスローガンがこのターゲット公開に定義されたより公式なスロガンになりました。

**関連トピック:**

* [オーディエンスの作成](../../audiences/using/creating-audiences.md)
* [送信の準備](../../sending/using/preparing-the-send.md)

