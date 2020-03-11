---
title: Adobe Experience Manager での電子メールコンテンツの作成.
description: Adobe Experience Managerの統合により、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9efce905cd767013a22afb2a4d642e42b6616ef1

---


# Adobe Experience ManagerのコンテンツのAdobe Campaign電子メールへの読み込み {#creating-email-aem}

このドキュメントを使用して、Adobe Experience Managerで電子メールのコンテンツを作成および管理し、電子メールをAdobe Campaign Standardにインポートして、マーケティングキャンペーンに使用する方法を学びます。

前提条件は次のとおりです。

* 統合用に設定されたAEMインスタンスへのアクセス。
* 統合用に設定されたAdobe Campaignインスタンスへのアクセス。
* AEMコンテンツを受信するように設定されたAdobe Campaign電子メールテンプレート。

## Adobe Experience Managerでの電子メールへのアクセス {#email-content-aem}

Adobe Experience Managerオーサリングインスタンスにログインし、サイトを参照して、電子メールコンテンツを含むフォルダーにアクセスします。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

Adobe Campaign 専用のいくつかのテンプレートを使用できます。これらのテンプレートには Adobe Campaign でサポートされる定義済みのコンポーネントが含まれているので、これらのいずれかを必ず使用してください。

デフォルトでは、事前に定義された2つのテンプレートを使用して、Adobe Campaignの電子メールコンテンツを作成できます。

* **[!UICONTROL Adobe Campaign Email]**:このテンプレートには、パーソナライズ可能な標準コンテンツが含まれています。 「Adobe Campaign電子メール(AC6.1)」と「Adobe Campaign電子メール(ACS)」のどちらかを選択できます。
* **[!UICONTROL Importer Page]**:このテンプレートを使用すると、HTMLファイルを含むZIPファイルを読み込み、その内容をパーソナライズできます。

1. Adobe Experience Managerで、新しいを作成します **[!UICONTROL Page]**。

1. テンプレートを選 **[!UICONTROL Adobe Campaign Email]** 択します。 詳細手順については、次のビデオを参照してください。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 新しい電子メールの内容を開きます。

1. で、を **[!UICONTROL Page properties]**&#x200B;に設定 **[!UICONTROL Adobe Campaign]** します **[!UICONTROL Cloud Service Configuration]**。 これにより、コンテンツと Adobe Campaign インスタンスの間の通信が可能になります。

   詳しくは、次のビデオをご覧ください。

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 電子メールの編集と送信 {#editing-email-aem}

コンポーネントとアセットを追加して、電子メールのコンテンツを編集できます。 パーソナライゼーションフィールドを使用して、Adobe Campaignの受信者のデータに基づいて、より関連性の高いメッセージを配信できます。

Adobe Experience Managerで電子メールコンテンツを作成するには：

1. サイドキックから「/」タブに **[!UICONTROL Plain text]** アクセスして、件名と電子メ **[!UICONTROL Page properties]** ールのバ **[!UICONTROL Email]** ージョンを編集します。

1. コンポーネン **[!UICONTROL Personalization fields]** トを通じて追加 **[!UICONTROL Text & Personalization]** します。 各コンポーネントは、特定の使用方法に対応します。画像の挿入、パーソナライゼーションの追加など

   詳しくは、次のビデオをご覧ください。
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. タブから、検 **[!UICONTROL Workflow]** 証ワークフローを **[!UICONTROL Approve for Adobe Campaign]** 選択します。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

1. コンテンツと送信パラメーターを定義したら、Adobe Campaign Standardでの電子メールの承認、準備および送信に進むことができます。

   詳しくは、次のビデオをご覧ください。

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
