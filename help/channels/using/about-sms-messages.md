---
title: SMS メッセージについて
description: Adobe CampaignのSMSチャネルの主な特性を確認します。
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# SMS メッセージについて{#about-sms-messages}

Adobe Campaignでは、SMS(Short Message Service)メッセージを配信できます。

>[!NOTE]
>
>SMSチャネルはアドオンです。 使用許諾契約書を確認してください。

SMS メッセージの場合、テキスト形式のメッセージのみを作成、変更およびパーソナライズできます。SMS メッセージは、送信前にプレビューすることもできます。

SMSメッセージがGSMエンコードの場合は160文字に制限され、Unicodeの場合は70文字に制限されます。 ただし、特定の特殊文字がメッセージの長さに影響を与える可能性があります。 For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMSメッセージは、メニュー、キャンペーン、 **[!UICONTROL Marketing activities]**またはワークフローから作成できます。「SMSメッセージの作成」を[参照してください](../../channels/using/creating-an-sms-message.md)。

携帯電話にSMSメッセージを配信するには、次の手順を実行する必要があります。

* モード **[!UICONTROL Routing]**を使用してチャネルに設定**[!UICONTROL Mobile (SMS)]** された外部アカウ **[!UICONTROL Bulk delivery]**ント。 For more on this, refer to the[Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)section.
* この外部アカウントに正しくリンクされた配信テンプレート。

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
* [SMS設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS レポート](../../reporting/using/sms-report.md)

## SMS配信テンプレート {#sms-delivery-template}

Adobe Campaignには、モバイルデバイス用の配信テンプレートが用意されています。 このテンプレートは、チャネルに使用する外部アカウントに正しくリンクされている必要が **[!UICONTROL Mobile (SMS)]**あります。 アクセスして変更するには：

1. アドバンス **[!UICONTROL Resources]**メニュー**[!UICONTROL Templates]** から/ **[!UICONTROL Delivery templates]**/を選択します。
1. マウスでテンプレート **[!UICONTROL Send via SMS]**の上にカーソルを置き、「要素を複製」オ**&#x200B;プションを選択し&#x200B;**ます。
1. 新しいテンプレートを選択します。
1. ボタンをクリッ **[!UICONTROL Edit properties]**クします。
1. テンプレートプ **[!UICONTROL Advanced parameters]**ロパティのセクションで、テンプレートが、SMSの配信に使用する外部アカウントにリンクされていることを確認します。

   ![](assets/sms_template.png)

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
