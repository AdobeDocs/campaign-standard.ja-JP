---
title: 役割のリスト
description: ユーザーに割り当て可能なリストのロールを確認します。
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
source-git-commit: 18db1b8cade7d88294ef2609dd4fad95c55fbd37

---


# 役割のリスト{#list-of-roles}

デフォルトでは、Adobe Campaignオファーはロールのセットを管理し、ユーザーおよびユーザーグループに割り当てられた一元的な承認を定義できます。

組織単位と組み合わせて、ロールを使用すると、ユーザーはインターフェイスのフィルタされた表示を提供し、様々な機能へのアクセスを定義できます。

詳しくは、「ロールと権限」の表を参照し [てください](/help/administration/using/assets/acs_rights.pdf)。この表では、選択した承認に応じて、インターフェイスで使用できる機能の詳細を説明しています。

![](assets/user_management_3.png)

役割はメニューから管理で **[!UICONTROL Administration > Users & Security > Roles]** きます。

デフォルトの権限は次のとおりです。

* **[!UICONTROL Administration]**:汎用管理権。
* **[!UICONTROL Datamodel]**:パブリケーションを実行し、カスタムリソースを作成する権限。
* **[!UICONTROL Generic import]**:データに対する汎用インポートを実行する権限。 これを機能させるには、ロールをロールにリン **[!UICONTROL Generic import]** クする必要があ **[!UICONTROL Workflow]** ります。
* **[!UICONTROL Prepare deliveries]**:配信の作成、変更、準備および削除 このロールを持つユーザーは、配信を準備できますが、送信できません。
* **[!UICONTROL Start deliveries]**:配信の作成、変更、準備、送信、削除を行う権限。
* **[!UICONTROL Workflow]**:ワークフロー(開始、停止、一時停止など)の実行を管理する権利 このロールを持つユーザーは、ワークフロー内でも配信を送信できません。

**関連トピック：**

* [アクセス管理について](../../administration/using/about-access-management.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)
