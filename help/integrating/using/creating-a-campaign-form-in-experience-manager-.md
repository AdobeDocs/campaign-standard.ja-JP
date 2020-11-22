---
solution: Campaign Standard
product: campaign
title: 'Experience Manager での Campaign フォームの作成 '
description: Adobe Experience Manager統合では、AEMで直接フォームを作成し、プロファイルの作成と更新や購読の管理を行うことができます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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
