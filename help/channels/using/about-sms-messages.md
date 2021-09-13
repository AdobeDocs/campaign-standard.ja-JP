---
title: SMS メッセージについて
description: Adobe CampaignのSMSチャネルの主な特性を確認します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 32%

---

# SMS メッセージについて{#about-sms-messages}

Adobe Campaignでは、SMS（ショートメッセージサービス）メッセージを配信できます。

>[!NOTE]
>
>SMSチャネルはアドオンです。 ライセンス契約をご確認ください。

SMS メッセージの場合、テキスト形式のメッセージのみを作成、変更およびパーソナライズできます。SMS メッセージは、送信前にプレビューすることもできます。

SMSメッセージの長さは、GSMエンコーディングの場合は160文字に制限され、Unicodeの場合は70文字に制限されます。 ただし、特定の特殊文字はメッセージの長さに影響を与える可能性があります。 詳しくは、[SMSエンコーディング](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)の節を参照してください。

SMSメッセージは、**[!UICONTROL Marketing activities]**&#x200B;メニュー、キャンペーン、またはワークフローから作成できます。[SMSメッセージの作成](../../channels/using/creating-an-sms-message.md)を参照してください。

携帯電話にSMSメッセージを配信するには、以下が必要です。

* **[!UICONTROL Bulk delivery]**&#x200B;モードで&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;チャネルに設定された&#x200B;**[!UICONTROL Routing]**&#x200B;外部アカウント。詳しくは、[ルーティング](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の節を参照してください。
* この外部アカウントに正しくリンクされている配信テンプレート。

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
* [SMSの設定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS レポート](../../reporting/using/sms-report.md)
* [Campaign Standard モバイルガイド](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)

## SMS配信テンプレート {#sms-delivery-template}

Adobe Campaignは、モバイルデバイス用の配信テンプレートを提供します。 このテンプレートは、**[!UICONTROL Mobile (SMS)]**&#x200B;チャネルに使用する外部アカウントに正しくリンクされている必要があります。 アクセスして変更するには、次の手順に従います。

1. 詳細設定メニューから&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;を選択します。
1. **[!UICONTROL Send via SMS]**&#x200B;テンプレートの上にマウスポインターを置き、「**要素を複製**」オプションを選択します。
1. 新しいテンプレートを選択します。
1. 「**[!UICONTROL Edit properties]**」ボタンをクリックします。
1. テンプレートプロパティの「 **[!UICONTROL Advanced parameters]** 」セクションで、テンプレートがSMSの配信に使用する外部アカウントにリンクされていることを確認します。

   ![](assets/sms_template.png)

**関連トピック：**

* [テンプレートの管理](../../start/using/marketing-activity-templates.md)
