---
solution: Campaign Standard
product: campaign
title: Adobe Experience Manager での E メールコンテンツの作成.
description: Adobe Experience Manager統合では、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 18%

---


# Adobe Experience ManagerのコンテンツをAdobe Campaignの電子メールにインポートする{#creating-email-aem}

このドキュメントを使用して、Adobe Experience Managerで電子メールコンテンツを作成および管理し、電子メールをAdobe Campaign Standardにインポートしてマーケティングキャンペーンに使用する方法を学びます。

前提は次のとおりです。

* 統合用に設定されたAEMインスタンスへのアクセス。
* 統合用に設定されたAdobe Campaignインスタンスへのアクセス。
* AEMコンテンツを受け取るように設定されたAdobe Campaign電子メールテンプレート。

## Adobe Experience Manager{#email-content-aem}の電子メールにアクセス中

Adobe Experience Managerオーサリングインスタンスにログインし、サイトを参照して、電子メールコンテンツが保存されているフォルダーにアクセスします。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Adobe Experience Manager での新しい E メールコンテンツの作成 {#creating-email-content-aem}

Adobe Campaign 専用のいくつかのテンプレートを使用できます。これらのテンプレートには Adobe Campaign でサポートされる定義済みのコンポーネントが含まれているので、これらのいずれかを必ず使用してください。

デフォルトでは、定義済みの2つのテンプレートを使用して、Adobe Campaign用の電子メールコンテンツを作成できます。

* **[!UICONTROL Adobe Campaign Email]**:このテンプレートには、パーソナライズ可能な標準コンテンツが含まれています。Adobe Campaign電子メール(AC6.1)とAdobe Campaign電子メール(ACS)のどちらかを選択できます。
* **[!UICONTROL Importer Page]**:このテンプレートを使用すると、HTMLファイルを含むZIPファイルとコンテンツを読み込んで、パーソナライズできるようにすることができます。

1. Adobe Experience Managerで、新しい&#x200B;**[!UICONTROL Page]**&#x200B;を作成します。

1. **[!UICONTROL Adobe Campaign Email]**&#x200B;テンプレートを選択します。 詳細手順については、次のビデオを参照してください。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 新しい電子メールコンテンツを開きます。

1. **[!UICONTROL Page properties]**&#x200B;内で、**[!UICONTROL Adobe Campaign]**&#x200B;を&#x200B;**[!UICONTROL Cloud Service Configuration]**&#x200B;として設定します。 これにより、コンテンツと Adobe Campaign インスタンスの間の通信が可能になります。

   詳しくは、次のビデオを参照してください。

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 電子メールの編集と送信{#editing-email-aem}

コンポーネントとアセットを追加して、電子メールコンテンツを編集できます。 パーソナライゼーションフィールドを使用して、Adobe Campaign内の受信者のデータに基づいて、より関連性の高いメッセージを配信できます。

Adobe Experience Managerで電子メールコンテンツを作成するには：

1. サイドキックから&#x200B;**[!UICONTROL Page properties]** > **[!UICONTROL Email]**&#x200B;タブにアクセスして、件名と電子メールの&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンを編集します。

1. 追加&#x200B;**[!UICONTROL Personalization fields]**&#x200B;から&#x200B;**[!UICONTROL Text & Personalization]**&#x200B;コンポーネントまで。 各コンポーネントは、次に示す特定の使用方法に対応します。画像の挿入、パーソナライゼーションの追加など

   詳しくは、次のビデオを参照してください。
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 「**[!UICONTROL Workflow]**」タブから、**[!UICONTROL Approve for Adobe Campaign]**&#x200B;検証ワークフローを選択します。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

1. コンテンツと送信パラメーターが定義されたら、Adobe Campaign Standardでの電子メールの承認、準備および送信に進むことができます。

   詳しくは、次のビデオを参照してください。

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
