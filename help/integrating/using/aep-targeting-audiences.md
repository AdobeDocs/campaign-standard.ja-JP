---
title: Adobe Experience Platform オーディエンスのターゲティング
description: ワークフロー内でAdobe Experience Platform オーディエンスをターゲットにする方法を説明します。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 3%

---

# Adobe Experience Platform オーディエンスのターゲティング {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Audience Destinations サービスは現在ベータ版です。予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様を Azure でホストする必要があります（現在は北米向けのベータ版のみ）。 へのアクセスを希望する場合は、Adobe カスタマーケアにお問い合わせください。

セグメントビルダーを使用して [Adobe Experience Platform オーディエンスを作成すると &#x200B;](../../integrating/using/aep-about-audience-destinations-service.md) ワークフロー内のキャンペーンオーディエンスと同じように使用して、メッセージをパーソナライズして送信できます。

ワークフローでAdobe Experience Platform オーディエンスをアクティブ化するには、次の手順に従います。

1. **[!UICONTROL Read audience]** アクティビティをワークフローに追加してから開きます。

1. **[!UICONTROL Adobe Experience Platform]** の下の「**[!UICONTROL Type of audience]**」オプションを選択し、目的のオーディエンスを追加します。

   ![](assets/aep_wkf_readaudience.png)

1. （任意）オーディエンスを選択したら、「目」ボタンをクリックして、セグメント定義を確認や編集できます（必ず変更内容を再度保存します）。

   目のボタンをクリックすると、Campaign 内の選択したオーディエンスに関連付けられた（別のタブの）セグメントビルダーに移動します。

1. **[!UICONTROL Platform data mapping]** 要素を選択し、選択したAdobe Experience Platform オーディエンスに対して目的のターゲティングディメンションを指定します。

   デフォルトでは、紐付けに使用するプライマリキー（プロファイルテーブルの iRecipientID、AppSubscription テーブルの iAppSubscriptionID など）は、ドロップダウンリストから自動的に使用できます。 プライマリキーの外部をターゲットにするには、カスタム **名前空間** を作成する必要があります。

   >[!NOTE]
   >
   >プライマリキー以外のターゲットの場合は、カスタム名前空間に対応するカスタムターゲットマッピングも作成する必要があります。 ターゲットマッピングについて詳しくは、[&#x200B; この節 &#x200B;](../../administration/using/target-mappings-in-campaign.md) を参照してください。

   ![](assets/aep_wkf_readaudience_namespace.png)

   このリストには、インスタンスで設定されたすべてのエクスペリエンスデータモデル（XDM）マッピングが含まれています。 Adobe Experience Platform Data Connector について詳しくは、[&#x200B; この専用ドキュメント &#x200B;](../../integrating/using/aep-about-data-connector.md) を参照してください。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. オーディエンスとターゲティングディメンションを正しく設定したら、「**[!UICONTROL Confirm]**」ボタンをクリックして変更を保存します。

これで、他のアクティビティでワークフローを設定できるようになりました。 例えば、**[!UICONTROL Email delivery]** アクティビティをリンクして、選択したオーディエンスにメールを送信できます。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standardを使用すると、メール、SMS メッセージ、ダイレクトメールメッセージ、プッシュ通知、アプリ内メッセージなどのすべての配信チャネル内で、Adobe Experience Platform オーディエンスをターゲットに設定できます。
>
>*メモ：すべてのプッシュメッセージおよびアプリ内メッセージで、Campaign Standardは、既知のプロファイルのみの配信をサポートします。

ワークフローと配信の使用方法について詳しくは、次の節を参照してください。

* [ワークフローの検出](../../automating/using/get-started-workflows.md)
* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [通信チャネルの検出](../../channels/using/get-started-communication-channels.md)
* [チャネルアクティビティについて](../../automating/using/about-channel-activities.md)
