---
title: SMS メッセージについて
description: Adobe Campaignの SMS チャネルの主な特異性を確認します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 30%

---

# SMS メッセージについて{#about-sms-messages}

Adobe Campaignでは、SMS （ショートメッセージサービス）メッセージを配信できます。

>[!NOTE]
>
>SMS チャネルはアドオンです。 使用許諾契約書を確認してください。

SMS メッセージの場合、テキスト形式のメッセージのみを作成、変更およびパーソナライズできます。SMS メッセージは、送信前にプレビューすることもできます。

SMS メッセージの長さは、GSM エンコーディングの場合は 160 文字、Unicode の場合は 70 文字に制限されます。 ただし、特定の特殊文字がメッセージの長さに影響を与える可能性があります。 詳しくは、「[SMS エンコーディング ](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)」の節を参照してください。

SMS メッセージは、**[!UICONTROL Marketing activities]** メニュー、キャンペーンまたはワークフローで作成できます。[SMS メッセージの作成 ](../../channels/using/creating-an-sms-message.md) を参照してください。

携帯電話に SMS メッセージを配信するには、次が必要です。

* **[!UICONTROL Bulk delivery]**&#x200B;モードで&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;チャネルに設定された&#x200B;**[!UICONTROL Routing]**&#x200B;外部アカウント。詳しくは、[ルーティング](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の節を参照してください。
* この外部アカウントに正しくリンクされている配信テンプレート。

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
* [SMS 設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS レポート](../../reporting/using/sms-report.md)
* [Campaign Standardモバイルガイド](../../channels/using/get-started-communication-channels.md)

## SMS 配信テンプレート {#sms-delivery-template}

Adobe Campaignは、モバイルデバイス用の配信テンプレートを提供します。 このテンプレートは、**[!UICONTROL Mobile (SMS)]** チャネルに使用される外部アカウントに正しくリンクされている必要があります。 これにアクセスして変更するには：

1. 詳細メニューから **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** を選択します。
1. **[!UICONTROL Send via SMS]** テンプレートの上にマウスポインターを置いて、「**要素を複製**」オプションを選択します。
1. 新しいテンプレートを選択します。
1. 「**[!UICONTROL Edit properties]**」ボタンをクリックします。
1. テンプレートプロパティの「**[!UICONTROL Advanced parameters]**」セクションで、SMS の配信に使用する外部アカウントにテンプレートがリンクされていることを確認します。

   ![](assets/sms_template.png)

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
