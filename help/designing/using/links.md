---
title: リンクの追加
description: Email Designerでリンクを管理する方法をご覧ください。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
TQID: https://experienceleague.adobe.com/5Cuvn5C61-SD6tCmXoG8NSgrarJe4ALXFknzTJBCcys
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 594
ht-degree: 13%

---

# リンクの追加 {#links}

## リンクの挿入 {#inserting-a-link}

このエディターを使用すると、HTMLのコンテンツ要素にリンクを挿入して、メールまたはランディングページをパーソナライズできます。

リンクを任意のページ要素（画像、単語、単語のグループ、テキストのブロックなど）に挿入できます。

>[!NOTE]
>
>以下の画像は、電子メールに[電子メール Designer](../../designing/using/designing-content-in-adobe-campaign.md)を使用してリンクを挿入する方法を示しています。

1. 要素を選択し、コンテキストツールバーから「**[!UICONTROL Insert link]**」をクリックします。

   ![](assets/des_insert_link.png)

1. 作成するリンクのタイプを選択します。

   * **外部リンク**：外部URLへのリンクを挿入します。

     URLにパーソナライゼーションを定義できます。 [URLのパーソナライズ ](personalization.md#personalizing-urls)を参照してください。

   * **ランディングページ**: Adobe Campaign ランディングページへのアクセス権を付与します。
   * **購読リンク**:Adobe Campaign サービスを購読するためのリンクを挿入します。
   * **購読解除リンク**:Adobe Campaign サービスから購読解除するためのリンクを挿入します。
   * アクションを定義する&#x200B;**リンク**：ランディングページ内の要素がクリックされたときにアクションを定義します。

     >[!NOTE]
     >
     >この種類のリンクは、ランディングページでのみ使用できます。

1. 受信者に表示されるテキストを変更できます。
1. ユーザーがリンクをクリックしたときにブラウザーの動作を設定できます（例えば、新しいウィンドウを開くなど）。

   >[!NOTE]
   >
   >ブラウザー動作の定義は、ランディングページにのみ適用されます。

1. 変更内容を保存します。

リンクを作成した後も、設定ペインで変更できます。 鉛筆アイコンをクリックして、そのパラメーターを編集します。

![](assets/des_link_edit.png)

[電子メール Designer](../../designing/using/designing-content-in-adobe-campaign.md)を使用して電子メールを編集する場合、電子メールに含まれているすべてのURLを一覧表示したテーブルから、作成したリンクに簡単にアクセスして変更できます。 このリストを使用すると、一元的に表示し、メールコンテンツ内の各URLを見つけることができます。 アクセスするには、[ トラッキング対象URLについて](#about-tracked-urls)を参照してください。

![](assets/des_link_list.png)

>[!NOTE]
>
>**ミラーページ URL**&#x200B;または&#x200B;**購読解除** リンクなどのパーソナライズされたURLは、このリストから変更できません。 その他のリンクはすべて編集可能です。

**関連トピック**：

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## トラッキング対象URLについて {#about-tracked-urls}

Adobe Campaignを使用すると、受信者がメールに含まれるURLをクリックしたときに、受信者の行動を追跡できます。 トラッキングについて詳しくは、[この節](../../sending/using/tracking-messages.md#about-tracking)を参照してください。

アクションバーの&#x200B;**[!UICONTROL Links]** アイコンには、追跡されるコンテンツのすべてのURLのリストが自動的に表示されます。

![](assets/des_links.png)

>[!NOTE]
>
>トラッキングはデフォルトで有効になっています。 この機能は、Adobe Campaignでトラッキングがアクティブ化されている場合にのみ、メールでのみ使用できます。 トラッキングパラメーターについて詳しくは、[この節](../../administration/using/configuring-email-channel.md#tracking-parameters)を参照してください。

各リンクのURL、カテゴリ、ラベル、トラッキングタイプは、このリストから変更できます。 リンクを編集するには、対応する鉛筆アイコンをクリックします。

![](assets/des_links_tracking.png)

トラッキング対象URLごとに、トラッキングモードを次のいずれかの値に設定できます。

* **トラッキング済み**：このURLでトラッキングをアクティブ化します。
* **ミラーページ**：この URL をミラーページの URL とみなします。
* **なし**：このURLのトラッキングをアクティブにしません。 この情報は保存されます。URLが今後のメッセージに再度表示された場合、そのトラッキングは自動的に非アクティブ化されます。
* **オプトアウト**：この URL をオプトアウトまたは購読解除 URL とみなします。

![](assets/des_link_tracking_type.png)

また、各URLのトラッキングをディアクティベートまたはアクティベートすることもできます。

>[!NOTE]
>
>Adobe Campaignでは、デフォルトで、**ミラーページ URL**&#x200B;と&#x200B;**購読解除** リンクを除くすべてのコンテンツ URLが追跡されます。

メッセージで使用されているURLに応じて、**[!UICONTROL Category]** フィールドを編集することで、URLを再グループ化できます。 これらのカテゴリは、例えば[URLやクリックストリーム ](../../reporting/using/urls-and-click-streams.md)のように、レポートに表示できます。

![](assets/des_link_tracking_category.png)

レポートを作成する場合、「**[!UICONTROL Components]**」タブで「**[!UICONTROL Dimension]**」を選択し、リストを下にスクロールしてトラッキングコンポーネントにアクセスします。 例えば、**[!UICONTROL Tracking URL Category]**&#x200B;をワークスペースにドラッグ&amp;ドロップして、クリックした各URLのトラッキングカテゴリに従って結果を表示します。

![](assets/des_link_tracking_report.png)

カスタマイズされたレポートの作成について詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。
