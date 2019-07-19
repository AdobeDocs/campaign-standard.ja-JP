---
title: SMSメッセージについて
seo-title: SMSメッセージについて
description: SMSメッセージについて
seo-description: Adobe CampaignのSMSチャネルの重要性を特定します。
page-status-flag: 常にアクティブ化されていない
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: sms- messages
discoiquuid: 6134fe72-77de-4fd0- b794-4d966epaccf
delivercontext-tags: DeliveryCreation，ウィザード;delivery， ssContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About SMS messages{#about-sms-messages}

Adobe Campaignでは、SMS（Short Message Service）メッセージを配信できます。

>[!NOTE]
>
>SMSチャネルはアドオンです。使用許諾契約書を確認してください。

SMSメッセージの場合は、メッセージの作成、変更およびカスタマイズをテキスト形式でのみ行うことができます。送信前にSMSメッセージをプレビューすることもできます。

SMSメッセージの長さは、GSMエンコーディングに含まれている場合は160文字に制限され、Unicodeの場合は70文字に制限されます。ただし、特定の特殊文字はメッセージの長さに影響を与えることがあります。For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS messages can be created from the **[!UICONTROL Marketing activities]** menu, from a campaign, or in a workflow, see [Creating an SMS message](../../channels/using/creating-an-sms-message.md).

SMSメッセージを必要な携帯電話に配信するには:

* **[!UICONTROL Routing]** モードを使用して **[!UICONTROL Mobile (SMS)]** チャネル上で設定された外部アカウント **[!UICONTROL Bulk delivery]** 。For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* この外部アカウントに正しくリンクされている配信テンプレート。

**関連トピック:**

* [テンプレートの管理](../../start/using/about-templates.md)
* [SMS設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)

## SMS delivery template {#sms-delivery-template}

Adobe Campaignは、モバイルデバイス用の配信テンプレートを提供します。This template must be correctly linked to the external account used for the **[!UICONTROL Mobile (SMS)]** channel. アクセスして変更するには:

1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** from the advanced menu.
1. Hover over the **[!UICONTROL Send via SMS]** template with the mouse and select the **Duplicate element** option.
1. 新しいテンプレートを選択します。
1. Click the **[!UICONTROL Edit properties]** button.
1. In the **[!UICONTROL Advanced parameters]** section of the template properties, make sure that the template is linked to the external account to be used for delivering SMS.

   ![](assets/sms_template.png)

**関連トピック:**

* [テンプレートの管理](../../start/using/about-templates.md)

