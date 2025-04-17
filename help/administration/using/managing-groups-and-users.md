---
title: グループとユーザーの管理
description: セキュリティグループを作成しユーザーを管理する方法について説明します
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 4b9834ab-0f7c-419e-a210-77a018ba874d
source-git-commit: 52217326ec7f17ab7ce4d058d185b2680681a9c0
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 65%

---

# グループとユーザーの管理{#managing-groups-and-users}

## セキュリティグループについて {#about-security-groups}

>[!IMPORTANT]
>
>**[!UICONTROL Access to the deliverability parameters (Deliverability)]** と **[!UICONTROL Message Center agents (mcExec)]** のセキュリティグループはAdobe内部のみで、どのユーザーにも割り当てないでください。

セキュリティグループとは、組織内で同じ役割および権限を共有するユーザーのセットです。

ユーザーは、常にセキュリティグループにリンクされている必要があります。これにより、特定の役割と組織単位を割り当てることができます。 ユーザーのアクセスを制限する場合、Campaign **[!UICONTROL Standard Users]** グループにユーザーを追加しないでください。このグループは組織単位にリンクされ **[!UICONTROL All]** います。

ロールの詳細については、次のページの表に、ユーザーのロールに応じて使用可能な操作を示します。[Adobe Campaign Standard権限 ](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)。

デフォルトのセキュリティグループは次のとおりです。

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

これらの組み込みセキュリティ グループは読み取り専用で、変更できません。 一連の特定の役割を持つ独自のセキュリティグループを作成するには、以下の節を参照してください。

## セキュリティグループの作成とユーザーの割り当て {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Admin Consoleでは、セキュリティグループはプロファイルと呼ばれます。

標準グループでユーザーを適切に管理できない場合は、独自のセキュリティグループを作成できます。管理者は、Adobe Campaign管理メニューとAdmin Consoleの両方にアクセスできる管理者が管理できます。 Admin Consoleについて詳しくは、この [ ドキュメント ](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html) を参照してください。

ここでは、最初に 2 つの標準グループ（Standard Users と Administrators）をユーザーに割り当てる必要があります。これらのセキュリティグループは、Adobe Campaign 機能の一部を制限します。Standard Users には基本的な Adobe Campaign アクセス権がある一方、Administrators は管理メニューなどにアクセスできます。

Admin Console でセキュリティグループに対しておこなった変更は、ユーザーが Adobe Campaign にログインするとすぐに同期されます。

次に、Geometrixx と Geometrixx Clothes セキュリティグループを作成し、Standard Users と Administrators の組織単位に応じて一部のアクセスが制限されるようにします。

![](assets/ootb_security_group_1.png)

最初に、標準セキュリティグループの 1 つをユーザーに割り当てる必要があります。

1. Admin Consoleで、インスタンスを選択し、「**ユーザー** タブを選択します。

   ![](assets/manage_security_group_2.png)

1. 「**[!UICONTROL Add user]**」ボタンをクリックして、ユーザーのメールアドレスを入力します。
1. 「**[!UICONTROL Assign Products]**」タブで、インスタンスを選択し、ドロップダウンリストから標準の **[!UICONTROL Administrators]** セキュリティグループを選択します。これにより、ユーザーは管理メニューにアクセスし、次のセキュリティグループを作成できます。

   ![](assets/ootb_security_group_2.png)

1. 「**[!UICONTROL Save]**」をクリックし、同じ手順に従って標準の **[!UICONTROL Standard Users]** セキュリティグループを新しいユーザーに割り当てます。

   ![](assets/ootb_security_group_3.png)

ユーザーに役割を割り当てるために標準の **[!UICONTROL Administrators]** セキュリティグループと **[!UICONTROL Standard users]** セキュリティグループに 2 人のユーザーを割り当てると、Administrators ユーザーは **Geometrixx** と **Geometrixx Clothes** の 2 つのセキュリティグループを作成して、標準セキュリティグループに加えて組織単位をユーザーに割り当てることができます。

1. Admin Consoleで、インスタンスを選択し、「**製品** タブを選択します。
1. 「**New Profile**」ボタンをクリックして、**Geometrixx** セキュリティグループを作成します。

   ![](assets/create_security_1.png)

