---
title: リソースの削除
description: 'リソースを削除する方法を説明します '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 16%

---


# リソースの削除{#deleting-a-resource}

リソースを削除するには、該当するリソースがである必要があり **[!UICONTROL Draft]**&#x200B;ます。 次の場合、リソースはステータス **[!UICONTROL Draft]** です。

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
   >既製の **プロファイル(プロファイル)** リソースの拡張機能を再ドラフトする場合は、定義済みの **** テストプロファイル(seedMember)拡張機能も再ドラフトする必要があります。 For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. リソースを公開. 詳しい手順については、「カスタムリソースの [発行](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)」を参照してください。

   次に、リソースが **ドラフト** モードに切り替わり、アクティベーションステータスが **[!UICONTROL Inactive]**&#x200B;になります。

1. モードで、削除するリソースをチェックし、 **[!UICONTROL List]** アイコンをクリックし ![](assets/delete_darkgrey-24px.png)**[!UICONTROL Delete element]** ます。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

