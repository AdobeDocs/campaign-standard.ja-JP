---
title: Experience Manager での Campaign フォームの作成
description: Adobe Experience Managerとの連携により、AEMで直接フォームを作成し、プロファイルの作成と更新、サブスクリプションの管理をおこなうことができます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
TQID: 'https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 11%
---
# Experience Manager での Campaign フォームの作成 {#creating-a-campaign-form-in-experience-manager}

AEM サイトで「フォーム」を作成し、フォームのフィールドをAdobe Campaign データベースのフィールドにマッピングできます。 これにより、プロファイルを作成および更新したり、サービスのサブスクリプションを管理したりできます。

AEM サイトでAdobe Campaign フォームを作成するには：

1. AEM サイトで、**Adobe Campaign プロファイル** テンプレートに基づいて新しいページを作成します。

   ![](assets/aem_content_forms.png)

1. ページプロパティで、Adobe Campaign インスタンスに対応する&#x200B;**[!UICONTROL Cloud Service]**&#x200B;を選択します。

   ![](assets/aem_content_forms_2.png)

1. **[!UICONTROL Form Start]** コンポーネントからフォームタイプを選択します。

   * **Adobe Campaign: プロファイルを保存**
   * **Adobe Campaign: サービスの購読**
   * **Adobe Campaign: サービスの購読を解除**

1. Adobe Campaign データベースのフィールドにマッピングできる様々なフィールドとコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストして公開し、AEM サイトからアクセスできるようにします。

詳しくは、[詳細ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=ja)を参照してください。
