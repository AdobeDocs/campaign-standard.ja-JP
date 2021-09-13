---
title: リソースの削除
description: 'リソースの削除方法を説明します '
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

リソースを削除するには、対象のリソースが&#x200B;**[!UICONTROL Draft]**&#x200B;である必要があります。 次の場合、リソースのステータスは&#x200B;**[!UICONTROL Draft]**&#x200B;です。

* 作成されたばかりで、まだ公開されていません。
* 既にパブリッシュ済みの場合は、リソースを再ドラフトする必要があります。

>[!IMPORTANT]
>
>カスタムリソースの再ドラフトと削除は、他のリソースに影響を与える可能性のある機密操作です。 これらのアクションは、エキスパートユーザーのみが実行する必要があります。

公開済みリソースの再ドラフトおよび削除をおこなうには：

1. 再ドラフトするリソースを選択します。
1. アクションバーの「**[!UICONTROL Re-draft]**」ボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. 「**[!UICONTROL Ok]**」をクリックします。

   >[!IMPORTANT]
   >
   >このアクションは確定的です。変更が公開されると、リソースのデータベーステーブルまたは列とそのデータが完全に削除され、他のカスタムリソースからのリンクが壊れる可能性があります。 リソース定義のみが使用可能なままになります。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >標準搭載の&#x200B;**Profiles (profile)**&#x200B;リソースの拡張を再ドラフトする場合は、定義した&#x200B;**Test profile (seedMember)**&#x200B;拡張も再ドラフトする必要があります。 プロファイルリソースの拡張について詳しくは、[この節](../../developing/using/extending-the-profile-resource-with-a-new-field.md)を参照してください。

1. リソースを公開. 詳しい手順については、[カスタムリソースのパブリッシュ](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)を参照してください。

   次に、リソースが&#x200B;**ドラフト**&#x200B;モードになり、そのアクティベーションステータスは&#x200B;**[!UICONTROL Inactive]**&#x200B;になります。

1. **[!UICONTROL List]**&#x200B;モードで、削除するリソースを確認し、![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**&#x200B;アイコンをクリックします。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。[トランザクションイベントの非公開](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)を参照してください。
