---
title: Dynamics 365 セルフサービスアプリを使用したAdobe Campaign Standard統合へのアクセス
description: Adobe Campaign StandardとDynamics 365 セルフサービスアプリの統合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
TQID: 'https://experienceleague.adobe.com/eSWqj-qyCQkrDNHl-7Pc6It5oBFHSBNG3-F0aoNiRYY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%
---
# Microsoft Dynamics 365 セルフサービスアプリでのAdobe Campaign Standard統合へのアクセス

この設定では、組織のExperience Cloud （EC）管理者と連携する必要があります。 これらは、セルフサービス統合アプリケーションインターフェイスへのアクセスを許可するために必要な最初の手順です。 ツールにアクセスできたら、データへの接続を設定し、Adobe CampaignとMicrosoft Dynamics 365間のデータフローを設定します。

>[!NOTE]
>
>Adobe担当者に連絡し、Adobe Campaign Standardの組織名とインスタンス名を指定する必要があります。 統合アプリが組織で有効になるようにリクエストするために、チケットがログに記録されます。

## 製品プロファイルの追加

この節では、Microsoft Dynamics 365 セルフサービスアプリでAdobe Campaign Standard統合へのアクセス権を付与する方法について説明します。 Adobe Experience Cloudで組織にアクセスできるユーザーは、以下の手順に従ってアクセス権を付与しない限り、統合セルフサービスアプリにアクセスできません。

>[!IMPORTANT]
>
> これらの手順を実行するには、組織のExperience Cloudで&#x200B;**管理者**&#x200B;の役割が必要です。
>

1. https://experience.adobe.com/を参照し、Adobe Experience Cloudにログインします。
1. **Admin Console**&#x200B;にアクセスします。

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. **[!UICONTROL Products]**&#x200B;をクリックして、Experience Cloud ソリューションにアクセスします。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >この節の残りの手順は、Campaign インスタンス（開発、テキスト、実稼動）ごとに実行されます。
   >

1. 最初のインスタンスをクリックして設定します。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   インスタンスページは次のようになります。

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 「**[!UICONTROL New Profile]**」ボタンをクリックし、**Campaign Standard - your-prod-instance-name - D365/ACS Integration**&#x200B;という名前の新しいエントリを追加します。

   * リストにこのエントリが表示された場合は、続行する必要はありません。 左側のメニューで「**Adobe Campaign Standard**」をクリックし、他のCampaign インスタンスを確認します。

   * 「your-prod-instance-name」をインスタンスの実際の名前に置き換えてください。

1. **[!UICONTROL Permission Group]** ドロップダウンはデフォルト値のままにできます。

1. エントリが次のようになっている場合は、「**[!UICONTROL Done]**」ボタンをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   新しい製品プロファイルが追加されました。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## ユーザーへのアクセスの許可 {#add-users-to-profile}

**[!UICONTROL Products]** ページから、Campaign インスタンスを選択し、次の手順に従います。

1. 以前に作成した新しいプロファイルをクリックします。**Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 「**[!UICONTROL Developers]**」タブをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 「**[!UICONTROL Add Developer]**」ボタンをクリックします

1. 追加するユーザーの名前または電子メールアドレスを入力します。  ユーザーに一致する結果を選択します。

   ユーザーが初めて組織に追加される場合は、詳細を入力します。

1. 「**[!UICONTROL Save]**」をクリックして確定します。
