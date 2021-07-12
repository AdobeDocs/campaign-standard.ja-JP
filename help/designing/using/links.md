---
solution: Campaign Standard
product: campaign
title: リンクの追加
description: Eメールデザイナーでリンクを管理する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Eメールデザイン
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 9%

---

# リンクの追加 {#links}

## リンクの挿入 {#inserting-a-link}

エディターを使用すると、HTMLコンテンツ要素にリンクを挿入して、Eメールまたはランディングページをパーソナライズできます。

リンクを任意のページ要素（画像、単語、単語のグループ、テキストのブロックなど）に挿入できます。

>[!NOTE]
>
>以下の画像では、Eメールに[Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)を使用してリンクを挿入する方法を示します。

1. 要素を選択し、コンテキストツールバーの「**[!UICONTROL Insert link]**」をクリックします。

   ![](assets/des_insert_link.png)

1. 作成するリンクのタイプを選択します。

   * **外部リンク**:外部URLへのリンクを挿入します。

      URLのパーソナライゼーションを定義できます。 [URLのパーソナライズ](../../designing/using/using-reusable-content.md#creating-a-content-fragment)を参照してください。

   * **ランディングページ**:Adobe Campaignランディングページへのアクセス権を付与します。
   * **購読リンク**:Adobe Campaignサービスを購読するためのリンクを挿入します。
   * **購読解除リンク**:Adobe Campaignサービスを購読解除するためのリンクを挿入します。
   * **アクションを定義するリンク**:ランディングページの要素がクリックされたときのアクションを定義します。

      >[!NOTE]
      >
      >このタイプのリンクは、ランディングページでのみ使用できます。

1. 受信者に表示するテキストを変更できます。
1. ユーザーがリンクをクリックしたときのブラウザーの動作を設定できます（例えば、新しいウィンドウを開く）。

   >[!NOTE]
   >
   >ブラウザーの動作の定義は、ランディングページにのみ適用されます。

1. 変更を保存します。

リンクを作成した後も、設定ペインから変更できます。 鉛筆アイコンをクリックして、そのパラメーターを編集します。

![](assets/des_link_edit.png)

[Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)でEメールを編集する際、Eメールに含まれるすべてのURLをリストする表から、作成したリンクに簡単にアクセスして変更できます。 このリストを使用すると、一元表示を作成し、Eメールコンテンツ内の各URLを特定できます。 これにアクセスするには、[追跡するURLについて](#about-tracked-urls)を参照してください。

![](assets/des_link_list.png)

>[!NOTE]
>
>**ミラーページのURL**&#x200B;や&#x200B;**購読解除**&#x200B;リンクなどのパーソナライズされたURLは、このリストからは変更できません。 その他のリンクはすべて編集可能です。

**関連トピック**：

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 追跡するURLについて {#about-tracked-urls}

Adobe Campaignでは、受信者がEメールに含まれているURLをクリックしたときの受信者の行動を追跡できます。 トラッキングについて詳しくは、[この節](../../sending/using/tracking-messages.md#about-tracking)を参照してください。

アクションバーの&#x200B;**[!UICONTROL Links]**&#x200B;アイコンに、追跡されるコンテンツのすべてのURLが自動的に表示されます。

![](assets/des_links.png)

>[!NOTE]
>
>トラッキングはデフォルトで有効になっています。 この機能は、Adobe Campaignでトラッキングが有効になっている場合にのみ、Eメールで使用できます。 トラッキングパラメーターについて詳しくは、[この節](../../administration/using/configuring-email-channel.md#tracking-parameters)を参照してください。

このリストから、各リンクのURL、カテゴリ、ラベルおよびトラッキングタイプを変更できます。 リンクを編集するには、対応する鉛筆アイコンをクリックします。

![](assets/des_links_tracking.png)

トラッキングするURLごとに、トラッキングモードを次のいずれかの値に設定できます。

* **追跡**:このURLのトラッキングを有効化します。
* **ミラーページ**：この URL をミラーページの URL とみなします。
* **なし**:は、このURLのトラッキングを有効化しません。この情報は保存されます。URLが今後のメッセージに再び表示される場合、そのトラッキングは自動的に無効化されます。
* **オプトアウト**：この URL をオプトアウトまたは購読解除 URL とみなします。

![](assets/des_link_tracking_type.png)

また、各URLのトラッキングを非アクティブ化またはアクティブ化することもできます。

>[!NOTE]
>
>Adobe Campaignでは、デフォルトで、**ミラーページURL**&#x200B;および&#x200B;**購読解除**&#x200B;リンクを除くすべてのコンテンツURLが追跡されます。

メッセージで使用されているURLに応じて&#x200B;**[!UICONTROL Category]**&#x200B;フィールドを編集することで、URLを再グループ化できます。 これらのカテゴリは、[URLやクリックストリーム](../../reporting/using/urls-and-click-streams.md)などのレポートに表示できます。

![](assets/des_link_tracking_category.png)

レポートを作成する際に、「**[!UICONTROL Components]**」タブから「**[!UICONTROL Dimension]**」を選択し、リストを下にスクロールしてトラッキングコンポーネントにアクセスします。 例えば、**[!UICONTROL Tracking URL Category]**&#x200B;をワークスペースにドラッグ&amp;ドロップして、クリックされた各URLのトラッキングカテゴリに従って結果を表示します。

![](assets/des_link_tracking_report.png)

カスタマイズされたレポートの作成について詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。
