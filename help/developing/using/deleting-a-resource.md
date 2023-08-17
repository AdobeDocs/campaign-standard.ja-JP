---
title: リソースの削除
description: リソースを削除する方法を説明します
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
ht-degree: 16%

---

# リソースの削除{#deleting-a-resource}

リソースを削除するには、該当するリソースが **[!UICONTROL Draft]**. リソースがにあります **[!UICONTROL Draft]** ステータス：

* 作成されたばかりで、まだ公開されていません。
* 既に公開されている場合は、リソースを再ドラフト化する必要があります。

>[!IMPORTANT]
>
>カスタムリソースの再ドラフトと削除は、他のリソースに影響を与える可能性のある機密操作です。 これらのアクションは、エキスパートユーザーのみが実行する必要があります。

公開済みリソースの再ドラフトおよび削除するには：

1. 再ドラフトするリソースを選択します。
1. アクションバーの「**[!UICONTROL Re-draft]**」ボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. 「**[!UICONTROL Ok]**」をクリックします。

   >[!IMPORTANT]
   >
   >このアクションは確定的です。リソースのデータベーステーブルまたは列とそのデータは、変更が公開されると完全に削除され、他のカスタムリソースからのリンクが壊れる可能性があります。 リソース定義のみが使用可能なままになります。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >標準搭載の拡張機能を再ドラフト化する場合 **プロファイル (profile)** リソースを再度ドラフトする必要があります。 **テストプロファイル (seedMember)** 定義済みの拡張機能。 プロファイルリソースの拡張について詳しくは、 [この節](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. リソースを公開します。詳しい手順については、 [カスタムリソースの公開](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   リソースは次に **ドラフト** モードとそのアクティベーションステータスは次のとおりです。 **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** モード、削除するリソースを確認し、 ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** アイコン。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。詳しくは、 [トランザクションイベントの非公開](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
