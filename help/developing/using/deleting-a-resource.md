---
title: リソースの削除
description: 'リソースを削除する方法を説明します。 '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6cf00f9b9bafdd54d8424a353b33dc689c0f59aa

---


# リソースの削除{#deleting-a-resource}

リソースを削除するには、対象のリソースがである必要がありま **[!UICONTROL Draft]**&#x200B;す。 次の場合、リソースはステ **[!UICONTROL Draft]** ータスになります。

* 作成されたばかりで、まだ公開されていません。
* 既に公開されている場合は、そのリソースを再度ドラフトする必要があります。

>[!IMPORTANT]
>
>カスタムリソースの再作図と削除は、他のリソースに影響を与える可能性のある機密操作です。 これらのアクションは、エキスパートユーザーのみが実行する必要があります。

公開済みリソースの再ドラフトと削除を行うには：

1. 再ドラフトするリソースを選択します。
1. アクションバ **[!UICONTROL Re-draft]** ーのボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. クリック **[!UICONTROL Ok]** .

   >[!IMPORTANT]
   >
   >このアクションは次のとおりです。変更が発行されると、リソースのデータベーステーブルまたは列とそのデータが完全に削除され、その結果、他のカスタムリソースからのリンクが切断される可能性があります。 リソース定義のみが使用可能なままになります。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >標準搭載の **プロファイル(プロファイル)リソースの拡張を再ドラフトする場合は、定義した任意の** Testプロファイル(seedMember)拡張も再ドラフトする必要があります **** 。 リソースの拡張の詳細については、このプロファイルの節を参 [照してくださ](../../developing/using/extending-the-profile-resource-with-a-new-field.md)い。

1. リソースをパブリッシュ. 詳細な手順については、「カスタムリソースの [公開」を参照してください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   次に、リソースがドラフトモ **ードに入り** 、アクティベーションのステータスが **[!UICONTROL Inactive]**。

1. モード **[!UICONTROL List]** で、削除するリソースをチェックし、アイコンをクリッ ![](assets/delete_darkgrey-24px.png) クしま **[!UICONTROL Delete element]** す。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。 See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

