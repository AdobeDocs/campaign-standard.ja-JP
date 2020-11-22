---
solution: Campaign Standard
product: campaign
title: メッセージのトラッキング
description: 配信受信者の動作を追跡する方法を説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 35%

---


# メッセージのトラッキング{#tracking-messages}

## 追跡について {#about-tracking}

Adobe Campaignでは、トラッキング機能のおかげで、配信受信者の動作を追跡できます。 そのために、Adobe Campaign ではセッション Cookie および永続 Cookie を使用します。

認証リクエスト（ページ上など）を通じて、サイトにWebトラッキングツールが装備されていることをユーザーに通知し、cookieの使用を許可するチェックボックスを追加したり、最初のページの上部にバナーを追加したりできます。 ポップアップウィンドウはブラウザーでブロックされていることが多いので、避ける必要があります。

追跡情報は、のデータベースの各連絡先に対して使用でき **[!UICONTROL integrated customer profiles]**&#x200B;ます。 詳しくは、[この節](../../audiences/using/integrated-customer-profile.md)を参照してください。

Adobe Campaign は、次の 2 つのタイプの Cookie を使用します。

* セッション Cookie （nlid）：連絡先に送信される E メールの識別子（broadlogId）およびメッセージテンプレートの識別子（deliveryId）が含まれています。Adobe Campaign が送信した E メールに含まれている URL を連絡先のユーザーがクリックすると追加され、この連絡先での web 上の行動をトラッキングできるようになります。このセッション Cookie は、ブラウザーが閉じられると自動的に消去されます。連絡先のユーザーは、Cookie を拒否するようにブラウザーを設定できます。
* Adobe Experience Cloudソリューション間で共有されるcookie。 これにより、Web サイトの訪問時に Experience Cloud ソリューションとやり取りするユーザーを識別できます。この Cookie の説明については、[こちら](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-mc.html)を参照してください。

Adobe Campaign Standardを使用した追跡では、次の機能にアクセスできます。

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="conditions" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="conditions" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="conditions" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="conditions" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="conditions" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>E メールトラッキング</td>
<td>プッシュ追跡</td>
<td>トラッキングされる URL</td>
<td>トラッキングログ</td>
<td>トラッキングレポート</td>
</tr>
</table>

## トラッキングログ {#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. このタブには、Adobe Campaignが追跡しているすべてのURLなど、送信されたメッセージの追跡情報が表示されます。 このタブの追跡情報は、10分ごとに更新されます。

>[!NOTE]
>
>配信の追跡が有効になっていない場合、このタブは表示されません。 トラッキングログは、 **電子メール** / **プッシュ通知** チャネルでのみ使用できます。

![](assets/tracking_logs.png)

上の例では、次の受信者があります。

* メッセージを開きました。
* 「詳細情報」カスタムリンクをクリック。
* 購読解除とミラーページのリンクをクリックしました。

この **[!UICONTROL Type]** 列に指定できる値は次のとおりです。

* **[!UICONTROL Email click]**:受信者がカスタムリンクをクリックした。
* **[!UICONTROL Mirror page]**:受信者がミラーページへのリンクをクリックしました。
* **[!UICONTROL Open]**:受信者が電子メールを開きました。
* **[!UICONTROL Opt-out]**:受信者が購読解除リンクをクリックしました。

>[!NOTE]
>
>プッシュ通知 **チャネルの場合** 、モバイル通知のクリックのみが追跡されます。 この場合、値はになり **[!UICONTROL Click on mobile notification]**&#x200B;ます。

トラッキングリンクの挿入方法について詳しくは、 [このページを参照してください](../../designing/using/links.md#inserting-a-link)。

## トラッキングされる URL {#tracked-urls}

この **[!UICONTROL Tracked URLs]** タブでは、送信されたメッセージに含まれるURL（URLタイプとソースURLなど）を再グループ化します。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
