---
title: 組織単位
seo-title: 組織単位
description: 組織単位
seo-description: 組織単位を使用してユーザーのアクセスレベルを定義します。
page-status-flag: 常にアクティブ化されていない
uuid: 8c82ffa- proxf4-4a89- b823- d8b7bae1db4f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: ユーザーおよびセキュリティ
discoiquuid: 6f60c653-1d12-4d27-9bc8- ce8c19bca466
context-tags: OrgUnit， overview;orgUnit， main;地理和、概要、goUnit， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Organizational units{#organizational-units}

## About units {#about-units}

プラットフォームの各オブジェクトとユーザーは、組織単位にリンクされています。この単位を使用すると、ユーザにフィルターを適用したビューを表示するために階層構造を定義できます。ユーザーのユニットは、プラットフォームオブジェクトごとにアクセスレベルを定義します。

>[!CAUTION]
>
>ユーザーがどのユニットにもリンクされていない場合、そのユーザーはAdobe Campaignに接続できません。If you would like to restrict access for a particular user or group of users, do not link it to the **[!UICONTROL All]** unit.

ユーザーは、親単位内のすべてのオブジェクトに対する読み取り専用アクセス権を持ちます。そのユニットおよび子単位のすべてのオブジェクトに対する読み取りおよび書き込みのアクセス権があります。ユーザーは、並行してブランチのオブジェクトにアクセスできません。

By default, only the **[!UICONTROL All]** units are available.

ユーザーに組織単位が割り当てられると、この単位は常にユーザーが作成したオブジェクトに適用されます。

![](assets/user_management_2.png)

>[!NOTE]
>
>ユーザーが異なる単位にリンクされている複数のグループに属する場合、特定のルールが適用されます。For more information, refer to the [Managing groups and users](../../administration/using/managing-groups-and-users.md) section.

## Creating and managing units {#creating-and-managing-units}

組織単位では、ユーザーがリンクしている組織に応じてインスタンスをフィルターできます。この単位は、地域、国、またはそのインスタンスのブランドを表します。

Here, we previously created security groups with different roles to two users: one user is assigned the security groups Administrators and Geometrixx, the other user belongs to the security groups Standard user and Geometrixx Clothes See [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) for the full example.

Geometrixx CoverおよびGeometrixxセキュリティグループ用の組織単位を作成する必要があります。

1. From Adobe campaign advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Click **[!UICONTROL Create]** to start configuring your organizational unit.

   ![](assets/manage_units_1.png)

1. Change the default **[!UICONTROL Label]** and **[!UICONTROL ID]** to Geometrixx.
1. 次に、この単位を親単位にリンクします。**[!UICONTROL All]**&#x200B;ここでは、

   ![](assets/manage_units_2.png)

1. Finally, click **[!UICONTROL Create]** to start assigning your new organizational unit to security group.
1. Geometrixxの衣服ユニットと同じ手順に従います。ただし、その親単位は以前に作成した単位であるGeometrixxである必要があります。

   ![](assets/manage_units_3.png)

異なる単位をセキュリティグループに割り当てる影響を確認するために、管理者グループおよびGeometrixxグループに割り当てられているユーザーは、2つの電子メールテンプレートを作成して、標準ユーザーに割り当てられている他のユーザーとGeometrixx衣服にアクセスできないことを確認します。

1. From the advanced menu, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. 既存のテンプレートを複製し、必要に応じてパーソナライズします。For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. When the template is created, select the **[!UICONTROL Edit properties]** icon to assign units to your template.

   ![](assets/manage_units_6.png)

1. **[!UICONTROL Access authorization]** ドロップダウンメニューで、組織単位を選択します。

   ここでは、以前に作成した組織単位Geometrixxのテンプレートを1つ作成します。

   ![](assets/manage_units_5.png)

1. 同じ手順に従って、以前に作成したGeometrixx衣服の組織単位に割り当てられている2番目のテンプレートを作成します。

Standard UserおよびGeometrixxの衣服グループに割り当てられているユーザーは、両方のテンプレートを表示できます。組織単位の階層構造により、Geometrixxの衣服ユニットにリンクされているテンプレートに対する読み取りおよび書き込みアクセス権は、Geometrixxユニットにリンクされているテンプレートへの読み取り専用アクセス権のみになります。

![](assets/manage_units_7.png)

Geometrixxの衣服ユニットはGeometrixxの子単位なので、ユーザーがGeometrixxテンプレートを変更しようとすると、次のメッセージが表示されます。

![](assets/manage_units_8.png)

組織単位では、プロファイルなどの異なる機能へのアクセスを制限できます。For example, if our Geometrixx Clothes user access the **[!UICONTROL Profiles]** tab, he will be able to fully access and modify the profiles with the Geometrixx Clothes organizational unit.

Whereas the profiles with the Geometrixx organizational unit will be read only, the following error will appear if our user tries to modify one profile: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitioning profiles {#partitioning-profiles}

各ブランドによって連絡されたプロファイルを組織が分離する必要がある場合は、組織単位でプロファイルを分割できます。

デフォルトでは、組織単位フィールドはプロファイルで使用できず、追加する必要があります。

組織単位のないプロファイルには、ユーザーがアクセスできません。

>[!CAUTION]
>
>プロファイルをインポートする前に、このオプションを追加することをお勧めします。顧客データベースを既にインポートしている場合は、既に読み込まれているプロファイルに組織単位の値を設定するために更新が必要です。

1. From the advanced menu, via the Adobe Campaign logo, select **Administration &gt; Development &gt; Custom resources**.
1. Select **Profile** or create a new custom resource to extend the profiles.
1. Check the **Add access authorization management fields** box to add the organizational units in the **Profile** extension.

   ![](assets/user_management_9.png)

1. **[!UICONTROL Save]**&#x200B;をクリックします。
1. カスタムリソースを再公開して、構造を更新します。For more information about the publication process, refer to [Updating the structure](../../developing/using/data-model-concepts.md) section.

**[!UICONTROL Access authorization]** セクションのプロファイルに組織単位フィールドが追加されます。

![](assets/user_management_10.png)

**関連トピック**:

* [数量について](../../administration/using/organizational-units.md#about-units)
* [アクセス管理について](../../administration/using/about-access-management.md)

