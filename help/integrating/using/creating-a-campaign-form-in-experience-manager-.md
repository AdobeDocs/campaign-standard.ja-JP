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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---

# Experience Manager での Campaign フォームの作成 {#creating-a-campaign-form-in-experience-manager}

AEMサイト上で「フォーム」を作成し、フォーム内のフィールドをAdobe Campaignデータベースのフィールドにマッピングできます。 これにより、プロファイルを作成および更新したり、サービスの購読を管理したりできます。

AEMサイトでAdobe Campaignフォームを作成するには：

1. AEMサイトで、 **Adobe Campaign Profile** テンプレート。

   ![](assets/aem_content_forms.png)

1. ページのプロパティで、 **[!UICONTROL Cloud Service]** Adobe Campaignインスタンスに対応しています。

   ![](assets/aem_content_forms_2.png)

1. 次の中からフォームタイプを選択します。 **[!UICONTROL Form Start]** コンポーネント：

   * **Adobe Campaign：プロファイルを保存**
   * **Adobe Campaign：サービスを購読**
   * **Adobe Campaign：サービスの購読を解除**

1. Adobe Campaignデータベースフィールドにマッピングできる別のフィールドやコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストしてパブリッシュし、AEMサイト上でアクセスできるようにします。

詳しくは、[詳細なドキュメント](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)を参照してください。
