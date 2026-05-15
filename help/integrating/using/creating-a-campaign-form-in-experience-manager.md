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
TQID: https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 187
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

詳しくは、[詳細ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)を参照してください。
