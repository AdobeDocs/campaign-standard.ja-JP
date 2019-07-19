---
title: Experience Cloudでのトリガーの設定
seo-title: Experience Cloudでのトリガーの設定
description: Experience Cloudでのトリガーの設定
seo-description: 'Adobe Experience Cloudの統合を設定して、以前の動作に基づいてパーソナライズされた配信を顧客に送信する方法について説明します。 '
page-status-flag: 常にアクティブ化されていない
uuid: 8fd7b804-9528-46a5- a060- bf16b8dc555d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- trigger
discoiquuid: 4163dc0c-8103-4425- b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activating the functionality {#activating-the-functionality}

機能はAdobe CampaignでAdobeによってアクティベートされる必要があります。アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。

トリガーをアクティブにするには、アドビチームには次の情報が必要です。

* Marketing Cloud会社名
* IMS ORG ID
* Analyticsログイン会社名（Marketing Cloud会社名と同じにすることができます）

## Configuring solutions and services {#configuring-solutions-and-services}

この機能を使用するには、次のソリューション/コアサービスにアクセスする必要があります。

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、モバイルApps、Select、Standard。
* Experience Cloud Triggersコアサービス

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTMコアサービス

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud訪問者IDおよびExperience Cloud Peopleコアサービス

   ![](assets/trigger_uc_prereq_3.png)

また、作業中のWebサイトも必要です。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>サブドメインの委任は、配信品質のキー要素です。Adobe Campaignの電子メールが、Webサイトで使用されているものと同じドメインから送信されていることを確認してください。

You need to configure [Experience Cloud DTM Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-people-core-service) and [Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-triggers-and-aliases-in-campaign) to run these use cases.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. Experience Cloud DTMコアサービス（Dynamic Tag Management）で、Webサイトのページに対してExperience Cloud IDとAdobe Analyticsをアクティブにします。

   ![](assets/trigger_uc_conf_1.png)

1. Webサイト間のIDの紐付け、Adobe AnalyticsおよびAdobe Campaignでは、エイリアシングを使用する必要があります。例えば、エイリアス"visitorid"を作成します。

   ![](assets/trigger_uc_conf_2.png)

### Configuring Experience Cloud People Core Service {#configuring-experience-cloud-people-core-service}

以前にDTMで参照していたエイリアスは、顧客属性を通じてExperience Cloud Peopleコアサービスで作成する必要があります。新しいコードを作成し、統合コードで同じDTMエイリアスを参照してください（例:"visitorid"）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Adobe Campaignのデータソースでこの顧客属性を使用します（次の手順）。

### Configuring triggers and aliases in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Make sure you have **[!UICONTROL Experience Cloud triggers]** visible on your Adobe Campaign Standard instance. 使用しない場合は、Adobe Campaign管理者に問い合わせてください。

   ![](assets/remarketing_1.png)

1. エイリアスを使用すると、Analyticsの連絡先をキャンペーンのプロファイルと調整できます。Experience Cloud IDサービスで定義されているエイリアスと、Campaignの共有データソースを一致させる必要があります。You need to configure the aliases resolution in Adobe Campaign via a Data source ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). **[!UICONTROL Data Source/Alias]** ドロップダウンメニューで正しいデータソースを選択してください。これは、前の手順で作成したものと同じ顧客属性データソースにマップされていることを確認してください。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >匿名ユーザーとログインユーザーの両方に対してトリガーを調整できます。匿名ユーザーの場合、プロファイルはAdobe Campaignに存在し、ユーザーに電子メールが送信されています。このため、訪問者IDの設定は十分です。ただし、ログインユーザーのトリガーを調整する場合は、宣言済みIDデータソースを設定する必要があります。For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creating a trigger in the Experience Cloud interface {#creating-a-trigger-in-the-experience-cloud-interface}

キャンペーンで使用できるように、Adobe Experience Cloudトリガーを作成する必要があります。

Experience Cloudで新しいトリガーを作成し、Webサイトで使用するレポートスイートを選択していることを確認します。トリガーが起動するように適切なディメンションを選択してください。

[Adobe Experience Cloudドキュメント](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) を参照して [、このビデオをご覧](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)ください。

## Triggers best practices and limitations {#triggers-best-practices-and-limitations}

以下に、キャンペーンの使用に関するベストプラクティスと制限事項の一覧を示します。

* キャンペーンStandardの複数のインスタンスがある場合、すべてのインスタンスが同じIMS組織IDにある限り、すべてのインスタンスでトリガーできます。Analyticsも同じIMS組織ID上にある必要があります。
* 2つの異なるレポートスイートのイベントを使用して、トリガーコアサービスでトリガーを作成することはできません。
* トリガーはトランザクションメッセージに基づいています。トランザクションメッセージは、メッセージを非常に迅速に送信する必要がある場合に使用します。トランザクションメッセージをキューに入れてから、バッチでループ再生することはできません。
* トリガーは本質的には判別できません。トリガーが生成されると、cookieに関連付けられたすべてのエイリアスが送信されます。したがって、市販キオスク、ライブラリ、サイバーカフェ、共有デバイスなどの共有ブラウザーの場合は、ホーム（同じデバイスからのログイン）では適切なIDにマップできません。ブラウザーとのログインに使用されるすべてのIDがキャンペーンに送信され、最初の紐付けに基づいてメッセージが送信されます。紐付けに使用できる「電子メールID"が複数存在する場合、キャンペーンは電子メールを送信しません。キャンペーンがキャプチャされ、Analyticsによって送信されない限り、キャンペーンは適切な電子メールIDが何かを知ることはできません。
* キャンペーンでペイロードのコンテンツを保存することはできません。トリガーを使用してプロファイルのデータを更新することはできません。
* 顧客属性は、トリガーではサポートされません（つまり、レポートスイートデータのみを使用して、トリガービジネスルールを定義できます）。
* コレクションのコレクションはキャンペーンではサポートされていません。

>[!CAUTION]
>
>Webサイトは、Adobe Campaignサーバーと同じドメインで実行している必要があります。そうしないと、訪問者IDを使用してWebサイトを匿名で訪問し、匿名でWebサイトを訪問することはできません。

