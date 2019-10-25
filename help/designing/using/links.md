---
title: リンクの管理
seo-title: リンクの管理
description: 'リンクの管理 '
seo-description: 電子メールデザイナーでのリンクの管理方法を確認します。
page-status-flag: 非活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1ccea1d142f0b1550c8891b2f31233af8c9d4e29

---


# リンク {#links}

## リンクの挿入 {#inserting-a-link}

このエディターを使用すると、HTMLコンテンツ要素にリンクを挿入して、電子メールページやランディングページをパーソナライズできます。

リンクを任意のページ要素（画像、単語、単語のグループ、テキストのブロックなど）に挿入できます。

>[!NOTE]
>
>次の画像は、電子メールデザイナーを使用した電子メール [へのリンクの挿入](../../designing/using/overview.md) 方法を示しています。

1. 要素を選択し、コンテキストツール **[!UICONTROL Insert link]** バーからをクリックします。

   ![](assets/des_insert_link.png)

1. 作成するリンクのタイプを選択します。

   * **外部リンク**:外部URLへのリンクを挿入します。

      URLのパーソナライゼーションを定義できます。 詳しくは、URL [のパーソナライズを参照してくださ](../../designing/using/using-reusable-content.md#creating-a-content-fragment)い。

   * **ランディングページ**:adobe Campaignのランディングページへのアクセスを許可します。
   * **購読リンク**:adobe Campaignサービスを購読するためのリンクを挿入します。
   * **購読解除リンク**:adobe Campaignサービスの購読を解除するリンクを挿入します。
   * **アクションを定義するリンク**:ランディングページ内の要素がクリックされたときのアクションを定義します。

      >[!NOTE]
      >
      >このタイプのリンクは、ランディングページでのみ使用できます。

1. 受信者に表示されるテキストを変更できます。
1. ユーザーがリンクをクリックしたときのブラウザーの動作を設定できます（例えば、新しいウィンドウを開く）。

   >[!NOTE]
   >
   >ブラウザーの動作の定義は、ランディングページにのみ適用されます。

1. 変更を保存します。

リンクが作成された後も、[設定]ペインで変更できます。 鉛筆アイコンをクリックして、パラメータを編集します。

![](assets/des_link_edit.png)

電子メールデザイナーで電子メールを編集する場合 [](../../designing/using/overview.md)、電子メールに含まれるすべてのURLを一覧表示した表から、作成したリンクに簡単にアクセスして変更できます。 このリストを使用すると、一元的なビューを作成し、電子メールコンテンツ内の各URLを検索できます。 アクセスするには、追跡するURLにつ [いてを参照してください](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>ミラーページURLや購読 **解除リンクなどのパーソナラ** イズされたURLは **** 、このリストから変更できません。 その他のリンクはすべて編集可能です。

**関連トピック**：

* [パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)
* [コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)
* [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 追跡するURLについて {#about-tracked-urls}

Adobe Campaignを使用すると、電子メールに含まれるURLをクリックした受信者の行動を追跡できます。 トラッキングについて詳しくは、この節を [参照してくださ](../../sending/using/tracking-messages.md#about-tracking)い。

アクシ **[!UICONTROL Links]** ョンバーのアイコンには、追跡されるコンテンツのすべてのURLのリストが自動的に表示されます。

![](assets/des_links.png)

>[!NOTE]
>
>トラッキングはデフォルトでアクティブ化されます。 この機能は、Adobe Campaignで追跡がアクティブ化されている場合に、電子メールに対してのみ使用できます。 For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

各リンクのURL、カテゴリ、ラベルおよび追跡タイプは、このリストから変更できます。 リンクを編集するには、対応する鉛筆アイコンをクリックします。

![](assets/des_links_tracking.png)

追跡する各URLに対して、追跡モードを次の値のいずれかに設定できます。

* **追跡**:このURLの追跡をアクティブにします。
* **ミラーページ**：この URL をミラーページの URL とみなします。
* **なし**:は、このURLの追跡をアクティブにしません。 この情報は保存されます。urlが今後のメッセージに再び表示される場合、その追跡は自動的に非アクティブになります。
* **オプトアウト**：この URL をオプトアウトまたは購読解除 URL とみなします。

![](assets/des_link_tracking_type.png)

また、各URLの追跡を非アクティブ化したり、アクティブ化したりすることもできます。

>[!NOTE]
>
>Adobe Campaignのデフォルトでは、ミラーページURLと購読解除リンクを除くすべ **てのコンテンツURL** が追 **跡されます** 。

メッセージで使用されているURLに応じて、フ **[!UICONTROL Category]** ィールドを編集してURLを再グループ化できます。 These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

レポートを作成する際に、タブからリストを **[!UICONTROL Components]** 選択し、下にスク **[!UICONTROL Dimension]** ロールして追跡コンポーネントにアクセスします。 例えば、ワークスペースにドラッグ&amp;ド **[!UICONTROL Tracking URL Category]** ロップして、各クリックされたURLの追跡カテゴリに従って結果を表示します。

![](assets/des_link_tracking_report.png)

カスタマイズされたレポートの作成について詳しくは、この節を [参照してくださ](../../reporting/using/about-dynamic-reports.md)い。
