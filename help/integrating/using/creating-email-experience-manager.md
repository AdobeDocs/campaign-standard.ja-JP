---
title: Adobe Experience Managerでのメールコンテンツの作成。
description: Adobe Experience Manager統合を使用すると、コンテンツをAEMで直接作成して、後からAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: 579404ddc128e25cc7f8f93dfec30663c7cf754e
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 12%

---

# Adobe Experience Manager コンテンツのAdobe Campaign E メールへの読み込み {#creating-email-aem}

このドキュメントでは、Adobe Experience Managerでメールコンテンツを作成および管理し、メールに含めることでマーケティングキャンペーンに使用する方法をAdobe Campaign Standardで説明します。

前提は次のとおりです。

* 統合用に設定されたAEM インスタンスへのアクセス。
* 統合用に設定されたAdobe Campaign インスタンスへのアクセス。
* AEM コンテンツを受け取るように設定されたAdobe Campaign電子メールテンプレート。

## Adobe Experience Managerでのメールへのアクセス {#email-content-aem}

Adobe Experience Manager オーサーインスタンスにログインし、サイトを参照して、メールコンテンツを含むフォルダーにアクセスします。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Adobe Experience Manager での新しい E メールコンテンツの作成 {#creating-email-content-aem}

Adobe Campaign固有の複数のテンプレートを使用できます。 これらのテンプレートには Adobe Campaign でサポートされる定義済みのコンポーネントが含まれているので、これらのいずれかを必ず使用してください。

デフォルトでは、2 つの事前定義済みテンプレートを使用して、Adobe Campaignのメールコンテンツを作成できます。

* **[!UICONTROL Adobe Campaign Email]**：このテンプレートには、パーソナライズできる標準コンテンツが含まれています。 Adobe Campaign メール（AC6.1）とAdobe Campaign メール（ACS）から選択できます。
* **[!UICONTROL Importer Page]**：このテンプレートを使用すると、HTMLファイルを含む ZIP ファイルをコンテンツと共に読み込んで、コンテンツをパーソナライズできます。

1. Adobe Experience Managerで、新しい **[!UICONTROL Page]** を作成します。

1. **[!UICONTROL Adobe Campaign Email]** テンプレートを選択します。 手順について詳しくは、次のビデオを参照してください。

   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 新しいメールコンテンツを開きます。

1. **[!UICONTROL Page properties]** で、**[!UICONTROL Cloud Service Configuration]** として **[!UICONTROL Adobe Campaign]** を設定します。 これにより、コンテンツと Adobe Campaign インスタンスの間の通信が可能になります。

   詳しくは、次のビデオをご覧ください。

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## メールの編集と送信 {#editing-email-aem}

コンポーネントやアセットを追加して、メールのコンテンツを編集できます。 パーソナライゼーションフィールドを使用すると、Adobe Campaignの受信者のデータに基づいて、より関連性の高いメッセージを配信できます。

Adobe Experience Managerでメールコンテンツを作成するには：

1. サイドキックから **[!UICONTROL Page properties]** ール/**[!UICONTROL Email]** ールタブにアクセスして、メールの件名と **[!UICONTROL Plain text]** バージョンを編集します。

1. **[!UICONTROL Text & Personalization]** コンポーネントを使用して **[!UICONTROL Personalization fields]** を追加します。 各コンポーネントは、画像の挿入、パーソナライゼーションの追加などの特定の用途に対応します。

   詳しくは、次のビデオをご覧ください。

   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 「**[!UICONTROL Workflow]**」タブから、**[!UICONTROL Approve for Adobe Campaign]** 検証ワークフローを選択します。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

Adobe Campaign Standardでメールを送信するには：

1. コンテンツと送信パラメーターを定義したら、Adobe Campaign StandardでAEM固有のメールテンプレートに基づいてメールを作成します。

+++ AEM固有のテンプレートの詳細情報。

   1. 詳細メニューから、**[!UICONTROL Templates]** `>` **[!UICONTROL Delivery templates]** ージ **[!UICONTROL Resources]**`>` アクセスします。

      ![](assets/aem_templates_1.png)

   1. 配信テンプレートの 1 つを複製または選択します。

   1. テンプレートの **[!UICONTROL Properties]** から、「**[!UICONTROL Content]**」ドロップダウンでAdobe Experience Manager アカウント **[!UICONTROL Adobe Experience Manager as Content mode]** 選択します。

      ![](assets/aem_templates_2.png)

+++

   ![](assets/aem_send_1.png)

1. メールのプロパティを入力し、「**[!UICONTROL Create]**」をクリックしてAEM コンテンツを選択します。

1. **[!UICONTROL Content]** ブロックにアクセスします。

   ![](assets/aem_send_2.png)

1. **[!UICONTROL Use Adobe Experience Manager content]** メニューから、「**[!UICONTROL Link AEM content]**」をクリックします。

   次に、メールで使用するコンテンツを選択します。

   ![](assets/aem_send_3.png)

1. ダッシュボードを通じてターゲットオーディエンスや実行スケジュールなどの追加パラメーターを指定し、メールをさらにカスタマイズします。 設定が完了したら、メール配信を送信できます。 [詳細情報](../../sending/using/confirming-the-send.md)

