---
title: Dynamics 365 Self-Service AppとのAdobe Campaign Standard統合へのアクセス
description: Dynamics 365 Self-Service AppとのAdobe Campaign Standard統合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM統合
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# Microsoft Dynamics 365 Self-Service AppとのAdobe Campaign Standard統合にアクセスする

この設定では、組織のExperience Cloud(EC)管理者と連携する必要があります。 以下は、セルフサービス統合アプリケーションインターフェイスへのアクセスを許可するために必要な最初の手順です。 ツールにアクセスできるようになると、データへの接続を設定し、Adobe CampaignとMicrosoft Dynamics 365の間のデータのフローを構成します。

>[!NOTE]
>
>Adobeの担当者に連絡し、Adobe Campaign Standardの組織名とインスタンス名を入力する必要があります。 組織で統合アプリを有効にするようにリクエストするためのチケットがログに記録されます。

## 商品追加プロファイル

この節では、Microsoft Dynamics 365セルフサービスアプリとのAdobe Campaign Standard統合へのアクセスを許可する方法を学びます。 次の手順に従ってアクセス権を付与しない限り、Adobe Experience Cloudで貴社へのアクセス権を持つユーザーは、統合セルフサービスアプリにアクセスできません。

>[!IMPORTANT]
>
> これらの手順では、組織のExperience Cloudに&#x200B;**管理者**&#x200B;の役割が必要です。


1. https://experience.adobe.com/を参照し、Adobe Experience Cloudにログインします。
1. **Admin Console**&#x200B;にアクセスします。

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. **[!UICONTROL Products]**&#x200B;をクリックして、Experience Cloudソリューションにアクセスします。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >この節の残りの手順は、各キャンペーンインスタンス（開発、テキスト、実稼働）に対して実行されます。

1. 設定する最初のインスタンスをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   インスタンスページは次のようになります。

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. **[!UICONTROL New Profile]**&#x200B;ボタンをクリックし、次の名前の新しいエントリを追加します。**Campaign Standard- your-prod-instance-name - D365/ACS統合**

   * リストにこのエントリが表示される場合は、続行する必要はありません。 左のメニューで&#x200B;**Adobe Campaign Standard**&#x200B;をクリックし、他のキャンペーンインスタンスを確認します。

   * 「your-prod-instance-name」は、必ずインスタンスの実際の名前に置き換えてください。

1. **[!UICONTROL Permission Group]**&#x200B;ドロップダウンはデフォルト値のままにしておくことができます。

1. エントリが次のように表示される場合は、「**[!UICONTROL Done]**」ボタンをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   新しい製品プロファイルが追加されました。

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## ユーザーへのアクセスを許可{#add-users-to-profile}

**[!UICONTROL Products]**&#x200B;ページで、キャンペーンインスタンスを選択し、次の手順に従います。

1. 以前に作成した新しいプロファイルをクリックします。 **Campaign Standard- your-prod-instance-name - D365/ACS統合**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. 「**[!UICONTROL Developers]**」タブをクリックします。

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. 「**[!UICONTROL Add Developer]**」ボタンをクリックします

1. 追加するユーザの名前または電子メールアドレスを入力します。  ユーザーに一致する結果を選択します。

   ユーザーが組織に初めて追加される場合は、詳細を入力します。

1. 「**[!UICONTROL Save]**」をクリックして確定します。
