---
title: 'Experience Manager でのキャンペーンフォームの作成 '
description: Adobe Experience Managerの統合により、AEMで直接フォームを作成し、プロファイルを作成および更新したり、購読を管理したりできます。
page-status-flag: 非活性化の
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとエクスペリエンスの管理職との連携
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Experience Manager でのキャンペーンフォームの作成{#creating-a-campaign-form-in-experience-manager}

AEMサイト上に「フォーム」を作成し、フォーム内のフィールドをAdobe Campaignデータベース内のフィールドにマッピングできます。 これにより、プロファイルを作成および更新したり、サービスの購読を管理したりできます。

AEMサイトにAdobe Campaignフォームを作成するには：

1. AEMサイトで、 **Adobe Campaignプロファイルテンプレートに基づいて新しいページを作成します** 。

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. コンポーネントからフォームの種類を選択 **[!UICONTROL Form Start]** します。

   * **Adobe Campaign:プロファイルの保存**
   * **Adobe Campaign:サービスの購読**
   * **Adobe Campaign:サービスの登録解除**

1. Adobe Campaignデータベースフィールドにマッピングできる様々なフィールドとコンポーネントを追加して、フォームのコンテンツを編集します。
1. フォームをテストして発行し、AEMサイト上でアクセス可能にします。

詳しくは、[詳細ドキュメント](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html)を参照してください。
