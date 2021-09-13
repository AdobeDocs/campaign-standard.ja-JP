---
title: 組織単位
description: 組織単位を使用してユーザーのアクセスレベルを定義します。
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---

# 組織単位{#organizational-units}

## 単位について {#about-units}

プラットフォームの各オブジェクトとユーザーは、組織単位にリンクされます。 この単位を使用すると、フィルターを適用したビューをユーザーに提供するために階層構造を定義できます。 ユーザの単位は、異なるプラットフォームオブジェクトに対するユーザのアクセスレベルを定義する。

>[!IMPORTANT]
>
>ユーザーがどのユニットにもリンクされていない場合、そのユーザーはAdobe Campaignに接続できません。 特定のユーザーまたはユーザーのグループに対するアクセスを制限する場合は、**[!UICONTROL All]**&#x200B;ユニットにリンクしないでください。 プロファイルをインポートする前に、「**アクセス認証管理フィールド**」オプションを追加することをお勧めします。 詳しくは、[この節](../../administration/using/organizational-units.md#partitioning-profiles)を参照してください。
>
>デフォルトでは、**[!UICONTROL All (all)]** 組織単位は **[!UICONTROL Administrators]** セキュリティグループに割り当てられます。これは読み取り専用で、変更できません。

ユーザーは、親単位のすべてのオブジェクトに対して読み取り専用アクセス権を持ちます。 彼は、ユニットと子ユニットのすべてのオブジェクトに対する読み取りと書き込みのアクセス権を持っています。 ユーザーは、並列分岐のオブジェクトにアクセスできません。

デフォルトでは、**[!UICONTROL All]**&#x200B;単位のみ使用できます。

ユーザーに組織単位が割り当てられると、この単位は常にユーザーが作成したオブジェクトに適用されます。

![](assets/user_management_2.png)

>[!NOTE]
>
>ユーザーが複数のグループに属し、異なる単位にリンクされている場合、特定のルールが適用されます。 詳しくは、[グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)の節を参照してください。

## ユニットの作成と管理 {#creating-and-managing-units}

組織単位では、ユーザーがリンクされている組織に応じて、インスタンスをフィルタリングできます。 この単位は、インスタンス内の地域、国またはブランドを表すことができます。

ここでは、2人のユーザーに対して異なる役割を持つセキュリティグループを以前に作成しました。1人のユーザーにセキュリティグループAdministratorsとGeometrixxが割り当てられ、もう1人のユーザーはセキュリティグループStandardのユーザーとGeometrixxClothesセキュリティグループの作成と全体の例については[ユーザーの割り当て](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)を参照してください。

次に、Geometrixx服とGeometrixxセキュリティグループの組織単位を作成する必要があります。

1. Adobeキャンペーンの詳細設定メニューから、**[!UICONTROL Administration]** /**[!UICONTROL Users & security]** / **[!UICONTROL Organizational units]**&#x200B;を選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックして、組織単位の設定を開始します。

   ![](assets/manage_units_1.png)

1. デフォルトの&#x200B;**[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL ID]**&#x200B;をGeometrixxに変更します。
1. 次に、このユニットを親ユニットにリンクします。 ここでは、**[!UICONTROL All]**&#x200B;を選択します。

   ![](assets/manage_units_2.png)

1. 最後に、「**[!UICONTROL Create]**」をクリックして、新しい組織単位をセキュリティグループに割り当て始めます。
1. 同じ手順で、Geometrixx服用ユニットに対しても同じ手順を実行します。ただし、親ユニットは、前に作成したGeometrixxである必要があります。

   ![](assets/manage_units_3.png)

異なるユニットを異なるセキュリティグループに割り当てた場合の影響を確認するために、管理者とGeometrixxグループに割り当てられたユーザーは2つのEメールテンプレートを作成し、Standard UserとGeometrixx服に割り当てられたユーザーがアクセスできるかどうかを確認します。

1. 詳細設定メニューから、**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**&#x200B;を選択します。
1. 既存のテンプレートを複製して、必要に応じてパーソナライズします。 詳しくは、[テンプレートについて](../../start/using/marketing-activity-templates.md)の節を参照してください。
1. テンプレートを作成したら、**[!UICONTROL Edit properties]**&#x200B;アイコンを選択して、テンプレートに単位を割り当てます。

   ![](assets/manage_units_6.png)

1. **[!UICONTROL Access authorization]**&#x200B;ドロップダウンメニューで、組織単位を選択します。

   ここでは、前に作成した組織単位Geometrixxを使用して1つのテンプレートを作成します。

   ![](assets/manage_units_5.png)

1. 同じ手順に従って、前に作成したGeometrixx服組織単位に割り当てた2番目のテンプレートを作成します。

Standard UserグループとData Clothesグループに割り当てられたユーザーは、両方のGeometrixxを表示できます。 組織単位の階層構造のため、彼は、Geometrixxの服装単位にリンクされたテンプレートに対する読み取り/書き込みアクセス権と、Geometrixx単位にリンクされたテンプレートに対する読み取り専用アクセス権のみを持ちます。

![](assets/manage_units_7.png)

Geometrixx衣類ユニットはGeometrixxの子ユニットなので、ユーザーがGeometrixxテンプレートを変更しようとすると、次のメッセージが表示されます。

![](assets/manage_units_8.png)

組織単位は、プロファイルなどの様々な機能へのアクセスを制限できます。 例えば、Geometrixx服のユーザーが「**[!UICONTROL Profiles]**」タブにアクセスすると、Geometrixx服の組織単位を使用してプロファイルに完全にアクセスし、変更できます。

Geometrixx組織単位を持つプロファイルは読み取り専用ですが、ユーザーが1つのプロファイルを変更しようとすると、次のエラーが表示されます。**[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## プロファイルの分割 {#partitioning-profiles}

>[!IMPORTANT]
>
>組織単位のないプロファイルはユーザーがアクセスできないので、プロファイルをインポートする前に、このオプションを追加することをお勧めします。
>
>顧客データベースを既にインポートしている場合は、既にインポート済みのプロファイルに組織単位の値を設定するために、更新が必要です。

組織で、異なる各ブランドから連絡を受けたプロファイルを分離する必要がある場合、組織単位でプロファイルを分割できます。

デフォルトでは、組織単位フィールドはプロファイルで使用できないので、追加する必要があります。

1. Adobe Campaignのロゴから、詳細設定メニューの&#x200B;**管理/開発/カスタムリソース**&#x200B;を選択します。
1. 「**プロファイル**」を選択するか、新しいカスタムリソースを作成してプロファイルを拡張します。 プロファイルの拡張方法について詳しくは、この[ページ](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource)を参照してください。
1. 「**アクセス許可管理フィールドを追加**」ボックスをオンにして、**プロファイル**&#x200B;拡張機能に組織単位を追加します。

   ![](assets/user_management_9.png)

1. 「**[!UICONTROL Save]**」をクリックします。
1. カスタムリソースを再公開して構造を更新します。 公開プロセスについて詳しくは、[構造の更新](../../developing/using/updating-the-database-structure.md)の節を参照してください。

組織単位フィールドが&#x200B;**[!UICONTROL Access authorization]**&#x200B;セクションのプロファイルに追加されます。

![](assets/user_management_10.png)

**関連トピック**：

* [単位について](../../administration/using/organizational-units.md#about-units)
* [アクセス管理について](../../administration/using/about-access-management.md)
