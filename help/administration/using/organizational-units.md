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
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 5%

---

# 組織単位{#organizational-units}

## 単位について {#about-units}

プラットフォームの各オブジェクトとユーザーは、組織単位にリンクされます。 この単位では、ユーザにフィルターを適用したビューを提供するために、階層構造を定義できます。 ユーザーの単位は、異なるプラットフォームオブジェクトに対するユーザーのアクセスレベルを定義します。

>[!IMPORTANT]
>
>ユーザーがどのユニットにもリンクされていない場合、そのユーザーはAdobe Campaignに接続できません。 特定のユーザーまたはユーザーグループに対するアクセスを制限する場合は、これを **[!UICONTROL All]** 単位。 オプションを追加することをお勧めします **認証管理フィールドへのアクセス** プロファイルを読み込む前に 詳しくは、[この節](../../administration/using/organizational-units.md#partitioning-profiles)を参照してください。
>
>デフォルトでは、**[!UICONTROL All (all)]** 組織単位は **[!UICONTROL Administrators]** セキュリティグループに割り当てられます。これは読み取り専用で、変更できません。

ユーザーは、親単位のすべてのオブジェクトに対して読み取り専用アクセス権を持ちます。 このようなユーザは、ユニットと子ユニットのすべてのオブジェクトに対する読み取りと書き込みのアクセス権を持っています。 ユーザーは並列分岐のオブジェクトにアクセスできません。

デフォルトでは、 **[!UICONTROL All]** 単位を使用できます。

ユーザーに組織単位が割り当てられると、この単位は常にユーザーが作成したオブジェクトに適用されます。

![](assets/user_management_2.png)

>[!NOTE]
>
>異なる単位にリンクされた複数のグループに属するユーザーの場合、特定のルールが適用されます。 詳しくは、 [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md) 」セクションに入力します。

## ユニットの作成と管理 {#creating-and-managing-units}

組織単位では、ユーザーがリンクされている組織に応じて、インスタンスをフィルタリングできます。 この単位は、インスタンス内の地域、国またはブランドを表すことができます。

ここでは、2 人のユーザーに対して異なる役割を持つセキュリティグループを以前に作成しました。1 人のユーザーにセキュリティグループが割り当てられました管理者とGeometrixx、もう 1 人のユーザーはセキュリティグループに属しています。標準ユーザーとGeometrixx服参照 [セキュリティグループの作成とユーザーの割り当て](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) を参照してください。

次に、Geometrixx服とGeometrixxセキュリティグループの組織単位を作成する必要があります。

1. Adobeキャンペーンの詳細設定メニューから、 **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. クリック **[!UICONTROL Create]** をクリックして、組織単位の設定を開始します。

   ![](assets/manage_units_1.png)

1. デフォルトを変更 **[!UICONTROL Label]** および **[!UICONTROL ID]** Geometrixxへ。
1. 次に、このユニットを親ユニットにリンクします。 ここでは、次を選択します。 **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. 最後に、「 **[!UICONTROL Create]** ：新しい組織単位をセキュリティグループに割り当て始めます。
1. 同じ手順で、Geometrixx服のユニットも同じです。ただし、親のユニットは、前に作成したGeometrixxである必要があります。

   ![](assets/manage_units_3.png)

異なるユニットを異なるセキュリティグループに割り当てた場合の影響を確認するために、管理者とGeometrixxグループに割り当てたユーザーは 2 つの E メールテンプレートを作成し、Standard User とGeometrixx服に割り当てたユーザーがアクセスできるかどうかを確認します。

1. 詳細設定メニューから、 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. 既存のテンプレートを複製し、必要に応じてパーソナライズします。 詳しくは、[テンプレートについて](../../start/using/marketing-activity-templates.md)の節を参照してください。
1. テンプレートを作成したら、 **[!UICONTROL Edit properties]** アイコンを使用して、テンプレートに単位を割り当てます。

   ![](assets/manage_units_6.png)

1. 内 **[!UICONTROL Access authorization]** ドロップダウンメニューから、組織単位を選択します。

   ここでは、前に作成した組織単位Geometrixxを使用して 1 つのテンプレートを作成します。

   ![](assets/manage_units_5.png)

1. 同じ手順に従って、前の手順で作成したGeometrixx服の組織単位に割り当てた 2 番目のテンプレートを作成します。

に割り当てられたユーザー **標準ユーザー** および **Geometrixx服** グループは、両方のテンプレートを表示できます。 組織単位の階層構造により、Geometrixx服の単位にリンクされたテンプレートに対する読み取り/書き込みアクセス権と、Geometrixx単位にリンクされたテンプレートに対する読み取り専用アクセス権のみが付与されます。

![](assets/manage_units_7.png)

Geometrixx服の単位はGeometrixxの子単位なので、ユーザーがGeometrixxテンプレートを変更しようとすると、次のメッセージが表示されます。

![](assets/manage_units_8.png)

組織単位は、プロファイルなどの様々な機能へのアクセスを制限できます。 例えば、Geometrixx服ユーザーが **[!UICONTROL Profiles]** 「 」タブで、Clothes 組織単位でプロファイルに完全にアクセスして変更できます。

Geometrixxの組織単位を持つプロファイルは読み取り専用ですが、ユーザーが 1 つのプロファイルを変更しようとすると、次のエラーが表示されます。 **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## プロファイルの分割 {#partitioning-profiles}

>[!IMPORTANT]
>
>組織単位を持たないプロファイルはユーザーがアクセスできないので、プロファイルをインポートする前に、このオプションを追加することをお勧めします。
>
>顧客データベースを既にインポートしている場合は、既にインポート済みのプロファイルに組織単位の値を設定するために、更新が必要です。

組織が異なる各ブランドから連絡を受けたプロファイルを分離する必要がある場合、プロファイルを組織単位で分割できます。

デフォルトでは、組織単位フィールドはプロファイルでは使用できないので、追加する必要があります。

1. 詳細設定メニューのAdobe Campaignロゴから、を選択します。 **管理/開発/カスタムリソース**.
1. 選択 **プロファイル** または、新しいカスタムリソースを作成して、プロファイルを拡張します。 プロファイルの拡張方法について詳しくは、 [ページ](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. 次を確認します。 **アクセス認証管理フィールドの追加** ボックスを使用して、 **プロファイル** 拡張子。

   ![](assets/user_management_9.png)

1. 「**[!UICONTROL Save]**」をクリックします。
1. カスタムリソースを再公開して構造を更新します。 公開プロセスについて詳しくは、 [構造の更新](../../developing/using/updating-the-database-structure.md) 」セクションに入力します。

組織単位フィールドが、 **[!UICONTROL Access authorization]** 」セクションに入力します。

![](assets/user_management_10.png)

**関連トピック**：

* [単位について](../../administration/using/organizational-units.md#about-units)
* [アクセス管理について](../../administration/using/about-access-management.md)
