---
title: Experience Cloud での Triggers の設定
description: 以前の行動に基づいてパーソナライズされた配信を顧客に送信するようにAdobe Experience Cloud Triggers統合を設定する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: cf2ded703e53d6db27e62712734f7ea846da9a21
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# Experience Cloud での Triggers の設定{#configuring-triggers-in-experience-cloud}

## 機能の有効化 {#activating-the-functionality}

機能は、AdobeによってAdobe Campaignでアクティブ化する必要があります。 担当のAdobeアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Adobeチームがトリガーをアクティブ化するには、次の情報が必要です。

* Marketing Cloud会社名
* 組織 ID
* Analytics ログイン会社名 (Marketing Cloud会社名と同じ )

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
>サブドメイン設定は、配信品質の重要な要素です。 Adobe Campaign E メールは、Web サイトで使用されるドメインと同じドメインから送信されることを確認します。

次の設定が必要です： [Experience CloudDTM コアサービス](#configuring-experience-cloud-dtm-core-service), [Experience CloudPeople コアサービス](#configuring-experience-cloud-people-core-service) および [Campaign](#configuring-triggers-and-aliases-in-campaign) を参照してください。

### Experience CloudDTM コアサービスの設定 {#configuring-experience-cloud-dtm-core-service}

1. Experience CloudDTM コアサービス (Dynamic Tag Management) で、Web サイトページのExperience CloudID とAdobe Analyticsをアクティベートします。

   ![](assets/trigger_uc_conf_1.png)

1. Web サイト、Adobe Analytics、Adobe Campaign間の ID の紐付けでは、エイリアスを使用する必要があります。 エイリアス（例：「visitorid」）を作成します。

   ![](assets/trigger_uc_conf_2.png)

### Experience CloudPeople コアサービスの設定 {#configuring-experience-cloud-people-core-service}

DTM で以前に参照されたエイリアスは、顧客属性を通じてExperience CloudPeople コアサービスで作成する必要があります。 新しいエイリアスを作成し、統合コードで同じ DTM エイリアスを参照していることを確認してください（例：「visitorid」）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>この顧客属性をAdobe Campaignのデータソースで使用します（次の手順）。

### Campaign でのトリガーとエイリアスの設定 {#configuring-triggers-and-aliases-in-campaign}

1. 次の条件を満たしていることを確認します。 **[!UICONTROL Experience Cloud triggers]** Adobe Campaign Standardインスタンスで表示できます。 表示されない場合は、Adobe Campaign管理者にお問い合わせください。

   ![](assets/remarketing_1.png)

1. エイリアスを使用すると、Analytics の連絡先を Campaign のプロファイルと紐付けできます。 Experience CloudID サービスで定義されたエイリアスを Campaign の共有データソースと照合する必要があります。 データソース ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ) をクリックします。 正しいデータソースが **[!UICONTROL Data Source/Alias]** ドロップダウンメニュー（前の手順で作成したのと同じ顧客属性データソースにマッピングされます）。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >匿名ユーザーとログイントリガーの両方について、ユーザーを紐付けできます。 匿名ユーザーの場合、プロファイルはAdobe Campaignに存在し、以前に電子メールがユーザーに送信されているはずです。 そのためには、訪問者 ID の設定で十分です。 ただし、ログインしたユーザーのトリガーを紐付けする場合は、宣言済み ID データソースを設定する必要があります。 詳しくは、 [データソースの設定](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Experience Cloudインターフェイスでのトリガーの作成 {#creating-a-trigger-in-the-experience-cloud-interface}

Adobe Experience Cloudトリガーを Campaign で使用できるようにするには、レポートを作成する必要があります。

「 」Experience Cloudで新しいトリガーを作成し、Web サイトで使用するレポートスイートを必ず選択してください。 トリガーが実行されるように、適切なディメンションを選択していることを確認します。

詳しくは、 [Adobe Experience Cloudドキュメント](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=ja).

## トリガーのベストプラクティスと制限事項 {#triggers-best-practices-and-limitations}

以下に、Campaign とトリガーの統合の使用に関するベストプラクティスと制限事項のリストを示します。

* Campaign Standardのインスタンスが複数ある場合、同じ組織にある限り、すべてのインスタンスがトリガーを受け取ることができます。 また、Analytics が同じ組織に属している必要があります。
* 2 つの異なるレポートスイートのトリガーを使用して、トリガーコアサービスでイベントを作成することはできません。
* トリガーは、トランザクションメッセージに基づいています。 トランザクションメッセージは、非常に迅速にメッセージを送信する必要がある場合に使用します。 トランザクションメッセージをキューに入れ、バッチでループすることはできません。
* トリガーは、本質上決定的ではありません。 トリガーが生成されると、cookie に関連付けられているすべてのエイリアスが送信されるので、小売キオスク、ライブラリ、サイバーカフェ、自宅の共有デバイス（同じデバイスからログインする夫婦）などのブラウザーでは、適切な ID にマッピングできません。 ブラウザーでのログインに使用されたすべての ID は、最初の紐付けに基づいてメッセージを送信する Campaign に送信されます。 紐付けの対象となる「電子メール ID」が複数ある場合、Campaign は電子メールを送信しません。 Analytics から取り込んで送信されない限り、Campaign が適切な電子メール ID を把握する方法はありません。
* ペイロードのコンテンツを Campaign に保存することはできません。 トリガーを使用してプロファイルのデータを更新することはできません。
* 顧客属性は、トリガーではサポートされません ( つまり、レポートスイートデータのみを使用してトリガーのビジネスルールを定義できます )。
* コレクションのコレクションは、Campaign ではサポートされていません。

>[!CAUTION]
>
>Web サイトは、Adobe Campaignサーバーと同じドメインで実行されている必要があります。 そうでない場合、訪問者 ID を使用して紐付けを行い、Web サイトに匿名で訪問するユーザーに連絡することはできません。
