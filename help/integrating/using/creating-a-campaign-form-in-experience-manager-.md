---
solution: Campaign Standard
product: campaign
title: 'Experience Manager での Campaign フォームの作成 '
description: Adobe Experience Manager統合では、AEMで直接フォームを作成し、プロファイルの作成と更新や購読の管理を行うことができます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: トリガー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 12%

---


# Experience Manager での Campaign フォームの作成 {#creating-a-campaign-form-in-experience-manager}

AEMサイトで「フォーム」を作成し、フォーム内のフィールドをAdobe Campaignデータベース内のフィールドにマップできます。 これにより、プロファイルの作成と更新、またはサービスへの購読の管理が可能になります。

AEMサイトでAdobe Campaignフォームを作成するには：

1. AEMサイトで、**Adobe Campaignプロファイル**&#x200B;テンプレートを基にして新しいページを作成します。

   ![](assets/aem_content_forms.png)

1. ページのプロパティで、Adobe Campaignインスタンスに対応する&#x200B;**[!UICONTROL Cloud Service]**&#x200B;を選択します。

   ![](assets/aem_content_forms_2.png)

1. **[!UICONTROL Form Start]**&#x200B;コンポーネントからフォームタイプを選択します。

   * **Adobe Campaign:プロファイルの保存**
   * **Adobe Campaign:サービスの購読**
   * **Adobe Campaign:サービスの登録解除**

1. Adobe Campaignデータベースフィールドにマップできるフィールドやコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストして発行し、AEMサイトでアクセス可能にします。

詳しくは、[詳細ドキュメント](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)を参照してください。
