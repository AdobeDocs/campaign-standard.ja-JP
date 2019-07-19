---
title: 'Experience Managerでのキャンペーンフォームの作成 '
seo-title: 'Experience Managerでのキャンペーンフォームの作成 '
description: 'Experience Managerでのキャンペーンフォームの作成 '
seo-description: Adobe Experience Managerの統合により、AEMで直接フォームを作成して、プロファイルを作成および更新したり、購読を管理したりできます。
page-status-flag: 常にアクティブ化されていない
uuid: 43057f81- d47d-4b96- b150-217c289cd608
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- experience- manager
discoiquuid: 4a8b5807-87dd-4db4- bd67-890f0adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a Campaign form in Experience Manager {#creating-a-campaign-form-in-experience-manager}

AEMサイトで「フォーム」を作成し、フォームのフィールドをAdobe Campaignデータベースのフィールドにマッピングできます。これにより、プロファイルを作成および更新したり、サービスの購読を管理したりできます。

AEMサイトでAdobe Campaignフォームを作成するには:

1. AEMサイトで、** Adobe Campaign Profile**テンプレートに基づいて新しいページを作成します。

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. **[!UICONTROL Form Start]** コンポーネントからフォームの種類を選択します。

   * **Adobe Campaign:プロファイルの保存**
   * **Adobe Campaign:サービスの購読**
   * **Adobe Campaign:サービスの登録解除**

1. Adobe Campaignデータベースフィールドにマップできるフィールドとコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストして発行し、AEMサイトでアクセスできるようにします。

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html).
