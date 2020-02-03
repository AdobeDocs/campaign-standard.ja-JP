---
title: Adobe Experience Platformオーディエンスのターゲット設定
description: ワークフロー内でAdobe Experience Platformオーディエンスをターゲット設定する方法について説明します。
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4b18f3b93394101eb569799bcfe362b4daf8f250

---


# Adobe Experience Platformオーディエンスのターゲット設定 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

Unified Profileセグメントビルダーを使用して [Adobe Experience Platformオーディエンスを作成したら](../../audiences/using/aep-about-audience-destinations-service.md) 、ワークフロー内のキャンペーンオーディエンスと同じ方法で、メッセージをパーソナライズして送信できます。

Adobe Experience Platformオーディエンスをワークフローでアクティブ化するには、次の手順に従います。

1. ワークフロー **[!UICONTROL Read audience]**にアクティビティを追加し、開きます。

1. の下のオプション **[!UICONTROL Adobe Experience Platform]**を選択し、**[!UICONTROL Type of audience]**&#x200B;目的のオーディエンスを追加します。

   ![](assets/aep_wkf_readaudience.png)

1. （オプション）オーディエンスを選択したら、目のボタンをクリックして、セグメント定義を確認または編集できます（変更を再度保存してください）。

   目のボタンをクリックすると、キャンペーン内で選択したオーディエンスに関連付けられた（別のタブの）統合セグメントビルダーに移動します。

1. 要素を選択し **[!UICONTROL Platform data mapping]**て、選択したAdobe Experience Platformオーディエンスに対して目的のターゲットディメンションを指定します。

   デフォルトでは、調整に使用される主キー（プロファイルテーブルのiRecipientID、AppSubscriptionテーブルのiAppSubscriptionIDなど）は、ドロップダウンリストから自動的に使用できます。 主キー以外のターゲットを設定するには、カスタム名前空間を作成する必要があ **ります**。

   >[!NOTE]
   >
   >主キー以外のターゲットの場合は、カスタム名前空間に対応するカスタムターゲットマッピングも作成する必要があります。 For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   このリストには、インスタンスに設定されたすべてのエクスペリエンスデータモデル(XDM)マッピングが含まれます。 Adobe Experience Platform Data Connectorについて詳しくは、この専用ドキュメントを [参照してください](../../administration/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. オーディエンスとターゲットディメンションが正しく設定されたら、ボタンをク **[!UICONTROL Confirm]**リックして変更を保存します。

これで、他のアクティビティを使用してワークフローを設定できます。 例えば、選択したオーディエンスに電子メ **[!UICONTROL Email delivery]**ールを送信するために、アクティビティにリンクを設定できます。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standardを使用すると、すべての配信チャネル内でAdobe Experience Platformオーディエンスをターゲットに設定できます。電子メール、SMSメッセージ、ダイレクトメールメッセージ、プッシュ通知、アプリ内メッセージ。
>
>*注意：すべてのプッシュメッセージおよびアプリ内メッセージに対して、Campaign Standardは既知のプロファイルに対する配信のみをサポートします。

ワークフローと配信の使用方法について詳しくは、次の節を参照してください。

* [ワークフローの検索](../../automating/using/discovering-workflows.md)
* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [通信チャネルの検出](../../channels/using/discovering-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
