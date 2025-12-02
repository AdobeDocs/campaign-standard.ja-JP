---
title: Dynamics 365 セルフサービスアプリとAdobe Campaign Standard統合へのアクセス権を取得します
description: Adobe Campaign Standardと Dynamics 365 セルフサービスアプリの統合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 1%

---

# Microsoft Dynamics 365 セルフサービスアプリとAdobe Campaign Standard統合にアクセスする

この設定を行うには、所属する組織のExperience Cloud（EC）管理者と協力する必要があります。 これらは、セルフサービス統合アプリケーションインターフェイスへのアクセスを提供するために必要な最初の手順です。 ツールにアクセスしたら、データへの接続を設定し、Adobe CampaignとMicrosoft Dynamics 365 の間のデータフローを設定します。

>[!NOTE]
>
>Adobe担当者に連絡し、Adobe Campaign Standard組織とインスタンス名を指定する必要があります。 統合アプリを組織に対して有効にすることをリクエストするチケットがログに記録されます。

## 製品プロファイルの追加

この節では、Microsoft Dynamics 365 セルフサービスアプリとAdobe Campaign Standard統合へのアクセスを許可する方法について説明します。 以下の手順に従ってアクセス権を付与しない限り、Adobe Experience Cloudの組織にアクセスできるユーザーは、統合セルフサービスアプリにアクセスできません。

>[!IMPORTANT]
>
> これらの手順を実行するには、組織のExperience Cloudで **管理者** の役割が必要になります。
>

1. https://experience.adobe.com/を参照し、Adobe Experience Cloudにログインします。
1. **Admin Console** にアクセスします。

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. 「**[!UICONTROL Products]**」をクリックして、Experience Cloud ソリューションにアクセスします。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >この節の残りの手順は、各 Campaign インスタンス（開発、テキスト、実稼動）で実行されます。
   >

1. 設定する最初のインスタンスをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   インスタンスページは次のようになります。

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. 「**[!UICONTROL New Profile]**」ボタンをクリックし、**Campaign Standard - your-prod-instance-name - D365/ACS Integration** という名前の新しいエントリを追加します。

   * リストにこのエントリが表示された場合は、続行する必要はありません。 左側のメニューで **0&rbrace;Adobe Campaign Standard&rbrace; をクリックし、他の Campaign インスタンスを確認します。**

   * 「your-prod-instance-name」をインスタンスの実際の名前に必ず置き換えてください。

1. **[!UICONTROL Permission Group]** ドロップダウンはデフォルト値のままにすることができます。

1. エントリが次のような場合は、「**[!UICONTROL Done]**」ボタンをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   新しい製品プロファイルが追加されました。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## ユーザーへのアクセスの許可 {#add-users-to-profile}

**[!UICONTROL Products]** ページで Campaign インスタンスを選択し、次の手順に従います。

1. 先ほど作成した新しいプロファイルをクリックします。**Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 「**[!UICONTROL Developers]**」タブをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 「**[!UICONTROL Add Developer]**」ボタンをクリックします

1. 追加するユーザーの名前またはメールアドレスを入力します。  ユーザーに一致する結果を選択します。

   ユーザーが組織に初めて追加される場合は、詳細を入力します。

1. 「**[!UICONTROL Save]**」をクリックして確定します。
