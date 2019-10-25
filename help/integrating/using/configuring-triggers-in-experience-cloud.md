---
title: Experience cloudでのTriggersの設定
seo-title: Experience cloudでのTriggersの設定
description: Experience cloudでのTriggersの設定
seo-description: 'Adobe Experience Cloud Triggers統合を設定し、以前の行動に基づいてパーソナライズされた配信を顧客に送信する方法を説明します。 '
page-status-flag: 非活性化の
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとトリガーの連携
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Experience cloudでのTriggersの設定{#configuring-triggers-in-experience-cloud}

## 機能のアクティブ化 {#activating-the-functionality}

この機能は、Adobe Campaignでアドビがアクティブ化する必要があります。 アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。

トリガーをアクティブにするには、アドビのチームで次の情報が必要になります。

* Marketing cloud会社名
* IMS ORG ID
* Analyticsログイン会社名（Marketing cloud会社名と同じ名前を使用できます）

## ソリューションとサービスの設定 {#configuring-solutions-and-services}

この機能を使用するには、次のソリューション/コアサービスにアクセスできる必要があります。

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、SelectまたはStandard。
* Experience Cloud Triggersコアサービス

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTMコアサービス

   ![](assets/trigger_uc_prereq_2.png)

* Experience cloud訪問者IDとExperience cloud訪問者コアサービス

   ![](assets/trigger_uc_prereq_3.png)

また、作業中のWebサイトも必要です。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>サブドメイン委任は配信品質キー要素です。 Adobe Campaignの電子メールは、Webサイトで使用されているものと同じドメインから送信される必要があります。

これらの使用例を実行するには、 [Experience Cloud DTMコアサービス](#configuring-experience-cloud-dtm-core-service)、 [Experience Cloud Peopleコアサービス](#configuring-experience-cloud-people-core-service) 、 [](#configuring-triggers-and-aliases-in-campaign) Campaignを設定する必要があります。

### Experience Cloud DTMコアサービスの設定 {#configuring-experience-cloud-dtm-core-service}

1. Experience Cloud DTMコアサービス(Dynamic Tag Management)で、WebサイトページのExperience Cloud IDとAdobe Analyticsをアクティブ化します。

   ![](assets/trigger_uc_conf_1.png)

1. Webサイト間のID調整、Adobe AnalyticsとAdobe Campaignでは、エイリアスを使用する必要があります。 例えば、エイリアス「visitorid」を作成します。

   ![](assets/trigger_uc_conf_2.png)

### Experience cloudPeopleコアサービスの設定 {#configuring-experience-cloud-people-core-service}

DTMで以前参照したエイリアスは、顧客属性を使用してExperience Cloud Peopleコアサービスで作成する必要があります。 新しいエイリアスを作成し、統合コードで同じDTMエイリアス（例：「visitorid」）を参照していることを確認します。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Adobe Campaignのデータソースで、この顧客属性を使用します（次の手順）。

### Campaignでのトリガーとエイリアスの設定 {#configuring-triggers-and-aliases-in-campaign}

1. Adobe Campaign Standardインスタンスに **[!UICONTROL Experience Cloud triggers]** 表示されていることを確認します。 削除しない場合は、Adobe Campaign管理者にお問い合わせください。

   ![](assets/remarketing_1.png)

1. エイリアスを使用すると、Analyticsの連絡先をCampaignのプロファイルと調整できます。 Experience Cloud IDサービスで定義されたエイリアスとCampaignの共有データソースを一致させる必要があります。 Adobe Campaignで、データソース( &gt; &gt; **[!UICONTROL Administration]** )を使用してエイリアスの解決を設定する **[!UICONTROL Application Settings]** 必要があ **[!UICONTROL Shared Data Sources]** ります。 ドロップダウンメニューで正しいデータソースを選択します。このデータソース **[!UICONTROL Data Source/Alias]** は、前の手順で作成したのと同じ顧客属性データソースにマップされています。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >匿名ユーザーとログインユーザーの両方のトリガーを調整できます。 匿名ユーザーの場合、プロファイルはAdobe Campaignに存在し、以前に電子メールがユーザーに送信されている必要があります。 この場合、訪問者IDの設定で十分です。 ただし、ログインしたユーザーのトリガーを調整する場合は、宣言済みIDデータソースを設定する必要があります。 詳しくは、「データソースの設定」を参 [照してください](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)。

## Experience cloudインターフェイスでのトリガーの作成 {#creating-a-trigger-in-the-experience-cloud-interface}

Adobe Experience cloudのトリガーをCampaignで使用できるように作成する必要があります。

Experience cloudで新しいトリガーを作成し、Webサイトで使用するレポートスイートを選択していることを確認します。 トリガーが起動するように、適切なディメンションを選択してください。

Adobe Experience cloudのドキュメント [を参照して](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) 、このビデオをご覧く [ださい](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)。

## ベストプラクティスと制限をトリガー {#triggers-best-practices-and-limitations}

以下に、Campaign - Triggers統合の使用に関するベストプラクティスと制限を示します。

* キャンペーン標準の複数のインスタンスがある場合、トリガーは、同じIMS組織IDにある限り、すべてのインスタンスで受け取ることができます。 また、Analyticsは同じIMS組織ID上にある必要があります。
* 2つの異なるレポートスイートのイベントを使用して、コアサービスのトリガーでトリガーを作成することはできません。
* トリガーは、トランザクションメッセージに基づいています。 メッセージを非常に迅速に送信する必要がある場合は、トランザクションメッセージが使用されます。 トランザクションメッセージをキューに入れてから、バッチでループすることはできません。
* トリガーは本質的には決定的ではありません。 トリガーが生成されると、cookieに関連付けられたすべてのエイリアスが送信されるので、家庭の小売キオスク、ライブラリ、サイバーカフェ、共有デバイス（同じデバイスからログインする夫婦）などの共有ブラウザーの場合は、正しいIDにマッピングできません。 ブラウザーでのログインに使用されるすべてのIDがCampaignに送信され、Campaignは最初の調整に基づいてメッセージを送信します。 調整の資格がある「電子メールID」が複数ある場合、Campaignは電子メールを送信しません。 Analyticsで取得および送信されない限り、Campaignで適切な電子メールIDが何であるかを知る方法はありません。
* ペイロードのコンテンツをCampaignに保存することはできません。 トリガーを使用してプロファイルのデータを更新することはできません。
* 顧客属性はTriggersではサポートされていません（つまり、Triggersビジネスルールを定義するために使用できるのはレポートスイートデータのみです）。
* コレクションのコレクションはCampaignではサポートされていません。

>[!CAUTION]
>
>WebサイトがAdobe Campaignサーバーと同じドメインで実行されている必要があります。 訪問者IDがない場合は、Webサイトを匿名で訪問するユーザーとの調整やリーチアウトに訪問者IDを使用できません。

