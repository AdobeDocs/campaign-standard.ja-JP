---
title: Adobe Experience Manager での E メールコンテンツの作成.
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 18%

---

# Adobe Campaign EメールへのAdobe Experience Managerコンテンツの読み込み {#creating-email-aem}

このドキュメントを使用して、Adobe Experience ManagerでEメールコンテンツを作成および管理し、EメールでAdobe Campaign StandardにインポートしてEメールコンテンツをマーケティングキャンペーンで使用する方法を学びます。

前提は次のとおりです。

* 統合用に設定されたAEMインスタンスへのアクセス。
* 統合用に設定されたAdobe Campaignインスタンスへのアクセス。
* AEMコンテンツを受け取るように設定されたAdobe Campaign Eメールテンプレート。

## Adobe Experience ManagerでのEメールへのアクセス {#email-content-aem}

Adobe Experience Managerオーサリングインスタンスにログインし、サイトを参照して、電子メールコンテンツが含まれているフォルダーにアクセスします。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Adobe Experience Manager での新しい E メールコンテンツの作成 {#creating-email-content-aem}

Adobe Campaign 専用のいくつかのテンプレートを使用できます。これらのテンプレートには Adobe Campaign でサポートされる定義済みのコンポーネントが含まれているので、これらのいずれかを必ず使用してください。

デフォルトでは、2つの定義済みテンプレートを使用して、Adobe Campaign用のEメールコンテンツを作成できます。

* **[!UICONTROL Adobe Campaign Email]**:このテンプレートには、パーソナライズ可能な標準コンテンツが含まれています。Adobe Campaign電子メール(AC6.1)とAdobe Campaign電子メール(ACS)のどちらかを選択できます。
* **[!UICONTROL Importer Page]**:このテンプレートを使用すると、HTMLファイルを含むZIPファイルとコンテンツをインポートし、パーソナライズできます。

1. Adobe Experience Managerで、新しい&#x200B;**[!UICONTROL Page]**&#x200B;を作成します。

1. **[!UICONTROL Adobe Campaign Email]**&#x200B;テンプレートを選択します。 詳細な手順については、次のビデオを参照してください。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 新しいEメールコンテンツを開きます。

1. **[!UICONTROL Page properties]**&#x200B;で、**[!UICONTROL Adobe Campaign]**&#x200B;を&#x200B;**[!UICONTROL Cloud Service Configuration]**&#x200B;に設定します。 これにより、コンテンツと Adobe Campaign インスタンスの間の通信が可能になります。

   詳しくは、次のビデオをご覧ください。

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Eメールの編集と送信 {#editing-email-aem}

コンポーネントとアセットを追加して、Eメールのコンテンツを編集できます。 パーソナライゼーションフィールドを使用して、Adobe Campaignで受信者のデータに基づいて、より関連性の高いメッセージを配信できます。

Adobe Experience ManagerでEメールコンテンツを作成するには：

1. サイドキックの&#x200B;**[!UICONTROL Page properties]** / **[!UICONTROL Email]**&#x200B;タブにアクセスして、件名とEメールの&#x200B;**[!UICONTROL Plain text]**&#x200B;バージョンを編集します。

1. **[!UICONTROL Personalization fields]**&#x200B;を&#x200B;**[!UICONTROL Text & Personalization]**&#x200B;コンポーネントを通して追加します。 各コンポーネントは、特定の使用方法に対応します。画像の挿入、パーソナライゼーションの追加など

   詳しくは、次のビデオをご覧ください。
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 「**[!UICONTROL Workflow]**」タブで、**[!UICONTROL Approve for Adobe Campaign]**&#x200B;検証ワークフローを選択します。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

1. コンテンツと送信パラメーターを定義したら、Adobe Campaign StandardでEメールの承認、準備、送信に進むことができます。

   詳しくは、次のビデオをご覧ください。

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
