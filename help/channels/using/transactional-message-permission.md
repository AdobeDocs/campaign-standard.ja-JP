---
title: トランザクションメッセージの権限
description: トランザクションイベントにリンクされた権限について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# トランザクションイベントの改善 {#transactional-event-improvements}

>[!AVAILABILITY]
>
>これらの機能は現在、一連の組織でのみ使用できます（使用制限あり）。 詳しくは、アドビ担当者にお問い合わせください。

現在、Adobe Campaign Standardでは、Administrator セキュリティグループを持たないユーザーはトランザクションイベントにアクセスしたり、トランザクションイベントを作成または公開したりできないため、イベントを設定および公開する必要があるが管理者権限が付与されていないビジネスユーザーに問題が発生します。 トランザクションイベントは複製できません。

トランザクションメッセージのアクセス制御に対して次の改善を実装しました。

* 管理者以外のユーザーがトランザクションイベントの設定を管理できるように、**MC ユーザー** という新しい **[!UICONTROL Role]** が追加されました。 **MC ユーザー** の役割を持つユーザーは、トランザクションイベントおよびメッセージに対するアクセス、作成、公開、および非公開の機能を使用できます。

* 実行配信（トランザクションメッセージが編集および公開されるたびに、またはデフォルトで月に 1 回ずつ作成される技術メッセージ）は、**Message Center エージェント（mcExec）** セキュリティグループの **[!UICONTROL Organizational unit]** に制限されるのではなく、イベントを作成するユーザーが属するセキュリティグループの **[!UICONTROL Organizational unit]** に設定されるようになりました。

* **管理者** は、公開済みのトランザクションイベントを、イベントを作成したユーザーと同じ **組織単位** 階層にある場合、**MC ユーザー** の役割を持つユーザーと複製できるようになりました。

## MC ユーザーの役割の割り当て {#assign-role}

**MC ユーザー** の役割をセキュリティ グループに割り当てるには：

1. 新しい **[!UICONTROL Security group]** を作成するか、既存のものを更新します。 [詳細情報](../../administration/using/managing-groups-and-users.md)。

1. 「**[!UICONTROL Create element]**」をクリックして、役割をセキュリティ・グループに割り当てます。

   ![](assets/event_access_1.png)

1. MC user **[!UICONTROL Role]** を選択し、「**[!UICONTROL Confirm]**」をクリックします。

   >[!IMPORTANT]
   >
   > オペレーターに MC ユーザーの役割を割り当てる場合は、イベントを非公開にする機能が付与されるので、注意して作業を進めてください。

   ![](assets/event_access_2.png)

1. 設定が完了したら、「**[!UICONTROL Save]**」をクリックします。

この **[!UICONTROL Security group]** にリンクされたユーザーは、トランザクションイベントおよびメッセージにアクセス、作成および公開できるようになりました。

## MC ユーザー・セキュリティ・グループの割り当て {#assign-group}

1. Admin Consoleで、「**製品**」タブを選択します。

1. 「**Adobe Campaign Standard」を選択してから** インスタンスを選択します。

1. **製品プロファイル** リストから、**MC ユーザー** グループを選択します。

1. 「**ユーザーを追加**」をクリックし、この製品プロファイルに追加するプロファイルの名前、ユーザーグループまたはメールアドレスを入力します。

1. 追加したら、「**保存**」をクリックします。

この **[!UICONTROL Security group]** に追加されたユーザーは、トランザクションイベントおよびメッセージにアクセスし、作成と公開ができるようになりました。

## トランザクションイベントの複製 {#duplicate-transactional-events}

**管理者** セキュリティグループを持つユーザーは <!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> イベントが **公開** された場合に、イベント設定を複製できるようになりました。

さらに、**MC ユーザー** の役割を持つ管理者以外のユーザーもイベント設定にアクセスできるようになりましたが、複製する権限は所属する **組織単位** によって決まります。 現在のユーザーとイベントを作成したユーザーが同じ組織単位階層に属している場合は、複製が許可されます。

例えば、「フランスの営業」組織単位に属するユーザーがイベント設定を作成する場合は、次のようになります。

* 組織単位が「Paris Sales」である別のユーザーは、このイベントを複製できます。「Paris Sales」は、「France Sales」組織単位の一部であるためです。

* ただし、「サンフランシスコの売上」という組織単位を持つユーザーは使用できません。「サンフランシスコの売上」は、「フランスの売上」組織単位とは別の「US の売上」組織単位に属しているためです。

イベント設定を複製するには、次の手順に従います。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Marketing plans]&#x200B;**/**&#x200B;[!UICONTROL Transactional messages]&#x200B;**/**&#x200B;[!UICONTROL Event configuration]&#x200B;**を選択します。**

1. 選択した公開済みイベント設定にポインタを合わせて、「**[!UICONTROL Duplicate element]**」ボタンを選択します。

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >公開されていないイベント設定は複製できません。 [詳細情報](publishing-transactional-event.md)

1. 重複したイベントが自動的に表示されます。 元のイベントに対して定義した設定と同じ設定が含まれていますが、ステータスは **[!UICONTROL Draft]** です。

   ![](assets/message-center_duplicated-draft-event.png)

1. 対応するトランザクションメッセージが自動的に作成されます。 アクセスするには、**[!UICONTROL Transactional messages]**/**[!UICONTROL Transactional messages]** に移動します。

   ![](assets/message-center_duplicated-message.png)

1. 新しく複製したメッセージを開きます。 含まれるデザインは元のメッセージに対して定義したものと同じですが、元のトランザクションメッセージが公開された場合でも、ステータスは **[!UICONTROL Draft]** になります。

   ![](assets/message-center_duplicated-draft-message.png)

1. このメッセージを編集してパーソナライズできるようになりました。 [&#x200B; トランザクションメッセージの編集 &#x200B;](../../channels/using/editing-transactional-message.md) を参照してください。

## 影響 {#impacts}

次の表に、これらの改善の影響の概要を示します。

| オブジェクト | この変更の前 | この変更後 |
|:-: | :--: | :-:|
| トランザクションイベント | イベントを作成および公開できるのは、**管理者** セキュリティグループ内のユーザーのみです。 | **MC ユーザー** の役割を持つユーザーは、イベントを作成および公開できます。 |
| トランザクションメッセージ | トランザクションメッセージは、**Message Center エージェント（mcExec）** セキュリティグループの **組織単位** に設定されます。 | トランザクションメッセージは、トランザクションイベント/メッセージを作成するユーザーが属するセキュリティグループの **組織単位** に設定されます。 |
| 実行配信 | 実行配信は、**Message Center エージェント（mcExec）** セキュリティグループの **組織単位** に設定されます。 | 実行配信は、トランザクションイベント/メッセージを作成するユーザーが属するセキュリティグループの **組織単位** に設定されます。 |
| 公開済みトランザクションイベント | 複製はどのユーザーにも不可能です。 | <ul><li>**管理者** セキュリティグループを持つユーザーは、公開済みイベントを複製できます。</li> <li>**MC ユーザー** の役割を持つユーザーは、イベントを作成したユーザーと同じ **組織単位** 階層にある場合、公開済みイベントを複製できます。</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->