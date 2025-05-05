---
title: Experience Manager での Campaign フォームの作成
description: Adobe Experience Manager統合を使用すると、AEMで直接フォームを作成して、プロファイルを作成および更新したり、購読を管理したりできます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---

# Experience Manager での Campaign フォームの作成 {#creating-a-campaign-form-in-experience-manager}

AEM サイトに「フォーム」を作成し、フォーム内のフィールドをAdobe Campaign データベースのフィールドにマッピングできます。 これにより、プロファイルを作成および更新したり、サービスの購読を管理したりできます。

AEM サイトにAdobe Campaign フォームを作成するには、次の手順を実行します。

1. AEM サイトで、**Adobe Campaign プロファイル** テンプレートに基づいて新しいページを作成します。

   ![](assets/aem_content_forms.png)

1. ページプロパティで、Adobe Campaign インスタンスに対応する **[!UICONTROL Cloud Service]** を選択します。

   ![](assets/aem_content_forms_2.png)

1. **[!UICONTROL Form Start]** コンポーネントからフォームタイプを選択します。

   * **Adobe Campaign: プロファイルを保存**
   * **Adobe Campaign: サービスに登録する**
   * **Adobe Campaign: サービスの登録を解除**

1. Adobe Campaign データベースフィールドにマッピングできる様々なフィールドとコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストして公開し、AEM サイトでアクセスできるようにします。

詳しくは、[詳細なドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=ja)を参照してください。
