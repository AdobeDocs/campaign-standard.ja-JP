---
title: リソースの削除
seo-title: リソースの削除
description: リソースの削除
seo-description: 'リソースの削除方法 '
page-status-flag: 常にアクティブ化されていない
uuid: 5de27589-6fa5-412c-8e5a- a4976de05715
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: 追加または拡張するリソース
discoiquuid: 0130733d-4e3f-40cd- b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Deleting a resource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* 作成されたばかりで、まだ公開されていません。
* 既に公開されている場合は、リソースを再作成する必要があります。

>[!CAUTION]
>
>カスタムリソースの再編成と削除は、他のリソースに影響を与える可能性のある、機密性の高い操作です。これらのアクションは、エキスパートユーザーのみが実行する必要があります。

公開済みリソースを再ドラフトおよび削除するには:

1. 再ドラフトするリソースを選択します。
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. **[!UICONTROL Ok]**&#x200B;をクリックします。

   >[!CAUTION]
   >
   >このアクションは確定的です。リソースのデータベーステーブルまたは列とデータは、変更が発行されると完全に削除され、その結果、他のカスタムリソースからのリンクが切断される可能性があります。リソース定義のみが使用可能になります。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >If you re-draft an extension of the out-of-the-box **Profiles (profile)** resource, you must also re-draft any **Test profile (seedMember)** extension you may have defined. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. リソースを公開します。For more detailed steps, refer to [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. **[!UICONTROL List]** モードで、削除するリソースをチェックしてアイコンを ![](assets/delete_darkgrey-24px.png)**[!UICONTROL Delete element]** クリックします。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除されると、対応するイベントが自動的に非公開になります。[トランザクションメッセージ](../../administration/using/configuring-transactional-messaging.md)の設定を参照してください。

