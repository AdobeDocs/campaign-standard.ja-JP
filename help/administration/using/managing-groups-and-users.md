---
title: グループとユーザーの管理
description: セキュリティグループの作成方法とユーザーの管理方法を説明します。
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 09a6e062be32b78fda6b0eb83a6d11ac249b3168
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 1%

---


# グループとユーザーの管理{#managing-groups-and-users}

## セキュリティグループについて {#about-security-groups}

セキュリティグループとは、組織内で同じ役割および権限を共有するユーザーのセットです。

ユーザーは常にセキュリティグループにリンクされている必要があります。 これにより、特定の役割や組織単位を割り当てることができます。

ロールの詳細については、次のページの表に、ユーザーのロールに応じて使用できる様々な操作を示します。 [Adobe Campaign Standardの承認](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

デフォルトのセキュリティグループは次のとおりです。

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

ユーザーがどのセキュリティグループにもリンクされていない場合、Adobe Campaignにアクセスできません。

ユーザーのアクセスを制限するには、Campaign Standardをユーザーグループに追加しないでください。ユーザーは **[!UICONTROL All]** 組織単位にリンクされます。

>[!NOTE]
>
>既定では、 **[!UICONTROL All (all)]** 組織単位は **[!UICONTROL Administrators]** セキュリティグループに割り当てられます。 読み取り専用で、変更できません。

## セキュリティグループの作成とユーザーの割り当て {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>管理コンソールでは、セキュリティグループはプロファイルと呼ばれます。

既製のグループでユーザーを管理するのに十分でない場合は、独自のセキュリティグループを作成できます。 管理者は、Adobe Campaign管理メニューと管理コンソールの両方にアクセスできる管理者が管理できます。 管理コンソールについて詳しくは、この [ドキュメントを参照してください](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html)。

ここでは、最初に、StandardユーザーとAdministratorの2つの既製のグループをユーザーに割り当てる必要があります。 次のセキュリティグループは、Adobe Campaign機能の一部を制限します。 「標準ユーザー」では基本的なAdobe Campaignアクセス権を持ちますが、「管理者」では管理メニューなどにアクセスできます。

管理コンソールでセキュリティグループに対して行った変更は、Adobe Campaignがユーザーにログインするとすぐに同期されます。

次に、Standardのユーザーと管理者の組織単位に応じて一部のアクセスを制限するセキュリティグループGeometrixxとGeometrixx衣類のセットを作成します。

![](assets/ootb_security_group_1.png)

最初に、あらかじめ用意されているセキュリティグループの1つをユーザーに割り当てる必要があります。

1. 管理コンソールで、インスタンスを選択し、「 **ユーザー** 」タブをクリックします。

   ![](assets/manage_security_group_2.png)

1. ボタンをクリックし **[!UICONTROL Add user]** て、ユーザーの電子メールアドレスを入力します。
1. タブで、インスタンスを選択し、ドロップダウン **[!UICONTROL Assign Products]** リストから **[!UICONTROL Administrators]** そのまま使用できるセキュリティグループを選択します。 これにより、ユーザーは管理メニューにアクセスし、次のセキュリティグループを作成できます。

   ![](assets/ootb_security_group_2.png)

1. をクリック **[!UICONTROL Save]** し、同じ手順に従って、あらかじめ用意され **[!UICONTROL Standard Users]** ているセキュリティグループを新しいユーザーに割り当てます。

   ![](assets/ootb_security_group_3.png)

ユーザーにロールを割り当て **[!UICONTROL Administrators]** るセキュリティグループと既製のセキュリティグループに2人のユーザーを関連付けると、管理者ユーザーは、既製のセキュリティグループに加えて、組織単位をユーザーに割り当てる2つのセキュリティグループ **[!UICONTROL Standard users]** Geometrixx **と** Geometrixx服 **** を作成できます。

1. 管理コンソールで、インスタンスを選択し、「 **製品** 」タブをクリックします。
1. 「 **新規プロファイル** 」ボタンをクリックして、 **Geometrixx** ・セキュリティ・グループを作成します。

   ![](assets/create_security_1.png)

1. 次の構文 **[!UICONTROL Profile name]** に従って、を入力します。 **[!UICONTROL Campaign Standard- instance name - ID of the security group]** をクリックし **[!UICONTROL Done]**&#x200B;ます。

   選択したIDは、Adobe Campaignでセキュリティグループを作成する際に使用されます。

   >[!NOTE]
   >
   >上記の構文が古いインスタンスで動作しないように見える場合は、を置き換える必要があり **[!UICONTROL Campaign - instance name - ID of the security group]**&#x200B;ます。

   ![](assets/manage_security_group_1.png)

1. 次に、同じ手順に従って、 **Geometrixx衣料** (Data Cloases)セキュリティグループを作成します。
1. タブを選択して、セキュリティグループをユーザーに割り当て **[!UICONTROL Users]** ます。

   ![](assets/manage_security_group_2.png)

1. 以前に作成したユーザーをクリックし、 ![](assets/managing_security_group_10.png) カテゴリ内の **[!UICONTROL Products]** アイコンをクリックします。

   開始 **[!UICONTROL Edit products assigned directly]** に新しいセキュリティグループを割り当てる場合に選択します。

   ![](assets/manage_security_group_8.png)

1. タブで、インスタンスを選択し、次に、ドロップダウンリストから以前に作成したセキュリティグループGeometrixxを選択して、管理者ユーザーに割り当てます。 **[!UICONTROL Assign Products]**

   クリック **[!UICONTROL Save]** .

   ![](assets/manage_security_group_3.png)

   ユーザーが複数のグループに属する場合：

   * 様々なグループの役割が累積されます。 ここでは、ユーザーは2つの異なるグループに分けられます。 ユニットの役割を果たす1つ。
   * 使用される階層の中で最も高い単位です(「 [組織単位](../../administration/using/organizational-units.md) 」の項の例を参照)。
   * ユニットのレベルが同じで、階層内の並列分岐にある場合、ユーザーは接続できなくなります。

1. 同じ手順に従って、StandardGeometrixxにData Choosesセキュリティグループを割り当てます。

   ![](assets/manage_security_group_9.png)

新しく作成されたセキュリティグループが管理コンソールに作成されます。 完全に同期するには、Adobe Campaignで作成する必要もあります。

管理者ユーザーは、組織単位の割り当てに使用するセキュリティグループのセットを作成する必要があります。 GeometrixxとGeometrixxの服 組織単位の作成方法については、「ユニットの [作成と管理](../../administration/using/organizational-units.md#creating-and-managing-units) 」を参照してください。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、を選択し **[!UICONTROL Administration > Users & Security > Security groups]**&#x200B;ます。
1. 新しいセキュリティグループを作成し、そのグループ **[!UICONTROL Label]** とを指定し **[!UICONTROL ID]**&#x200B;ます。

   このIDは、管理コンソールで選択したIDと同じである必要があります。

1. この **[!UICONTROL User access]** フィールドで、組織単位を割り当てます。 ここでは、Geometrixxセキュリティグループに **[!UICONTROL All]** 組織単位が割り当てられます。

   >[!NOTE]
   >
   >ユーザーに標準搭載のセキュリティグループを割り当てる場合は、組織単位をリセットする必要があります。

   ![](assets/manage_security_group_6.png)

1. ロールをセキュリティグループに割り当てることもできます。 この場合、この手順は不要です。これは、あらかじめ用意されているセキュリティグループ **[!UICONTROL Administrators]** と、ロールの割り当て **[!UICONTROL Standard users]** に使用されるためです。
1. 同じ手順に従って、最後のセキュリティGeometrixx衣料品を作成し、Geometrixx衣料品の組織単位を割り当てます。

   ![](assets/manage_security_group_7.png)

ユーザーはセキュリティグループに割り当てられ、Adobe Campaignに接続できるようになりました。

>[!IMPORTANT]
>
>管理コンソールでセキュリティグループから削除されたユーザーは、Adobe Campaignセキュリティグループに引き続き属し、Adobe Campaignにログインできなくなります。 この場合、ユーザーが機密情報を受け取らないように、管理コンソールでユーザーの電子メールアドレスを削除します。

