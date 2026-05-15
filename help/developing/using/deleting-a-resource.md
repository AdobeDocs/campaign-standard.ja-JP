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
TQID: https://experienceleague.adobe.com/cDShxyrLISaGidkLNnhtMwZHbo8SlRie6DTV0yVR6IY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 15%

---

# リソースの削除{#deleting-a-resource}

リソースを削除するには、対象となるリソースが&#x200B;**[!UICONTROL Draft]**&#x200B;である必要があります。 次の場合、リソースは&#x200B;**[!UICONTROL Draft]** ステータスになります。

* 作成されたばかりで、まだ公開されていません。
* 既に公開されている場合は、リソースを再作成する必要があります。

>[!IMPORTANT]
>
>カスタムリソースの再作成と削除は、他のリソースに影響を与える可能性のある機密性の高い操作です。 これらのアクションは、エキスパートユーザーのみが実行する必要があります。

公開したリソースを再ドラフトして削除するには：

1. 再作成するリソースを選択します。
1. アクションバーの「**[!UICONTROL Re-draft]**」ボタンをクリックします。

   ![](assets/schema_extension_uc26.png)

1. 「**[!UICONTROL Ok]**」をクリックします。

   >[!IMPORTANT]
   >
   >このアクションは決定的です。リソースのデータベーステーブルまたはカラムとそのデータは、変更が公開されると完全に削除され、他のカスタムリソースからのリンクが壊れる可能性があります。 リソース定義のみが使用できます。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >標準の&#x200B;**プロファイル（プロファイル）** リソースの拡張機能を再ドラフトする場合は、定義した&#x200B;**テストプロファイル（シードメンバー）**&#x200B;拡張機能も再ドラフトする必要があります。 プロファイルリソースの拡張について詳しくは、[この節](../../developing/using/extending-the-profile-resource-with-a-new-field.md)を参照してください。

1. リソースを公開します。 詳細な手順については、[&#x200B; カスタムリソースの公開](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)を参照してください。

   その後、リソースは&#x200B;**ドラフト** モードになり、アクティベーションのステータスは&#x200B;**[!UICONTROL Inactive]**&#x200B;です。

1. **[!UICONTROL List]** モードで、削除するリソースを確認し、![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** アイコンをクリックします。

   ![](assets/schema_extension_uc28.png)

リソースがデータモデルから削除されます。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。 「[&#x200B; トランザクションイベントの非公開](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)」を参照してください。
