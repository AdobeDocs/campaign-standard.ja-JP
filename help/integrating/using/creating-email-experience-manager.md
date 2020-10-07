---
title: Adobe Experience Manager での E メールコンテンツの作成.
description: Adobe Experience Manager統合では、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 18%

---


# Adobe Campaign電子メールへのAdobe Experience Managerコンテンツの読み込み {#creating-email-aem}

このドキュメントを使用して、Adobe Experience Managerで電子メールコンテンツを作成および管理し、電子メールをAdobe Campaign Standardにインポートしてマーケティングキャンペーンに使用する方法を学びます。

前提は次のとおりです。

* 統合用に設定されたAEMインスタンスへのアクセス。
* 統合用に設定されたAdobe Campaignインスタンスへのアクセス。
* AEMコンテンツを受け取るように設定されたAdobe Campaign電子メールテンプレート。

## Adobe Experience Managerの電子メールへのアクセス {#email-content-aem}

Adobe Experience Managerオーサリングインスタンスにログインし、サイトを参照して、電子メールコンテンツが保存されているフォルダーにアクセスします。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Adobe Experience Manager での新しい E メールコンテンツの作成 {#creating-email-content-aem}

Adobe Campaign 専用のいくつかのテンプレートを使用できます。これらのテンプレートには Adobe Campaign でサポートされる定義済みのコンポーネントが含まれているので、これらのいずれかを必ず使用してください。

デフォルトでは、定義済みの2つのテンプレートを使用して、Adobe Campaign用の電子メールコンテンツを作成できます。

* **[!UICONTROL Adobe Campaign Email]**:このテンプレートには、パーソナライズ可能な標準コンテンツが含まれています。 Adobe Campaign電子メール(AC6.1)とAdobe Campaign電子メール(ACS)のどちらかを選択できます。
* **[!UICONTROL Importer Page]**:このテンプレートを使用すると、HTMLファイルを含むZIPファイルとコンテンツを読み込んで、パーソナライズできるようにすることができます。

1. Adobe Experience Managerで、新しいを作成し **[!UICONTROL Page]**&#x200B;ます。

1. テン **[!UICONTROL Adobe Campaign Email]** プレートを選択します。 詳細手順については、次のビデオを参照してください。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 新しい電子メールコンテンツを開きます。

1. で、 **[!UICONTROL Page properties]**&#x200B;をに設定 **[!UICONTROL Adobe Campaign]** し **[!UICONTROL Cloud Service Configuration]**&#x200B;ます。 これにより、コンテンツと Adobe Campaign インスタンスの間の通信が可能になります。

   詳しくは、次のビデオを参照してください。

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 電子メールの編集と送信 {#editing-email-aem}

コンポーネントとアセットを追加して、電子メールコンテンツを編集できます。 パーソナライゼーションフィールドを使用して、Adobe Campaign内の受信者のデータに基づいて、より関連性の高いメッセージを配信できます。

Adobe Experience Managerで電子メールコンテンツを作成するには：

1. サイドキックの「/」 **[!UICONTROL Plain text]** タブにアクセスして、件名と電子メールの **[!UICONTROL Page properties]****[!UICONTROL Email]** バージョンを編集します。

1. コンポー追加ネント **[!UICONTROL Personalization fields]** を通して表示され **[!UICONTROL Text & Personalization]** ます。 各コンポーネントは、次に示す特定の使用方法に対応します。画像の挿入、パーソナライゼーションの追加など

   詳しくは、次のビデオを参照してください。
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. タブから、 **[!UICONTROL Workflow]****[!UICONTROL Approve for Adobe Campaign]** 検証ワークフローを選択します。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

1. コンテンツと送信パラメーターが定義されたら、Adobe Campaign Standardでの電子メールの承認、準備および送信に進むことができます。

   詳しくは、次のビデオを参照してください。

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
