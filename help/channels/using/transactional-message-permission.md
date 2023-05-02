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
ht-degree: 0%

---

# トランザクションイベントの改善 {#transactional-event-improvements}

>[!AVAILABILITY]
>
>これらの機能は、現在、一連の組織（限定提供）でのみ使用できます。 詳しくは、Adobe担当者にお問い合わせください。

現在、Adobe Campaign Standardでは、Administrator セキュリティグループを持たないユーザーは、トランザクションイベントにアクセス、作成または公開できず、イベントの設定と公開を必要とするが管理者権限を持たないビジネスユーザーに問題が発生しています。 また、トランザクションイベントを複製することはできません。

トランザクションメッセージのアクセス制御に対して、次の改善が実装されました。

* 新しい **[!UICONTROL Role]**&#x200B;と呼ばれる **MC ユーザー**&#x200B;を追加しました。これは、管理者以外のユーザーがトランザクションイベントの設定を管理できるようにするためです。 この **MC ユーザー** の役割は、これらのユーザーに、トランザクションイベントおよびメッセージへのアクセス、作成、公開、非公開の機能を付与します。

* 実行配信（つまり、トランザクションメッセージが再編集されて公開されるたびに、またはデフォルトで月に 1 回作成されるテクニカルメッセージ）が、 **[!UICONTROL Organizational unit]** （イベントを作成するユーザーが属するセキュリティグループ） **[!UICONTROL Organizational unit]** の **Message Center エージェント (mcExec)** セキュリティグループ。

* **管理者** 公開済みトランザクションイベントと、 **MC ユーザー** 同じ役割であれば、 **組織単位** 階層を、イベントを作成したユーザーとして追加しました。

## MC ユーザーの役割を割り当てる {#assign-role}

を割り当てるには、以下を実行します。 **MC ユーザー** の役割をセキュリティグループに割り当てます。

1. 新しい **[!UICONTROL Security group]** 既存のものを更新する。 [詳細情報](../../administration/using/managing-groups-and-users.md)

1. クリック **[!UICONTROL Create element]** ：役割をセキュリティグループに割り当てます。

   ![](assets/event_access_1.png)

1. MC ユーザーを選択 **[!UICONTROL Role]** をクリックし、 **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > MC ユーザーの役割をオペレーターに割り当てる際は、イベントを非公開にする機能を付与するので、注意して作業を進めます。

   ![](assets/event_access_2.png)

1. 設定が完了したら、「 **[!UICONTROL Save]**.

このリンク先のユーザー **[!UICONTROL Security group]** トランザクションイベントとメッセージにアクセスし、作成して公開できるようになりました。

## MC ユーザーセキュリティグループを割り当てる {#assign-group}

1. Admin Consoleで、 **製品** タブをクリックします。

1. 選択 **Adobe Campaign Standard** 次に、インスタンスを選択します。

1. 次の **製品プロファイル** リストで、 **MC ユーザー** グループ化します。

1. クリック **ユーザーを追加** をクリックし、この製品プロファイルに追加するプロファイルの名前、ユーザーグループ、または電子メールアドレスを入力します。

1. 追加したら、「 **保存**.

このに追加されたユーザー **[!UICONTROL Security group]** トランザクションイベントとメッセージにアクセスし、作成して公開できるようになりました。

## 重複トランザクションイベント {#duplicate-transactional-events}

ユーザーが **管理者** セキュリティグループ<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> イベントが **公開済み**.

さらに、管理者以外のユーザーが **MC ユーザー** ロールはイベント設定にアクセスできるようになりましたが、複製する権限は **組織単位** 彼らは属している。 現在のユーザーとイベントを作成したユーザーが同じ組織単位階層に属している場合は、重複が許可されます。

例えば、「フランス販売」組織単位に属するユーザーがイベント設定を作成するとします。

* 「パリの販売」は「フランスの販売」組織単位の一部なので、組織単位が「パリの販売」である別のユーザーは、このイベントを複製できます。

* ただし、「San Francisco Sales」は「France Sales」組織単位とは別の「US Sales」組織単位に属するので、組織単位が「San Francisco Sales」のユーザーはこの操作を実行できません。

イベント設定を複製するには、次の手順に従います。

1. 次をクリック： **Adobe** ロゴ（左上隅）に移動し、「 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. 任意の公開済みイベント設定にマウスポインターを置いて、「 **[!UICONTROL Duplicate element]** 」ボタンをクリックします。

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >公開されていないイベント設定は複製できません。 [詳細情報](publishing-transactional-event.md)

1. 複製されたイベントが自動的に表示されます。 元のイベントに対して定義したのと同じ設定が含まれますが、 **[!UICONTROL Draft]** ステータス。

   ![](assets/message-center_duplicated-draft-event.png)

1. 対応するトランザクションメッセージが自動的に作成されます。 アクセスするには、に移動します。 **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. 新しく複製されたメッセージを開きます。 元のメッセージに対して定義したのと同じデザインが含まれていますが、 **[!UICONTROL Draft]** ステータス（元のトランザクションメッセージが公開された場合も含む）

   ![](assets/message-center_duplicated-draft-message.png)

1. これで、このメッセージを編集し、パーソナライズできます。 詳しくは、 [トランザクションメッセージの編集](../../channels/using/editing-transactional-message.md).

## 影響 {#impacts}

次の表に、これらの改善の影響を示します。

| オブジェクト | この変更の前 | この変更後 |
|:-: | :--: | :-:|
| トランザクションイベント | 内のユーザーのみ **管理者** セキュリティグループは、イベントを作成および公開できます。 | この **MC ユーザー** の役割を使用すると、ユーザーはイベントを作成および公開できます。 |
| トランザクションメッセージ | トランザクションメッセージは **組織単位** の **Message Center エージェント (mcExec)** セキュリティグループ。 | トランザクションメッセージは **組織単位** トランザクションイベント/メッセージを作成するユーザーが属するセキュリティグループの |
| 実行配信 | 実行配信は **組織単位** の **Message Center エージェント (mcExec)** セキュリティグループ。 | 実行配信は **組織単位** トランザクションイベント/メッセージを作成するユーザーが属するセキュリティグループの |
| 公開済みトランザクションイベント | どのユーザーに対しても複製はできません。 | <ul><li>を持つ **管理者** セキュリティグループは公開済みイベントを複製できます。</li> <li>を持つ **MC ユーザー** ロールは、同じになっていれば、公開されたイベントを複製できます **組織単位** 階層を、イベントを作成したユーザーとして追加しました。</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->