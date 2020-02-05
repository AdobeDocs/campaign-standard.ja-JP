---
title: リソースの削除
description: 'リソースを削除する方法 '
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
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# リソースの削除{#deleting-a-resource}

リソースを削除するには、対象のリソースがである必要がありま **[!UICONTROL Draft]**す。 次の場合、リソースはステ**[!UICONTROL Draft]** ータスになります。

* 作成されたばかりで、まだ公開されていません。
* 既に公開されている場合は、そのリソースを再起草する必要があります。

>[!CAUTION]
>
>カスタムリソースの再作図と削除は、他のリソースに影響を与える可能性のある機密性の高い操作です。 これらの操作は、エキスパートユーザーのみが実行する必要があります。

公開済みリソースを再ドラフトおよび削除するには：

1. 再ドラフトするリソースを選択します。
1. アクションバ **[!UICONTROL Re-draft]**ーのボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. クリック **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >このアクションは次のとおりです。変更が発行されると、リソースのデータベーステーブルまたは列とそのデータが完全に削除され、その結果、他のカスタムリソースからのリンクが破損する可能性があります。 リソース定義のみが使用可能なままになります。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >標準搭載のプロファイル（プロファイル）リソースの拡張機能を再ドラフトする場合は、定義した **Testプロファイル(seedMember)拡張も再ドラフトする必要があります****** 。 プロファイルリソースの拡張の詳細については、この節を [参照してくださ](../../developing/using/extending-the-profile-resource-with-a-new-field.md)い。

1. リソースをパブリッシュ. 詳細な手順については、「カスタムリソースの [公開」を参照してください](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   次に、リソースがドラフトモ **ードに入り** 、そのアクティブ化ステータスが **[!UICONTROL Inactive]**です。

1. モード **[!UICONTROL List]**&#x200B;で、削除するリソースを確認し、アイコンをクリック![](assets/delete_darkgrey-24px.png)し&#x200B;**[!UICONTROL Delete element]** ます。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除されると、対応するイベントは自動的に非公開になります。 See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

