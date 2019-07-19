---
title: メッセージの追跡
seo-title: メッセージの追跡
description: メッセージの追跡
seo-description: 配信の受信者の行動を追跡する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: c3721647-0663-4614- a9c9-3b3a40af328a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 送信および追跡メッセージ
discoiquuid: 6fa50f0d-3dcf-4a9e- bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Tracking messages{#tracking-messages}

## About tracking {#about-tracking}

追跡機能により、Adobe Campaignでは配信の受信者の行動を追跡できます。これを行うには、Adobe Campaignはセッションcookieと永続的cookieを使用します。

ユーザーに、cookieの使用を許可する（ページ上に表示される）認証要求を使用して、サイトにWebトラッキングツールが装備されていることをユーザーに通知したり、ランディングユーザーがランディングした最初のページの先頭にバナーを追加したりできます。ポップアップウィンドウは、ブラウザーによってブロックされる頻度が高いため、回避する必要があります。

Adobe Campaignでは、次の2種類のCookieを使用します。

* セッションcookie（nbid）。これには、連絡先（BroadlogID）に送信される電子メールの識別子と、メッセージテンプレート（DeliveryID）の識別子が含まれます。これは、連絡先がAdobe Campaignから送信された電子メールに含まれるURLをクリックしたときに追加され、Web上での行動を追跡できます。ブラウザーを閉じると、このセッションcookieは自動的に削除されます。連絡先は、cookieを拒否するようにブラウザーを設定できます。
* Adobe Experience Cloudソリューション間で共有されるcookie。これにより、Experience Cloudソリューションを訪問したユーザーをWebサイトに訪問したときに特定できます。The description of this cookie is available here: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracking logs {#tracking-logs}

**[!UICONTROL Tracking logs]** このタブには、この配信のトラッキング履歴が一覧表示されます。このタブには、Adobe Campaignによって追跡されているすべてのURLなど、送信されたメッセージの追跡情報が表示されます。このタブのトラッキング情報は、10分ごとに更新されます。

>[!NOTE]
>
>配信が有効になっていない場合、このタブは表示されません。Tracking logs are available for the **email** and **push notification** channels only.

![](assets/tracking_logs.png)

上記の例では、受信者:

* メッセージを開きました。
* "LEARN MORE"カスタムリンクをクリックしました。
* 購読解除およびミラーページリンクをクリックしました。

**[!UICONTROL Type]** 列の値は次のとおりです。

* **[!UICONTROL Email click]**:受信者がカスタムリンクをクリックしました。
* **[!UICONTROL Mirror page]**:受信者がミラーページへのリンクをクリックしました。
* **[!UICONTROL Open]**:受信者が電子メールを開きました。
* **[!UICONTROL Opt-out]**:受信者が購読解除リンクをクリックしました。

>[!NOTE]
>
>**プッシュ通知** チャネルの場合、モバイル通知のクリックのみが追跡されます。In that case, the value will be **[!UICONTROL Click on mobile notification]**.

For more on how to insert tracking links, refer to [this page](../../designing/using/inserting-a-link.md).

## Tracked URLs {#tracked-urls}

**[!UICONTROL Tracked URLs]** タブでは、送信されたメッセージに含まれるURL（URLタイプやそのソースURLなど）が再グループ化されます。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/about-tracked-urls.md).
