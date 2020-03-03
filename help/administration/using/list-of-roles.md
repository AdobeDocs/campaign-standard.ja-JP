---
title: 役割のリスト
description: ユーザーに割り当て可能なロールのリストを確認します。
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 88d0f67683c5209ccf25d1ceae1ab23b3ac14e06

---


# 役割のリスト{#list-of-roles}

デフォルトでは、Adobe Campaignには一連のロールが用意されており、ユーザーおよびユーザーグループに割り当てられた一元的な承認を定義できます。

組織単位と組み合わせて、ユーザーはインターフェイスをフィルター表示し、様々な機能へのアクセスを定義できます。

詳しくは、「ロールと権限」( [Roles and permissions](/help/administration/using/assets/acs_rights.pdf))テーブルを参照してください。このテーブルには、選択した承認に応じて、インターフェイスで使用できる機能の詳細が表示されます。

![](assets/user_management_3.png)

役割はメニューから管理でき **[!UICONTROL Administration > Users & Security > Roles]** ます。

デフォルトの権限は次のとおりです。

* **[!UICONTROL Administration]**:汎用管理権限。
* **[!UICONTROL Datamodel]**:パブリケーションを実行し、カスタムリソースを作成する権限。
* **[!UICONTROL Export]**: データのエクスポート権限.
* **[!UICONTROL Generic import]**:データに対して汎用インポートを実行する権限。 これを機能させるには、ロールをロールにリン **[!UICONTROL Generic import]** クする必要があ **[!UICONTROL Workflow]** ります。
* **[!UICONTROL Prepare deliveries]**:配信の作成、変更、準備および削除を行う権限。 このロールを持つユーザーは、配信を準備できますが、送信することはできません。
* **[!UICONTROL Start deliveries]**:配信の作成、変更、準備、送信および削除を行う権限。
* **[!UICONTROL Workflow]**:ワークフローの実行を管理する権利（開始、停止、一時停止など）。 このロールを持つユーザーは、ワークフロー内でも配信を送信できません。

>[!IMPORTANT]
>
>、、、 **[!UICONTROL Deliverability]**&#x200B;および **[!UICONTROL Command execution]**&#x200B;役割 **[!UICONTROL Export]**&#x200B;は、 **[!UICONTROL File access]** アドビ **[!UICONTROL Message Center push]** 管理者の内部使用のみを目的としています。 ユーザに与えるべきではありません。

**関連トピック：**

* [アクセス管理について](../../administration/using/about-access-management.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
