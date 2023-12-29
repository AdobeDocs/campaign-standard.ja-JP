---
title: メッセージのトラッキング
description: 配信受信者の行動をトラッキングする方法について説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 33%

---

# メッセージのトラッキング{#tracking-messages}

## トラッキングについて {#about-tracking}

Adobe Campaignでは、トラッキング機能を使用して、配信受信者の行動をトラッキングできます。 そのために、Adobe Campaign ではセッション Cookie および永続 Cookie を使用します。

Cookie の使用を許可するチェックボックスが付いた認証リクエスト（例：ページ上で表示される）を介して、サイトに Web トラッキングツールが装備されていることをユーザーに通知したり、最初のページの上部にバナーを追加したりできます。 ポップアップウィンドウはブラウザーでブロックされていることが多いので、避ける必要があります。

トラッキング情報は、データベースの各連絡先に対して、次の項目に対して使用できます。 **[!UICONTROL integrated customer profiles]**. 詳しくは、[この節](../../audiences/using/integrated-customer-profile.md)を参照してください。

Adobe Campaign は、次の 2 つのタイプの Cookie を使用します。

* セッション Cookie (nlid)。 連絡先に送信されるメールの識別子（broadlogId）およびメッセージテンプレートの識別子（deliveryId）が含まれています。Adobe Campaign が送信したメールに含まれている URL を連絡先のユーザーがクリックすると追加され、この連絡先での web 上の行動をトラッキングできるようになります。このセッション Cookie は、ブラウザーが閉じられると自動的に消去されます。連絡先のユーザーは、Cookie を拒否するようにブラウザーを設定できます。
* Adobe Experience Cloudソリューション間で共有される cookie。 これにより、Web サイトの訪問時に Experience Cloud ソリューションとやり取りするユーザーを識別できます。この Cookie の説明については、[こちら](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html)を参照してください。

Adobe Campaign Standardを使用したトラッキングでは、次の機能にアクセスできます。

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="条件" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../administration/using/push-tracking.md"><img width="60px" alt="条件" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="条件" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="条件" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="条件" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>メールトラッキング</td>
<td>プッシュトラッキング</td>
<td>トラッキングする URL</td>
<td>トラッキングログ</td>
<td>トラッキングレポート</td>
</tr>
</table>

## トラッキングログ {#tracking-logs}

The **[!UICONTROL Tracking logs]** 「 」タブには、この配信のトラッキング履歴が一覧表示されます。 このタブには、Adobe Campaignで追跡されているすべての URL など、送信されたメッセージのトラッキング情報が表示されます。 このタブのトラッキング情報は、10 分ごとに更新されます。

>[!NOTE]
>
>配信のトラッキングが有効になっていない場合、このタブは表示されません。 トラッキングログは、 **電子メール** および **プッシュ通知** チャネルのみ。

![](assets/tracking_logs.png)

上記の例では、受信者は次のようになります。

* メッセージを開きました。
* ミラーページのリンクをクリックしました。
* 「LEARN MORE」カスタムリンクをクリックしました。

Adobe Analytics の **[!UICONTROL Type]** 列には、次の値を指定できます。

* **[!UICONTROL Email click]**：受信者がカスタムリンクをクリックしました。
* **[!UICONTROL Mirror page]**：受信者がミラーページへのリンクをクリックしました。
* **[!UICONTROL Open]**：受信者が E メールを開封しました。
* **[!UICONTROL Opt-out]**：受信者が購読解除リンクをクリックしました。

>[!NOTE]
>
>の **プッシュ通知** チャネルに送信された場合、モバイル通知のクリックのみが追跡されます。 その場合、値は **[!UICONTROL Click on mobile notification]**.

トラッキングリンクの挿入方法について詳しくは、 [このページ](../../designing/using/links.md#inserting-a-link).

The **[!UICONTROL Tracking indicators]** レポートには、電子メールメッセージの受信後の行動をトラッキングするための主要指標が含まれます。 詳しくは、この[ページ](../../reporting/using/tracking-indicators.md)を参照してください。

## トラッキングする URL {#tracked-urls}

The **[!UICONTROL Tracked URLs]** 「 」タブは、送信されたメッセージに含まれている URL を、その URL タイプとソース URL を含めて再グループ化します。

![](assets/sending_delivery6.png)

トラッキングリンクについて詳しくは、 [この節](../../designing/using/links.md#about-tracked-urls).
