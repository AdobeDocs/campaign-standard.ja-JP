---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform オーディエンスのターゲティング
description: ワークフロー内でAdobe Experience Platformオーディエンスをターゲットする方法を説明します。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# Adobe Experience Platform オーディエンスのターゲティング {#targeting-aep-audiences}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

セグメントビルダーを使用して [Adobe Experience Platformオーディエンスを作成したら](../../audiences/using/aep-about-audience-destinations-service.md) 、ワークフロー内のキャンペーンオーディエンスと同じ方法でメッセージをパーソナライズし、送信できます。

ワークフローでAdobe Experience Platformオーディエンスをアクティブ化するには、次の手順に従います。

1. ワークフロー追加の **[!UICONTROL Read audience]** アクティビティを開きます。

1. の下の **[!UICONTROL Adobe Experience Platform]** オプションを選択 **[!UICONTROL Type of audience]**&#x200B;し、目的のオーディエンスを追加します。

   ![](assets/aep_wkf_readaudience.png)

1. （オプション）オーディエンスを選択したら、目のボタンをクリックして、セグメント定義を確認または編集できます（変更を再度保存してください）。

   目のボタンをクリックすると、キャンペーン内で選択したオーディエンスに関連付けられたセグメントビルダー（別のタブ）に移動します。

1. 要素を選択し、選択したAdobe Experience Platform **[!UICONTROL Platform data mapping]** オーディエンスに必要なターゲティングディメンションを指定します。

   デフォルトでは、調整に使用される主キー(プロファイルテーブルのiRecipientID、AppSubscriptionテーブルのiAppSubscriptionIDなど)は、ドロップダウンリストから自動的に使用できます。 主キー以外でターゲットするには、カスタム **名前空間を作成する必要があります**。

   >[!NOTE]
   >
   >主キー以外のターゲットの場合は、カスタム名前空間に対応するカスタムターゲットマッピングも作成する必要があります。 For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   このリストには、インスタンスに設定されたすべてのエクスペリエンスデータモデル(XDM)マッピングが含まれています。 Adobe Experience Platformデータコネクタの詳細については、 [この専用ドキュメントを参照してください](../../developing/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. オーディエンスとターゲティングディメンションが正しく設定されたら、ボタンをクリックして変更を保存し **[!UICONTROL Confirm]** ます。

これで、他のアクティビティとワークフローを設定できます。 例えば、選択したオーディエンスに電子メールを送信する **[!UICONTROL Email delivery]** アクティビティをリンクできます。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standardを使用すると、すべての配信チャネル内でAdobe Experience Platformオーディエンスをターゲットできます。電子メール、SMSメッセージ、ダイレクトメールメッセージ、プッシュ通知、アプリ内メッセージ。
>
>*注意：すべてのプッシュメッセージおよびアプリ内メッセージに対して、Campaign Standardは既知のプロファイルに対する配信のみをサポートします。

ワークフローと配信の使用方法について詳しくは、次の節を参照してください。

* [ワークフローの検出](../../automating/using/get-started-workflows.md)
* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
