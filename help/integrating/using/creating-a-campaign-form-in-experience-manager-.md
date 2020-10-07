---
title: 'Experience Manager での Campaign フォームの作成 '
description: Adobe Experience Manager統合では、AEMで直接フォームを作成し、プロファイルの作成と更新や購読の管理を行うことができます。
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# Experience Manager での Campaign フォームの作成 {#creating-a-campaign-form-in-experience-manager}

AEMサイトで「フォーム」を作成し、フォーム内のフィールドをAdobe Campaignデータベース内のフィールドにマップできます。 これにより、プロファイルの作成と更新、またはサービスへの購読の管理が可能になります。

AEMサイトでAdobe Campaignフォームを作成するには：

1. AEMサイトで、 **Adobe Campaignプロファイルテンプレートに基づいて新しいページを作成します** 。

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. コンポーネントからフォームタイプを選択し **[!UICONTROL Form Start]** ます。

   * **Adobe Campaign:プロファイルの保存**
   * **Adobe Campaign:サービスの購読**
   * **Adobe Campaign:サービスの登録解除**

1. Adobe Campaignデータベースフィールドにマップできるフィールドやコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストして発行し、AEMサイトでアクセス可能にします。

詳しくは、[詳細ドキュメント](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)を参照してください。
