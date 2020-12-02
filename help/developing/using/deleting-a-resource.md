---
solution: Campaign Standard
product: campaign
title: リソースの削除
description: 'リソースを削除する方法を説明します '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: fc755f3176622e1faf08ccfa4236e016110f9a68
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 16%

---


# リソースの削除{#deleting-a-resource}

リソースを削除するには、対象のリソースが&#x200B;**[!UICONTROL Draft]**&#x200B;である必要があります。 次の場合、リソースは&#x200B;**[!UICONTROL Draft]**&#x200B;ステータスになります。

* まだ公開されていない。
* 既に公開されている場合は、リソースを再ドラフトする必要があります。

>[!IMPORTANT]
>
>カスタムリソースの再作図と削除は、他のリソースに影響を与える可能性のある機密操作です。 これらの操作は、エキスパートユーザーのみが実行する必要があります。

公開済みリソースを再ドラフトおよび削除するには：

1. 再ドラフトするリソースを選択します。
1. アクションバーの「**[!UICONTROL Re-draft]**」ボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. 「**[!UICONTROL Ok]**」をクリックします。

   >[!IMPORTANT]
   >
   >このアクションは次のとおり確定的です。変更が発行されると、リソースのデータベーステーブルまたは列とそのデータは完全に削除されるので、他のカスタムリソースからのリンクが壊れる可能性があります。 リソース定義のみが使用可能なままになります。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >既製の&#x200B;**プロファイル(プロファイル)**&#x200B;リソースの拡張子を再ドラフトする場合は、定義した任意の&#x200B;**テストプロファイル(seedMember)**&#x200B;拡張子も再ドラフトする必要があります。 プロファイルリソースの拡張についての詳細は、[このセクション](../../developing/using/extending-the-profile-resource-with-a-new-field.md)を参照してください。

1. リソースを公開. 詳細な手順については、[カスタムリソースの発行](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)を参照してください。

   次に、リソースが&#x200B;**ドラフト**&#x200B;モードに切り替わり、そのアクティベーションステータスは&#x200B;**[!UICONTROL Inactive]**&#x200B;です。

1. **[!UICONTROL List]**&#x200B;モードで、削除するリソースをチェックし、![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**&#x200B;アイコンをクリックします。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。[トランザクションイベントの非公開](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)を参照してください。
