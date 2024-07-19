---
title: リソースの削除
description: リソースの削除方法を学ぶ
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# リソースの削除{#deleting-a-resource}

リソースを削除するには、そのリソースが **[!UICONTROL Draft]** である必要があります。 次の場合、リソースは **[!UICONTROL Draft]** ステータスになります。

* 作成されたばかりで、まだ公開されていません。
* 既に公開されている場合は、リソースを再度作成する必要があります。

>[!IMPORTANT]
>
>カスタム リソースの再製図と削除は、他のリソースに影響を与える可能性のある重要な操作です。 これらのアクションは、エキスパートユーザーのみが実行する必要があります。

公開済みリソースを再ドラフト化して削除するには：

1. 再ドラフト化するリソースを選択します。
1. アクションバーの「**[!UICONTROL Re-draft]**」ボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. 「**[!UICONTROL Ok]**」をクリックします。

   >[!IMPORTANT]
   >
   >これにより、変更が公開されると、リソースのデータベーステーブルまたは列とそのデータが完全に削除され、他のカスタムリソースからのリンクが壊れる可能性があります。 リソース定義のみが引き続き使用できます。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >標準の **Profiles （profile）** リソースの拡張機能を再ドラフトする場合は、定義した **テストプロファイル （seedMember）** 拡張機能も再ドラフトする必要があります。 プロファイルリソースの拡張について詳しくは、[ この節 ](../../developing/using/extending-the-profile-resource-with-a-new-field.md) を参照してください。

1. リソースをPublishします。 詳しい手順については、[ カスタムリソースの公開 ](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource) を参照してください。

   その後、リソースは **ドラフト** モードになり、アクティベーションステータスは **[!UICONTROL Inactive]** になります。

1. **[!UICONTROL List]** モードで、削除するリソースを確認し、「![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**」アイコンをクリックします。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。[ トランザクションイベントの非公開 ](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) を参照してください。
