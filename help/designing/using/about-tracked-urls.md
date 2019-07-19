---
title: 追跡されているURLについて
seo-title: 追跡されているURLについて
description: 追跡されているURLについて
seo-description: 追跡するコンテンツのすべてのURLを管理する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: dfe5146b-5256-431c-87b3-3c54817aba36
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: 管理リンク
discoiquuid: d9b0b3c2-874b-4cb4- bce9- c0194a19f25f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About tracked URLs{#about-tracked-urls}

Adobe Campaignでは、電子メールに含まれているURLをクリックすると、受信者の行動を追跡できます。For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

The **[!UICONTROL Links]** icon in the action bar automatically displays the list of all the URLs of your content that will be tracked.

![](assets/des_links.png)

>[!NOTE]
>
>追跡はデフォルトで有効になっています。この機能は、Adobe Campaignで追跡が有効になっている場合にのみ電子メールで使用できます。For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

各リンクのURL、カテゴリ、ラベルおよびトラッキングタイプは、このリストから変更できます。リンクを編集するには、対応する鉛筆アイコンをクリックします。

![](assets/des_links_tracking.png)

トラッキングモードごとに、トラッキングモードを次のいずれかの値に設定できます。

* **追跡**:このURLでトラッキングをアクティブにします。
* **ミラーページ**:このURLはミラーページURLであると見なされます。
* **なし**:は、このURLのトラッキングをアクティブにしません。この情報は保存されます。URLが今後のメッセージで再び表示される場合、そのトラッキングは自動的に無効になります。
* **オプトアウト**:このURLは、オプトアウトまたは購読解除URLと見なされます。

![](assets/des_link_tracking_type.png)

また、各URLの追跡を非アクティブ化またはアクティブ化することもできます。

>[!NOTE]
>
>By default in Adobe Campaign, all content URLs are tracked except **Mirror page URL** and **Unsubscription** link.

You can regroup your URLs by editing the **[!UICONTROL Category]** field, depending on the URLs used in the message. These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

When building a report, from the **[!UICONTROL Components]** tab, select **[!UICONTROL Dimension]** and scroll down the list to access the tracking components. For example, drag and drop **[!UICONTROL Tracking URL Category]** into the workspace to display results according to the tracking category of each clicked URL.

![](assets/des_link_tracking_report.png)

For more on building customized reports, see [this section](../../reporting/using/about-dynamic-reports.md).
