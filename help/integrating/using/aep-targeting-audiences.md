---
title: Adobe Experience Platform オーディエンスのターゲティング
description: ワークフロー内でAdobe Experience Platformオーディエンスをターゲットにする方法について説明します。
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
>Audience Destinations サービスは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

以下を作成したら、 [Adobe Experience Platformオーディエンス](../../integrating/using/aep-about-audience-destinations-service.md) セグメントビルダーを使用すると、ワークフロー内の Campaign オーディエンスがメッセージをパーソナライズおよび送信する際と同じ方法で使用できます。

ワークフローでAdobe Experience Platformオーディエンスをアクティブ化するには、次の手順に従います。

1. を追加します。 **[!UICONTROL Read audience]** 「 」アクティビティをワークフローに追加し、開きます。

1. を選択します。 **[!UICONTROL Adobe Experience Platform]** のオプション **[!UICONTROL Type of audience]**&#x200B;次に、目的のオーディエンスを追加します。

   ![](assets/aep_wkf_readaudience.png)

1. （オプション）オーディエンスが選択されたら、目のボタンをクリックして、セグメント定義を確認または編集できます（変更を再度保存してください）。

   目のボタンをクリックすると、Campaign 内の選択したオーディエンスに関連付けられている（別のタブの）セグメントビルダーに移動します。

1. を選択します。 **[!UICONTROL Platform data mapping]** 要素を使用して、選択したAdobe Experience Platformオーディエンスの目的のターゲティングディメンションを指定します。

   デフォルトでは、紐付けに使用されるプライマリキー（例：プロファイルテーブルの iRecipientID、AppSubscription テーブルの iAppSubscriptionID）は、ドロップダウンリストから自動的に使用できます。 プライマリキー以外でターゲット設定するには、カスタムキーを作成する必要があります **名前空間**.

   >[!NOTE]
   >
   >プライマリキー以外のターゲットの場合は、カスタム名前空間に対応するカスタムターゲットマッピングも作成する必要があります。 ターゲットマッピングについて詳しくは、 [この節](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   このリストには、インスタンスで設定されたすべての Experience Data Model(XDM) マッピングが含まれています。 Adobe Experience Platform Data Connector について詳しくは、 [この専用ドキュメント](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. オーディエンスとターゲティングディメンションが正しく設定されたら、 **[!UICONTROL Confirm]** ボタンをクリックして、変更を保存します。

これで、他のアクティビティを使用したワークフローを設定できます。 例えば、 **[!UICONTROL Email delivery]** 「 」アクティビティを選択して、選択したオーディエンスに E メールを送信します。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standardを使用すると、すべての配信チャネル内でAdobe Experience Platformオーディエンスをターゲットに設定できます。E メール、SMS メッセージ、ダイレクトメールメッセージ、プッシュ通知およびアプリ内メッセージ。
>
>*注意：すべてのプッシュメッセージおよびアプリ内メッセージで、Campaign Standardは既知のプロファイルに対する配信のみをサポートします。

ワークフローと配信の使用方法について詳しくは、次の節を参照してください。

* [ワークフローの検出](../../automating/using/get-started-workflows.md)
* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
