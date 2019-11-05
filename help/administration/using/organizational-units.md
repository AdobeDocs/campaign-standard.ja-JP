---
title: 組織単位
description: 組織単位を使用して、ユーザーのアクセスレベルを定義します。
page-status-flag: 非活性化の
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: ユーザーとセキュリティ
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 組織単位{#organizational-units}

## 単位について {#about-units}

プラットフォームの各オブジェクトおよびユーザは、組織単位にリンクされる。 このユニットは、ユーザにフィルタされたビューを与えるために階層構造を定義することを可能にします。 ユーザーのユニットは、異なるプラットフォームオブジェクトに対するアクセスレベルを定義します。

>[!CAUTION]
>
>ユーザーがどのユニットにもリンクされていない場合、そのユーザーはAdobe Campaignに接続できません。 特定のユーザーまたはユーザーのグループに対するアクセスを制限する場合は、ユニットにリンクしないでくだ **[!UICONTROL All]** さい。

ユーザは、親単位内のすべてのオブジェクトに対して読み取り専用アクセス権を持ちます。 彼は、自分のユニットと子ユニットのすべてのオブジェクトに対する読み取りと書き込みのアクセス権を持っている。 ユーザーは並行ブランチのオブジェクトにアクセスできません。

デフォルトでは、使用でき **[!UICONTROL All]** るのは単位のみです。

ユーザーに組織単位が割り当てられると、この単位は、ユーザーが作成したオブジェクトに常に適用されます。

![](assets/user_management_2.png)

>[!NOTE]
>
>ユーザーが複数のグループに属し、異なるユニットにリンクされている場合、特定のルールが適用されます。 詳しくは、「グループとユーザーの管 [理」の節を参照してください](../../administration/using/managing-groups-and-users.md) 。

## ユニットの作成と管理 {#creating-and-managing-units}

組織単位では、ユーザーがリンクされている組織に応じてインスタンスをフィルターできます。 このユニットは、地域、国、またはインスタンス内のブランドを表すことができます。

ここでは、2人のユーザーに対して異なる役割を持つセキュリティグループを以前に作成しました。1人のユーザーに「管理者」と「Geometrixx」というセキュリティグループが割り当てられ、もう1人のユーザーは「Standard」ユーザーと「Geometrixx Chooges」セキュリティグループに属します。詳しくは、「セキュリテ [ィグループの作成と完全な例のユーザーの割り当て](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) 」を参照してください。

次に、Geometrixx CloashsとGeometrixxセキュリティグループの組織単位を作成する必要があります。

1. Adobe campaignのアドバンスメニューで、// **[!UICONTROL Administration]** を選 **[!UICONTROL Users & security]** 択しま **[!UICONTROL Organizational units]**&#x200B;す。
1. をクリッ **[!UICONTROL Create]** クして、組織単位の設定を開始します。

   ![](assets/manage_units_1.png)

1. デフォルトの「」と「Geometrixx」 **[!UICONTROL Label]** を変 **[!UICONTROL ID]** 更します。
1. 次に、このユニットを親ユニットにリンクします。 ここで選んだ **[!UICONTROL All]**。

   ![](assets/manage_units_2.png)

1. 最後に、をクリックし **[!UICONTROL Create]** て、新しい組織単位のセキュリティグループへの割り当てを開始します。
1. Geometrixx Choosesユニットに対しても同じ手順を実行しますが、親ユニットは以前に作成したユニットGeometrixxである必要があります。

   ![](assets/manage_units_3.png)

異なるセキュリティグループに異なる単位を割り当てた場合の影響を確認するために、管理者グループとGeometrixxグループに割り当てたユーザーは2つの電子メールテンプレートを作成し、Standard UserおよびGeometrixx Choosesに割り当てた他のユーザーがアクセスできるかどうかを確認します。

1. アドバンスメニューで、// **[!UICONTROL Resources]** を選 **[!UICONTROL Templates]** 択しま **[!UICONTROL Delivery Templates]**&#x200B;す。
1. 既存のテンプレートを複製し、必要に応じてパーソナライズします。 For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. テンプレートを作成したら、アイコンを選択し **[!UICONTROL Edit properties]** て、テンプレートに単位を割り当てます。

   ![](assets/manage_units_6.png)

1. ドロップダウ **[!UICONTROL Access authorization]** ンメニューで、組織単位を選択します。

   ここでは、以前に作成した組織単位Geometrixxを使用して1つのテンプレートを作成します。

   ![](assets/manage_units_5.png)

1. 同じ手順で、以前に作成したGeometrixx Choognes組織単位に割り当てた2番目のテンプレートを作成します。

「Standard User」グループと「Geometrixx Chooses」グループに割り当てられたユーザーは、両方のテンプレートを表示できます。 組織単位の階層構造により、Geometrixx Chooses単位にリンクされたテンプレートに対する読み取りと書き込みのアクセス権を持ち、Geometrixx単位にリンクされたテンプレートに対する読み取り専用のアクセス権のみを持ちます。

![](assets/manage_units_7.png)

Geometrixx ChoogesのユニットはGeometrixxの子ユニットなので、ユーザーがGeometrixxテンプレートを変更しようとすると、次のメッセージが表示されます。

![](assets/manage_units_8.png)

組織単位は、プロファイルなどの様々な機能へのアクセスを制限できます。 例えば、Geometrixx Choogesのユーザーがタブにアクセスすると、 **[!UICONTROL Profiles]** Geometrixx Choogesの組織単位でプロファイルに完全にアクセスし、変更を加えることができます。

Geometrixx組織単位のプロファイルは読み取り専用ですが、ユーザーが1つのプロファイルを変更しようとすると、次のエラーが表示されます。 **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## 分割プロファイル {#partitioning-profiles}

組織が様々なブランドから連絡を受けたプロファイルを分離する必要がある場合は、組織単位でプロファイルを分割できます。

デフォルトでは、プロファイルで組織単位フィールドを使用できないので、追加する必要があります。

組織単位のないプロファイルは、ユーザーはアクセスできません。

>[!CAUTION]
>
>プロファイルをインポートする前に、このオプションを追加することをお勧めします。 顧客データベースを既にインポート済みの場合は、既にインポート済みのプロファイルに組織単位の値を設定するために更新が必要です。

1. アドバンスメニューのAdobe Campaignロゴから、管理/開発/カスタム **リソースを選択します**。
1. 「 **Profile** 」を選択するか、新しいカスタムリソースを作成してプロファイルを拡張します。
1. プロファイル拡 **張子に組織単位を追加するには、「アクセス許可管理フィールドを追加** 」ボックスをオン **にします** 。

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. カスタムリソースを再公開して構造を更新します。 発行プロセスの詳細については、「構造の更新」を [参照してください](../../developing/using/data-model-concepts.md) 。

セクション内のプロファイルに組織単位フィールドが追加さ **[!UICONTROL Access authorization]** れます。

![](assets/user_management_10.png)

**関連トピック**：

* [単位について](../../administration/using/organizational-units.md#about-units)
* [アクセス管理について](../../administration/using/about-access-management.md)