1. 構文「**[!UICONTROL Campaign Standard- instance name - ID of the security group]**」に従って **[!UICONTROL Profile name]** を入力し、「**[!UICONTROL Done]**」をクリックします。

   選択した ID は、Adobe Campaign でセキュリティグループを作成する際に使用されます。

   >[!NOTE]
   >
   >上記の構文が古いインスタンスで動作しない場合は、**[!UICONTROL Campaign - instance name - ID of the security group]** で置き換えてください。

   ![](assets/manage_security_group_1.png)

1. 次に、同じ手順に従って **Geometrixx Clothes** セキュリティグループを作成します。
1. 「**[!UICONTROL Users]**」タブを選択して、セキュリティグループをユーザーに割り当てます。

   ![](assets/manage_security_group_2.png)

1. 以前に作成したユーザーをクリックし、**[!UICONTROL Products]** カテゴリ内の ![](assets/managing_security_group_10.png) アイコンをクリックします。

   「**[!UICONTROL Edit products assigned directly]**」を選択して、新しいセキュリティグループを割り当て始めます。

   ![](assets/manage_security_group_8.png)

1. 「**[!UICONTROL Assign Products]**」タブでインスタンスを選択し、ドロップダウンリストから以前に作成したセキュリティグループ Geometrixx を選択して、Administrators ユーザーに割り当てます。

   「**[!UICONTROL Save]**」をクリックします。

   ![](assets/manage_security_group_3.png)

   ユーザーが複数のグループに属する場合：

   * 異なるグループの役割は累積されます。ここでは、ユーザーは 2 つの異なるグループに属しています。1 つは役割ベースで、もう 1 つは単位ベースです。
   * 単位は使用される階層の中で最高のものです（[組織単位](../../administration/using/organizational-units.md)の節の例を参照）。
   * ユーザーに割り当てられている組織単位が階層内の分岐に並行している場合（つまり、共通の割り当てられた親単位がない場合）、システムはユーザーの組織単位を選択し、ユーザーはシステムが選択した組織単位とその子にアクセスできます。

1. 同じ手順に従って、Geometrixx Clothes セキュリティグループを Standard Users ユーザーに割り当てます。

   ![](assets/manage_security_group_9.png)

これで、新しく作成されたセキュリティグループがAdmin Consoleに作成されました。 セキュリティグループを完全に同期するには、Adobe Campaign でもセキュリティグループを作成する必要があります。

Administrators ユーザーは、組織単位の割り当てに使用する Geometrixx および Geometrixx Clothes セキュリティグループのセットを作成する必要があります。組織単位の作成方法については、[単位の作成と管理](../../administration/using/organizational-units.md#creating-and-managing-units)を参照してください。

1. 左上隅の **Adobe** ロゴをクリックし、「**[!UICONTROL Administration > Users & Security > Security groups]**」を選択します。
1. 新しいセキュリティグループを作成し、**[!UICONTROL Label]** と **[!UICONTROL ID]** を指定します。

   ID は、Admin Consoleで選択したものと同じである必要があります。

1. 「**[!UICONTROL User access]**」フィールドで、組織単位を割り当てます。ここでは、Geometrixx セキュリティグループに **[!UICONTROL All]** 組織単位が割り当てられます。

   >[!NOTE]
   >
   >標準のセキュリティグループをユーザーに割り当てる場合は、組織単位をリセットする必要があります。

   ![](assets/manage_security_group_6.png)

1. 役割をセキュリティグループに割り当てることもできます。その場合、標準の **[!UICONTROL Administrators]** セキュリティグループと **[!UICONTROL Standard users]** セキュリティグループが役割の割り当てに使用されるので、この手順は不要です。
1. 同じ手順で、最後のセキュリティ Geometrixx Clothes を作成し、Geometrixx Clothes の組織単位を割り当てます。

   ![](assets/manage_security_group_7.png)

これで、ユーザーはセキュリティグループに割り当てられ、Adobe Campaign に接続できるようになります。

>[!IMPORTANT]
>
>ユーザーがAdmin Consoleのセキュリティグループから削除された場合、Adobe Campaign セキュリティグループに残り、Adobe Campaignにログインできなくなります。 この場合、ユーザーが機密情報を受け取らないように、Admin Console でユーザーのメールアドレスを削除します。
