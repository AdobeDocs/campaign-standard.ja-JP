---
title: Experience Cloud でのトリガーの設定
description: '以前の行動に基づいて、パーソナライズされた配信を顧客に送信する、開始へのAdobe Experience Cloudトリガー統合の設定方法を説明します。 '
page-status-flag: never-activated
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---


# Experience Cloud でのトリガーの設定{#configuring-triggers-in-experience-cloud}

## 機能のアクティブ化 {#activating-the-functionality}

この機能は、AdobeによるAdobe Campaignでアクティブ化する必要があります。 Adobeのアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Adobeチームは、トリガーをアクティブ化するために次の情報が必要です。

* Marketing Cloud会社名
* IMS 組織 ID
* Analyticsログイン会社(Marketing Cloud会社名と同じにすることができます)

## ソリューションおよびサービスの設定 {#configuring-solutions-and-services}

この機能を使用するには、次のソリューション/コアサービスにアクセスできる必要があります。

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select、または Standard。
* Experience Cloud Triggers コアサービス

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM コアサービス

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud 訪問者 ID と Experience Cloud People コアサービス

   ![](assets/trigger_uc_prereq_3.png)

また、稼働中の Web サイトも必要です。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>サブドメインの委任は、配信品質の主要要素です。 Adobe Campaignの電子メールは、Webサイトで使用されているドメインと同じドメインから送信される必要があります。

これらの使用例を実行するには、 [Experience CloudDTMコアサービス](#configuring-experience-cloud-dtm-core-service)、 [Experience Cloudユーザーコアサービス](#configuring-experience-cloud-people-core-service) 、 [](#configuring-triggers-and-aliases-in-campaign) キャンペーンを設定する必要があります。

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. Experience CloudDTMコアサービス(Dynamic Tag Management)で、WebサイトページのExperience CloudIDとAdobe Analyticsをアクティブにします。

   ![](assets/trigger_uc_conf_1.png)

1. Webサイト、Adobe Analytics、Adobe Campaign間のIDの調整には、エイリアシングを使用する必要があります。 例えば、エイリアス「visitorid」を作成します。

   ![](assets/trigger_uc_conf_2.png)

### Experience CloudPeopleコアサービスの設定 {#configuring-experience-cloud-people-core-service}

DTMで以前参照したエイリアスは、Customer Attributeを使用してExperience CloudPeopleコアサービスで作成する必要があります。 新しいエイリアスを作成し、統合コードで同じDTMエイリアス（例：「visitorid」）を参照していることを確認します。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Adobe Campaignのデータソースでこの顧客属性を使用します（次の手順）。

### キャンペーンでのトリガーとエイリアスの設定 {#configuring-triggers-and-aliases-in-campaign}

1. Adobe Campaign Standardインスタンスが **[!UICONTROL Experience Cloud triggers]** 表示されていることを確認します。 削除しなかった場合は、Adobe Campaign管理者に問い合わせてください。

   ![](assets/remarketing_1.png)

1. エイリアスを使用すると、Analyticsの連絡先をキャンペーン内のプロファイルと調整できます。 Experience CloudIDサービスで定義されたエイリアスとキャンペーンの共有データソースを一致させる必要があります。 データソース( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** )を使用して、Adobe Campaignでエイリアス解決を設定する必要があります。 ドロップダウンメニューで正しいデータソースを選択してください。このデータソースは、前の手順で作成したのと同じ顧客属性データソースにマップされています。 **[!UICONTROL Data Source/Alias]**

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >匿名ユーザーとログインユーザーの両方のトリガーを調整できます。 匿名ユーザーの場合、プロファイルはAdobe Campaign内に存在する必要があり、以前に電子メールがユーザーに送信されています。 この場合、訪問者IDの設定で十分です。 ただし、ログインしたユーザーのトリガーを調整する場合は、宣言済みIDデータソースを設定する必要があります。 For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Experience Cloudインターフェイスでのトリガーの作成 {#creating-a-trigger-in-the-experience-cloud-interface}

キャンペーンで使用できるように、Adobe Experience Cloudトリガーを作成する必要があります。

Experience Cloudで新しいトリガーを作成し、Webサイトで使用するレポートスイートを必ず選択してください。 トリガーが起動するように、適切なディメンションを選択してください。

[Adobe Experience Cloudのドキュメントを参照し](https://docs.adobe.com/content/help/ja-JP/core-services/interface/activation/triggers.html) 、この [ビデオをご覧ください](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)。

## ベストプラクティスと制限をトリガー {#triggers-best-practices-and-limitations}

次に、キャンペーンの使用に関するベストプラクティスと制限のリストを示します。Triggers統合：

* Campaign Standardの複数のインスタンスがある場合、トリガーは、同じIMS組織IDにある限り、すべてのインスタンスで受け取ることができます。 また、Analyticsは同じIMS組織IDにある必要があります。
* 2つの異なるレポートスイートのイベントを使用して、コアサービスのトリガーを作成することはできません。
* トリガーはトランザクションメッセージに基づいています。 トランザクションメッセージは、非常に早くメッセージを送信する必要がある場合に使用されます。 トランザクションメッセージをキューに入れてからバッチでループすることはできません。
* トリガーは本質上決定的ではありません。 トリガーを生成すると、cookieに関連付けられたすべてのエイリアスが送信されるので、家庭の小売店のキオスク、ライブラリ、サイバーカフェ、共有デバイス（夫婦が同じデバイスからログインする）などの共有ブラウザーの場合は、適切なIDにマッピングできません。 ブラウザとのログインに使用されるすべてのIDは、最初の調整に基づいてメッセージを送信するキャンペーンに送信されます。 調整の対象となる「電子メールID」が複数存在する場合、キャンペーンは電子メールを送信しません。 Analyticsで取り込まれて送信されない限り、正しい電子メールIDが何かをキャンペーンが知ることはできません。
* ペイロードの内容をキャンペーンに格納することはできません。 トリガーを使用してプロファイルのデータを更新することはできません。
* 顧客属性はTriggersではサポートされていません（つまり、Triggersビジネスルールを定義する際に使用できるのはレポートスイートデータのみです）。
* コレクションのキャンペーンは、コレクションではサポートされていません。

>[!CAUTION]
>
>WebサイトがAdobe Campaignサーバーと同じドメインで実行されている必要があります。 一致しない場合、訪問者IDを使用して調整を行い、Webサイトを匿名で訪問するユーザーにリーチアウトすることはできません。

