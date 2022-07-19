---
title: リンクの追加
description: E メールデザイナーでリンクを管理する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: 146dfea38bd456a5d9200b0632d4aa279b10a7b9
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 9%

---

# リンクの追加 {#links}

## リンクの挿入 {#inserting-a-link}

エディターでは、HTMLコンテンツ要素にリンクを挿入して、E メールまたはランディングページをパーソナライズできます。

リンクを任意のページ要素（画像、単語、単語のグループ、テキストのブロックなど）に挿入できます。

>[!NOTE]
>
>以下の画像は、 [メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md) を電子メールで送信します。

1. 要素を選択し、 **[!UICONTROL Insert link]** を選択します。

   ![](assets/des_insert_link.png)

1. 作成するリンクのタイプを選択します。

   * **外部リンク**:外部 URL へのリンクを挿入します。

      URL のパーソナライゼーションを定義できます。 詳しくは、 [パーソナライズされた URL](personalization.md#personalizing-urls).

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

1. 変更内容を保存します。

リンクを作成した後でも、設定ペインから変更できます。 鉛筆アイコンをクリックして、そのパラメーターを編集します。

![](assets/des_link_edit.png)

電子メールを編集する際に、 [メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)を使用すると、電子メールに含まれるすべての URL を一覧表示する表から、作成したリンクに簡単にアクセスして変更できます。 このリストを使用すると、一元表示が可能になり、E メールコンテンツ内の各 URL を特定できます。 アクセスするには、 [トラッキングする URL について](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>パーソナライズされた URL( 例： **ミラーページの URL** または **購読解除** このリストからはリンクを変更できません。 その他のリンクはすべて編集可能です。

**関連トピック**：

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## トラッキングする URL について {#about-tracked-urls}

Adobe Campaignでは、受信者が E メールに含まれている URL をクリックしたときの行動を追跡できます。 トラッキングについて詳しくは、[この節](../../sending/using/tracking-messages.md#about-tracking)を参照してください。

この **[!UICONTROL Links]** アクションバーのアイコンは、追跡されるコンテンツのすべての URL のリストを自動的に表示します。

![](assets/des_links.png)

>[!NOTE]
>
>トラッキングはデフォルトで有効化されています。 この機能は、Adobe Campaignでトラッキングが有効になっている場合にのみ、E メールで使用できます。 トラッキングパラメーターについて詳しくは、 [この節](../../administration/using/configuring-email-channel.md#tracking-parameters).

このリストから、各リンクの URL、カテゴリ、ラベルおよびトラッキングタイプを変更できます。 リンクを編集するには、対応する鉛筆アイコンをクリックします。

![](assets/des_links_tracking.png)

トラッキングする URL ごとに、トラッキングモードを次のいずれかの値に設定できます。

* **追跡**:この URL のトラッキングを有効化します。
* **ミラーページ**：この URL をミラーページの URL とみなします。
* **なし**:この URL のトラッキングを有効化しません。 この情報は保存されます。URL が今後のメッセージに再び表示される場合、そのトラッキングは自動的に無効化されます。
* **オプトアウト**：この URL をオプトアウトまたは購読解除 URL とみなします。

![](assets/des_link_tracking_type.png)

また、URL ごとにトラッキングを非アクティブ化したり、アクティブ化したりすることもできます。

>[!NOTE]
>
>Adobe Campaignでは、デフォルトで、 **ミラーページの URL** および **購読解除** リンク。

URL を再グループ化するには、 **[!UICONTROL Category]** フィールドに値を入力する必要があります。 これらのカテゴリは、レポートに表示できます。例えば、 [URL とクリックストリーム](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

レポートを作成する際に、 **[!UICONTROL Components]** タブ、選択 **[!UICONTROL Dimension]** をクリックし、リストを下にスクロールしてトラッキングコンポーネントにアクセスします。 例えば、「 」をドラッグ&amp;ドロップします。 **[!UICONTROL Tracking URL Category]** をワークスペースに表示し、クリックされた各 URL のトラッキングカテゴリに従って結果を表示します。

![](assets/des_link_tracking_report.png)

カスタマイズされたレポートの作成について詳しくは、 [この節](../../reporting/using/about-dynamic-reports.md).
