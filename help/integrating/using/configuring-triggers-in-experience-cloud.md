---
title: Experience Cloud での Triggers の設定
description: Adobe Experience Cloud トリガー統合を設定して、以前の行動に基づいてパーソナライズされた配信を顧客に送信する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# Experience Cloud での Triggers の設定{#configuring-triggers-in-experience-cloud}

## 機能のアクティベート {#activating-the-functionality}

この機能は、AdobeによってAdobe Campaignでアクティベートする必要があります。 Adobe アカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。

Adobe チームは、トリガーをアクティブ化するために次の情報が必要になります。

* Marketing Cloudの会社名
* 組織 ID
* Analytics ログイン会社（Marketing Cloudの会社名と同じ場合があります）

## ソリューションとサービスの設定 {#configuring-solutions-and-services}

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
>サブドメイン設定は、配信品質キー要素です。 Adobe Campaignのメールは、web サイトで使用されるドメインと同じドメインから送信されるようにしてください。

これらのユースケースを実行するには、[Experience Cloud DTM コアサービス ](#configuring-experience-cloud-dtm-core-service)、[Experience Cloud People コアサービス ](#configuring-experience-cloud-people-core-service) および [Campaign](#configuring-triggers-and-aliases-in-campaign) を設定する必要があります。

### Experience Cloud DTM コアサービスの設定 {#configuring-experience-cloud-dtm-core-service}

1. Experience Cloud DTM コアサービス（動的Tag Management）で、web サイトページのExperience Cloud ID とAdobe Analyticsを有効にします。

   ![](assets/trigger_uc_conf_1.png)

1. Web サイト、Adobe Analytics、Adobe Campaign間の ID 紐付けには、エイリアスを使用する必要があります。 「visitorid」などのエイリアスを作成します。

   ![](assets/trigger_uc_conf_2.png)

### Experience Cloud People コアサービスの設定 {#configuring-experience-cloud-people-core-service}

DTM で以前に参照されたエイリアスは、顧客属性を通じてExperience Cloud People コアサービスで作成する必要があります。 新しいエイリアスを作成し、統合コードで同じ DTM エイリアス（例：「visitorid」）を参照してください。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>この顧客属性をAdobe Campaignのデータソースで使用します（次の手順）。

### Campaign でのトリガーとエイリアスの設定 {#configuring-triggers-and-aliases-in-campaign}

1. Adobe Campaign Standard インスタンスに **[!UICONTROL Experience Cloud triggers]** が表示されていることを確認します。 そうでない場合は、Adobe Campaignの管理者にお問い合わせください。

   ![](assets/remarketing_1.png)

1. エイリアスを使用すると、Analytics の連絡先を Campaign のプロファイルと紐付けすることができます。 Experience Cloud ID サービスで定義されたエイリアスと、Campaign の Shared Data Sourceを一致させる必要があります。 データソース（**[!UICONTROL Administration]**/**[!UICONTROL Application Settings]**/**[!UICONTROL Shared Data Sources]**）を介して、Adobe Campaignでエイリアス解決を行う必要があります。 **[!UICONTROL Data Source/Alias]** ドロップダウンメニューで正しいデータソースを選択していることを確認します。このドロップダウンメニューは、前の手順で作成したのと同じ顧客属性データソースにマッピングされています。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >匿名ユーザーとログインしたユーザーの両方に対するトリガーを調整できます。 匿名ユーザーの場合、プロファイルはAdobe Campaignに存在する必要があり、以前にメールが送信されています。 このためには、訪問者 ID を設定するだけで十分です。 ただし、ログインユーザーのトリガーを調整する場合、宣言済み ID データのSourceを設定する必要があります。 詳しくは、[Data Sourceの設定 ](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources) を参照してください。

## Experience Cloud インターフェイスでのトリガーの作成 {#creating-a-trigger-in-the-experience-cloud-interface}

Campaign で使用できるように、Adobe Experience Cloud トリガーを作成する必要があります。

Experience Cloudで新しいトリガーを作成し、web サイトで使用するレポートスイートを選択していることを確認します。 トリガーが発生するように、適切な寸法を選択してください。

[Adobe Experience Cloud ドキュメント ](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=ja) を参照してください。

## トリガーのベストプラクティスと制限事項 {#triggers-best-practices-and-limitations}

以下に、Campaign とトリガーの統合の使用に関するベストプラクティスと制限事項を示します。

* Campaign Standardのインスタンスが複数存在する場合、それらが同じ組織内にある限り、すべてのインスタンスでトリガーを受け取ることができます。 また、Analytics は同じ組織に存在する必要があります。
* 2 つの異なるレポートスイートのトリガーを使用して、トリガーコアサービスでイベントを作成することはできません。
* トリガーは、トランザクションメッセージに基づいています。 トランザクションメッセージは、メッセージをすばやく送信する必要がある場合に常に使用されます。 トランザクションメッセージをキューに入れた後で、バッチでループさせることはできません。
* トリガーは本質的に決定的ではありません。 トリガーが生成されると、その Cookie に関連付けられたすべてのエイリアスが送信されます。そのため、小売店のキオスク、図書館、サイバーカフェ、または自宅の共有デバイス（同じデバイスからの夫婦のログイン）などの共有ブラウザーの場合、適切な ID にマッピングすることはできません。 ブラウザーへのログインに使用されるすべての ID は、Campaign に送信され、最初の紐付けに基づいてメッセージが送信されます。 紐付けの対象となる「電子メール ID」が複数ある場合、Campaign は電子メールを送信しません。 Analytics でキャプチャして送信されない限り、Campaign が適切なメール ID を把握することはできません。
* Campaign にペイロードのコンテンツを保存することはできません。 トリガーを使用してプロファイルのデータを更新することはできません。
* トリガー属性はトリガーではサポートされていません（つまり、顧客のビジネスルールを定義するために使用できるのはレポートスイートデータのみです）。
* コレクションのコレクションは、Campaign ではサポートされていません。

>[!CAUTION]
>
>Web サイトは、Adobe Campaign サーバーと同じドメインで実行されている必要があります。 そうでない場合、訪問者 ID を使用して紐付けを行い、web サイトを匿名で訪問するユーザーに連絡することはできません。
