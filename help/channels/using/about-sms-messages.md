---
solution: Campaign Standard
product: campaign
title: SMS メッセージについて
description: Adobe Campaign内のSMSチャネルの主な特殊性を見つける。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 32%

---


# SMS メッセージについて{#about-sms-messages}

Adobe Campaignを使用すると、SMS (Short Message Service)メッセージを配信できます。

>[!NOTE]
>
>SMSチャネルはアドオンです。 使用許諾契約書を確認してください。

SMS メッセージの場合、テキスト形式のメッセージのみを作成、変更およびパーソナライズできます。SMS メッセージは、送信前にプレビューすることもできます。

SMSメッセージがGSMエンコーディングの場合は160文字に制限され、Unicodeの場合は70文字に制限されます。 ただし、特定の特殊文字を使用すると、メッセージの長さに影響を与える場合があります。 詳しくは、[SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)の節を参照してください。

SMSメッセージは、**[!UICONTROL Marketing activities]**&#x200B;メニュー、キャンペーン、またはワークフローから作成できます。詳しくは、[SMSメッセージの作成](../../channels/using/creating-an-sms-message.md)を参照してください。

SMSメッセージを携帯電話に配信するには、次の手順を実行します。

* **[!UICONTROL Bulk delivery]**&#x200B;モードで&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;チャネルに設定された&#x200B;**[!UICONTROL Routing]**&#x200B;外部アカウント。詳しくは、[ルーティング](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の節を参照してください。
* この外部アカウントに正しくリンクされている配信テンプレート。

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
* [SMS構成](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS レポート](../../reporting/using/sms-report.md)
* [Campaign Standard モバイルガイド](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)

## SMS配信テンプレート{#sms-delivery-template}

Adobe Campaignオファーは、モバイルデバイスの配信テンプレートです。 このテンプレートは、**[!UICONTROL Mobile (SMS)]**&#x200B;チャネルに使用される外部アカウントに正しくリンクされている必要があります。 アクセスして変更するには：

1. 詳細設定メニューから&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;を選択します。
1. **[!UICONTROL Send via SMS]**&#x200B;テンプレートの上にマウスを置き、**重複要素**&#x200B;オプションを選択します。
1. 新しいテンプレートを選択します。
1. 「**[!UICONTROL Edit properties]**」ボタンをクリックします。
1. テンプレートプロパティの&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;セクションで、テンプレートが、SMSの配信に使用する外部アカウントにリンクされていることを確認します。

   ![](assets/sms_template.png)

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
