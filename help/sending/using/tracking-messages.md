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

Adobe Campaignのトラッキング機能では、配信の受信者の行動をトラッキングできます。 そのために、Adobe Campaign ではセッション Cookie および永続 Cookie を使用します。

サイトに承認リクエスト（ページ上に表示されるなど）を通じて、Cookie の使用を許可するチェックボックスを備えた web トラッキングツールが搭載されていることをユーザーに通知したり、サイトが最初に表示されるページの上部にバナーを追加したりできます。 ポップアップウィンドウはブラウザーでブロックされていることが多いので、避ける必要があります。

トラッキング情報は、**[!UICONTROL integrated customer profiles]** へのデータベースの各連絡先で使用できます。 詳しくは、[この節](../../audiences/using/integrated-customer-profile.md)を参照してください。

Adobe Campaign は、次の 2 つのタイプの Cookie を使用します。

* セッション cookie （nlid）。 連絡先に送信されるメールの識別子（broadlogId）およびメッセージテンプレートの識別子（deliveryId）が含まれています。Adobe Campaign が送信したメールに含まれている URL を連絡先のユーザーがクリックすると追加され、この連絡先での web 上の行動をトラッキングできるようになります。このセッション Cookie は、ブラウザーが閉じられると自動的に消去されます。連絡先のユーザーは、Cookie を拒否するようにブラウザーを設定できます。
* Adobe Experience Cloud ソリューション間で共有される cookie。 これにより、Web サイトの訪問時に Experience Cloud ソリューションとやり取りするユーザーを識別できます。この Cookie の説明については、[こちら](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html)を参照してください。

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

「**[!UICONTROL Tracking logs]**」タブには、この配信のトラッキング履歴が一覧表示されます。 このタブには、Adobe Campaignでトラッキングされたすべての URL など、送信済みメッセージのトラッキング情報が表示されます。 このタブのトラッキング情報は 10 分ごとに更新されます。

>[!NOTE]
>
>配信トラッキングが有効になっていない場合、このタブは表示されません。 トラッキングログは、**電子メール** および **プッシュ通知** チャネルでのみ使用できます。

![](assets/tracking_logs.png)

上記の例では、受信者は次のようになります。

* メッセージを開きました。
* ミラーページのリンクをクリックしました。
* 「詳細情報」カスタムリンクをクリックしました。

**[!UICONTROL Type]** 列に表示できる値は次のとおりです。

* **[!UICONTROL Email click]**：受信者がカスタムリンクをクリックした。
* **[!UICONTROL Mirror page]**：受信者がミラーページへのリンクをクリックした。
* **[!UICONTROL Open]**：受信者がメールを開封しました。
* **[!UICONTROL Opt-out]**：受信者が購読解除リンクをクリックした。

>[!NOTE]
>
>**プッシュ通知** チャネルの場合、モバイル通知のクリックのみがトラッキングされます。 この場合、値は **[!UICONTROL Click on mobile notification]** になります。

トラッキングリンクの挿入方法について詳しくは、[ このページ ](../../designing/using/links.md#inserting-a-link) を参照してください。

**[!UICONTROL Tracking indicators]** レポートには、メールメッセージを受信した後の行動をトラッキングする主要な指標が含まれています。 詳しくは、この[ページ](../../reporting/using/tracking-indicators.md)を参照してください。

## トラッキングする URL {#tracked-urls}

「**[!UICONTROL Tracked URLs]**」タブは、送信されたメッセージに含まれている URL を、その URL タイプとソース URL を含めて再グループ化します。

![](assets/sending_delivery6.png)

トラッキングリンクについて詳しくは、[ この節 ](../../designing/using/links.md#about-tracked-urls) を参照してください。
