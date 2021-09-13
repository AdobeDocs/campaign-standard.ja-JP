---
title: Adobe Experience Platform オーディエンスのターゲティング
description: ワークフロー内でAdobe Experience Platformオーディエンスをターゲット設定する方法について説明します。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---

# Adobe Experience Platform オーディエンスのターゲティング {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

セグメントビルダーを使用して[Adobe Experience Platformオーディエンス](../../integrating/using/aep-about-audience-destinations-service.md)を作成したら、ワークフロー内のCampaignオーディエンスがメッセージをパーソナライズおよび送信する場合と同じ方法で使用できます。

ワークフローでAdobe Experience Platformオーディエンスをアクティブ化するには、次の手順に従います。

1. ワークフローに&#x200B;**[!UICONTROL Read audience]**&#x200B;アクティビティを追加し、開きます。

1. **[!UICONTROL Type of audience]**&#x200B;の下の&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;オプションを選択し、目的のオーディエンスを追加します。

   ![](assets/aep_wkf_readaudience.png)

1. （オプション）オーディエンスが選択されたら、目のボタンをクリックして、セグメント定義を確認または編集できます（変更を再度保存してください）。

   目のボタンをクリックすると、Campaign内の選択したオーディエンスに関連付けられた（別のタブにある）セグメントビルダーに移動できます。

1. **[!UICONTROL Platform data mapping]**&#x200B;要素を選択し、選択したAdobe Experience Platformオーディエンスの目的のターゲティングディメンションを指定します。

   デフォルトでは、紐付けに使用されるプライマリキー（プロファイルテーブルのiRecipientID、AppSubscriptionテーブルのiAppSubscriptionIDなど）は、ドロップダウンリストから自動的に使用可能になります。 プライマリキー外でターゲットを設定するには、カスタムの&#x200B;**名前空間**&#x200B;を作成する必要があります。

   >[!NOTE]
   >
   >プライマリキー以外のターゲットの場合は、カスタム名前空間に対応するカスタムターゲットマッピングも作成する必要があります。 ターゲットマッピングの詳細については、[この節](../../administration/using/target-mappings-in-campaign.md)を参照してください。

   ![](assets/aep_wkf_readaudience_namespace.png)

   このリストには、インスタンスで設定されたすべてのエクスペリエンスデータモデル(XDM)マッピングが含まれます。 Adobe Experience Platform Data Connectorについて詳しくは、この専用ドキュメント](../../integrating/using/aep-about-data-connector.md)を参照してください。[

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. オーディエンスとターゲティングディメンションが正しく設定されたら、「**[!UICONTROL Confirm]**」ボタンをクリックして変更を保存します。

これで、他のアクティビティを使用してワークフローを設定できます。 例えば、**[!UICONTROL Email delivery]**&#x200B;アクティビティをリンクして、選択したオーディエンスにEメールを送信できます。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standardを使用すると、すべての配信チャネル内でAdobe Experience Platformオーディエンスをターゲット設定できます。Eメール、SMSメッセージ、ダイレクトメールメッセージ、プッシュ通知およびアプリ内メッセージ。
>
>*注意：すべてのプッシュメッセージおよびアプリ内メッセージで、Campaign Standardは既知のプロファイルの配信のみをサポートします。

ワークフローと配信の使用方法について詳しくは、次の節を参照してください。

* [ワークフローの検出](../../automating/using/get-started-workflows.md)
* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
