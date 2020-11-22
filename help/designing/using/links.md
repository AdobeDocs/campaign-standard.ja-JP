---
solution: Campaign Standard
product: campaign
title: リンクの追加
description: 電子メールデザイナでリンクを管理する方法を確認します。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 8%

---


# リンクの追加 {#links}

## リンクの挿入 {#inserting-a-link}

このエディターを使用すると、HTMLコンテンツ要素にリンクを挿入して、電子メールやランディングページをパーソナライズできます。

リンクを任意のページ要素（画像、単語、単語のグループ、テキストのブロックなど）に挿入できます。

>[!NOTE]
>
>次の画像は、電子メールに [EメールDesignerを使用してリンクを挿入する方法を示しています](../../designing/using/designing-content-in-adobe-campaign.md) 。

1. 要素を選択し、コンテキストツールバー **[!UICONTROL Insert link]** からをクリックします。

   ![](assets/des_insert_link.png)

1. 作成するリンクのタイプを選択します。

   * **外部リンク**:外部URLへのリンクを挿入します。

      URLのパーソナライズを定義できます。 詳しくは、URLの [個人化を参照してください](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

   * **ランディングページ**:adobe campaignランディングページへのアクセスを許可します。
   * **購読リンク**:adobe campaignサービスを購読するためのリンクを挿入します。
   * **購読解除リンク**:adobe campaignサービスの登録を解除するためのリンクを挿入します。
   * **アクションを定義するリンク**:ランディングページ内の要素をクリックしたときのアクションを定義します。

      >[!NOTE]
      >
      >このタイプのリンクは、ランディングページに対してのみ使用できます。

1. 受信者に表示されるテキストを変更できます。
1. ユーザがリンクをクリックしたときのブラウザーの動作を設定できます（例えば、新しいウィンドウを開く）。

   >[!NOTE]
   >
   >ブラウザーの動作の定義は、ランディングページにのみ適用されます。

1. 変更を保存します。

リンクを作成した後も、[設定]ペインで変更できます。 鉛筆アイコンをクリックして、パラメータを編集します。

![](assets/des_link_edit.png)

電子メールデザイナーで電子メールを編集する場合 [](../../designing/using/designing-content-in-adobe-campaign.md)、電子メールに含まれるすべてのURLを一覧表示した表から、作成したリンクに簡単にアクセスして変更できます。 このリストにより、表示を一元化し、電子メールコンテンツ内の各URLを特定できます。 アクセスするには、追跡対象URL [についてを参照してください](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>このリストでは、 **ミラーページURL** 、 **購読解除** リンクなど、パーソナライズされたURLを変更できません。 他のすべてのリンクは編集可能です。

**関連トピック**：

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 追跡するURLについて {#about-tracked-urls}

Adobe Campaignを使用すると、受信者が電子メールに含まれるURLをクリックしたときの行動を追跡できます。 For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

アクションバーの **[!UICONTROL Links]** アイコンには、追跡するコンテンツのすべてのURLのリストが自動的に表示されます。

![](assets/des_links.png)

>[!NOTE]
>
>トラッキングはデフォルトでアクティブ化されます。 この機能は、Adobe Campaignでトラッキングが有効になっている場合、電子メールでのみ使用できます。 For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

各リンクのURL、カテゴリ、ラベルおよび追跡タイプは、このリストで変更できます。 リンクを編集するには、対応する鉛筆アイコンをクリックします。

![](assets/des_links_tracking.png)

追跡する各URLに対して、追跡モードを次のいずれかの値に設定できます。

* **追跡**:このURLのトラッキングをアクティブにします。
* **ミラーページ**：この URL をミラーページの URL とみなします。
* **なし**:は、このURLの追跡をアクティブにしません。 この情報は保存されます。その後のメッセージでURLが再び表示される場合、その追跡は自動的に非アクティブになります。
* **オプトアウト**：この URL をオプトアウトまたは購読解除 URL とみなします。

![](assets/des_link_tracking_type.png)

また、各URLのトラッキングを非アクティブ化したり、アクティブ化したりすることもできます。

>[!NOTE]
>
>Adobe Campaignでは、デフォルトで、 **ミラーページURLと** 購読解除 **** リンクを除くすべてのコンテンツURLが追跡されます。

メッセージで使用されているURLに応じて、 **[!UICONTROL Category]** フィールドを編集することで、URLを再グループ化できます。 These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

レポートを作成する際に、 **[!UICONTROL Components]** タブでリストを選択し **[!UICONTROL Dimension]** て下にスクロールし、トラッキングコンポーネントにアクセスします。 例えば、ワークスペースにドラッグ&amp;ドロップ **[!UICONTROL Tracking URL Category]** すると、各クリックされたURLの追跡カテゴリに従って結果が表示されます。

![](assets/des_link_tracking_report.png)

カスタマイズレポートの作成について詳しくは、 [このセクションを参照してください](../../reporting/using/about-dynamic-reports.md)。
