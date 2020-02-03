---
title: グループとユーザーの管理
description: セキュリティグループを作成し、ユーザーを管理する方法について説明します。
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
source-git-commit: cc439572afc1a6ab90d4c95576e250af315fd14c

---


# グループとユーザーの管理{#managing-groups-and-users}

## セキュリティグループについて {#about-security-groups}

セキュリティグループは、組織内で同じ役割と権限を共有するユーザーのセットです。

ユーザーは、常にセキュリティグループにリンクされている必要があります。 これにより、特定の役割と組織単位を割り当てることができます。

ロールの詳細については、次のページの表に、ユーザーのロールに従って使用できる様々な操作を示します。 [Adobe Campaign Standardの承認](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

デフォルトのセキュリティグループは次のとおりです。

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

ユーザーがどのセキュリティグループにもリンクされていない場合、Adobe Campaignにアクセスできません。

ユーザーのアクセスを制限する場合は、組織単位にリンクされているので、Campaign Standardユーザーグループにユーザーを追加しな **[!UICONTROL All]**いでください。

>[!NOTE]
>
>デフォルトでは、組織単 **[!UICONTROL All (all)]**位はセキュリティグループに割り**[!UICONTROL Administrators]** 当てられます。 読み取り専用で、変更できません。

## セキュリティグループの作成とユーザーの割り当て {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>管理コンソールでは、セキュリティグループはプロファイルと呼ばれます。

あらかじめ用意されているグループがユーザーを管理するのに十分でない場合は、独自のセキュリティグループを作成できます。 管理者は、Adobe Campaignの管理メニューと管理コンソールの両方にアクセスできる管理者が管理できます。 管理コンソールの詳細については、このドキュメントを参照して [ください](https://helpx.adobe.com/enterprise/managing/user-guide.html)。

ここでは、最初にStandardユーザーとAdministratorの2つの既製のグループをユーザーに割り当てる必要があります。 次のセキュリティグループは、Adobe Campaignの一部の機能を制限します。標準ユーザーはAdobe Campaignに基本的なアクセス権を持っていますが、管理者は管理メニューなどにアクセスできます。

管理コンソールでセキュリティグループに対して行った変更は、ユーザーがAdobe Campaignにログインするとすぐに同期されます。

次に、GeometrixxとGeometrixx Choogesというセキュリティグループを作成し、Standardのユーザーと管理者の組織単位に応じて一部のアクセスを制限します。

![](assets/ootb_security_group_1.png)

最初に、あらかじめ用意されているセキュリティグループの1つをユーザーに割り当てる必要があります。

1. 管理コンソールで、インスタンスを選択し、「ユーザー **** 」タブを選択します。

   ![](assets/manage_security_group_2.png)

1. ボタンをクリ **[!UICONTROL Add user]**ックし、ユーザーの電子メールアドレスを入力します。
1. タブで、 **[!UICONTROL Assign Products]**インスタンスを選択し、ドロップダ**[!UICONTROL Administrators]** ウンリストからあらかじめ用意されているセキュリティグループを選択します。 これにより、ユーザーは管理メニューにアクセスし、次のセキュリティグループを作成できます。

   ![](assets/ootb_security_group_2.png)

1. 同じ手 **[!UICONTROL Save]**順をクリックし、追加設定不要のセキュリ**[!UICONTROL Standard Users]** ティグループを新しいユーザーに割り当てます。

   ![](assets/ootb_security_group_3.png)

ユーザーにロールを割り当てるセキュリティグループに2人のユーザーが関連付けられると、管理者ユーザーは、そのまま使用できるセキュリティグループに加えて、組織単位をユーザーに割り当てる2つのセキュリティグループ **[!UICONTROL Administrators]**Geometrixx**[!UICONTROL Standard users]** とGeometrixx Chooses ******** を作成できます。

1. 管理コンソールで、インスタンスを選択し、「 **Products** 」タブを選択します。
1. 「 **New Profile** 」ボタンをクリックして **Geometrixx** セキュリティグループを作成します。

   ![](assets/create_security_1.png)

1. 次の構文に従 **[!UICONTROL Profile name]**って、を入力します。をク**[!UICONTROL Campaign Standard- instance name - ID of the security group]** リックしま **[!UICONTROL Done]**す。

   選択したIDは、Adobe Campaignでセキュリティグループを作成する際に使用されます。

   >[!NOTE]
   >
   >上記の構文が古いインスタンスで動作しないように見える場合は、を置き換える必要がありま **[!UICONTROL Campaign - instance name - ID of the security group]**す。

   ![](assets/manage_security_group_1.png)

1. 次に、同じ手順に従って **Geometrixx Choosesセキュリティグループを作成します** 。
1. タブを選択して、セキュリティグループをユーザに割り当 **[!UICONTROL Users]**てます。

   ![](assets/manage_security_group_2.png)

1. 以前に作成したユーザーをクリックし、次にカテ ![](assets/managing_security_group_10.png) ゴリ内のアイコンをクリッ **[!UICONTROL Products]**クします。

   新しいセキ **[!UICONTROL Edit products assigned directly]**ュリティグループのユーザーへの割り当てを開始する場合に選択します。

   ![](assets/manage_security_group_8.png)

1. タブで、イ **[!UICONTROL Assign Products]**ンスタンスを選択し、以前に作成したセキュリティグループGeometrixxをドロップダウンリストから選択して、管理者ユーザーに割り当てます。

   クリック **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   ユーザーが複数のグループに属している場合：

   * 様々なグループの役割が累積されます。 ここでは、ユーザーは2つの異なるグループに分かれています。ユニットの役割を果たす1つ。
   * 使用される階層の中で最も高い単位です(「 [Organizational units](../../administration/using/organizational-units.md) 」の例を参照)。
   * ユニットが同じレベルで、階層内の並列分岐にある場合、ユーザーは接続できなくなります。

1. 同じ手順で、Geometrixx ChoogesセキュリティグループをStandardユーザーに割り当てます。

   ![](assets/manage_security_group_9.png)

新しく作成されたセキュリティグループが管理コンソールに作成されます。 完全に同期するには、Adobe Campaignでも作成する必要があります。

管理者ユーザーは、組織単位の割り当てに使用するセキュリティグループのセットを作成する必要があります。GeometrixxおよびGeometrixx Cloases。 組織単位の作成方法については、「単位の作成と管 [理」を参照してください](../../administration/using/organizational-units.md#creating-and-managing-units) 。

1. 左上隅 **[!UICONTROL Adobe Campaign]**のロゴをクリックし、を選択します**[!UICONTROL Administration > Users & Security > Security groups]**。
1. 新しいセキュリティグループを作成し、そのグループとを **[!UICONTROL Label]**指定しま**[!UICONTROL ID]**&#x200B;す。

   このIDは、管理コンソールで選択したIDと同じである必要があります。

1. このフィールド **[!UICONTROL User access]**で、組織単位を割り当てます。 ここで、Geometrixxセキュリティグループに組織単位が割り当**[!UICONTROL All]** てられます。

   ![](assets/manage_security_group_6.png)

1. ロールをセキュリティグループに割り当てることもできます。 この場合、この手順は不要です。これは、あらかじめ用意されているセキュリティグループと、ロールの割り当てに **[!UICONTROL Administrators]**使用さ**[!UICONTROL Standard users]** れるためです。
1. 同じ手順で、最後のセキュリティGeometrixx Choogesを作成し、Geometrixx Choogesの組織単位を割り当てます。

   ![](assets/manage_security_group_7.png)

これで、ユーザーはセキュリティグループに割り当てられ、Adobe Campaignに接続できます。

>[!CAUTION]
>
>ユーザーが管理コンソールでセキュリティグループから削除されると、そのユーザーはAdobe Campaignセキュリティグループの一部となり、Adobe Campaignにログインできなくなります。 この場合、ユーザーが機密情報を受け取らないように、管理コンソールでユーザーの電子メールアドレスを削除します。

