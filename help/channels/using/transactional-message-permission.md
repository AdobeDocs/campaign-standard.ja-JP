---
title: トランザクションメッセージの権限
description: トランザクションイベントにリンクされた権限について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# トランザクションメッセージの権限 {#transactional-message-permission}

現在、Adobe Campaign Standardでは、Administrator セキュリティグループを持たないユーザーは、イベントにアクセス、作成または公開できず、イベントの設定と公開が必要で、管理者権限を持たないビジネスユーザーに問題が発生しています。

トランザクションメッセージのアクセス制御に対して、次の改善が実装されました。

* 新しい **[!UICONTROL Role]**&#x200B;と呼ばれる **MC ユーザー**&#x200B;を追加しました。これは、管理者以外のユーザーがトランザクションイベントを管理できるようにするためです。 この **MC ユーザー** の役割は、これらのユーザーに、トランザクションイベントおよびメッセージへのアクセス、作成、公開、非公開の機能を付与します。

* 子の配信が **[!UICONTROL Organizational unit]** メッセージテンプレートを作成するユーザーが属するセキュリティグループのセキュリティグループ ( **[!UICONTROL Organizational unit]** の **Message Center エージェント (mcExec)** セキュリティグループ。

* デフォルト **Message Center の実行 (mcExec)** トランザクションメッセージの子配信を収集するキャンペーンが、組織単位に設定されるようになりました。 **すべて** すべてのユーザーが子配信のレポートを表示できるようにします。

を割り当てるには、以下を実行します。 **MC ユーザー** 役割：

1. 新しい **[!UICONTROL Security group]** 既存のものを更新する。 [詳細情報](../../administration/using/managing-groups-and-users.md)。

1. クリック **[!UICONTROL Create element]** ：役割をセキュリティグループに割り当てます。

   ![](assets/event_access_1.png)

1. MC ユーザーを選択 **[!UICONTROL Role]** をクリックし、 **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > MC ユーザーの役割をオペレーターに割り当てる際は、イベントを非公開にする機能を付与するので、注意して作業を進めます。

   ![](assets/event_access_2.png)

1. 設定が完了したら、「 **[!UICONTROL Save]**.

このリンク先のユーザー **[!UICONTROL Security group]** トランザクションイベントとメッセージにアクセス、作成、公開できるようになりました。

次の表に、この機能がアクセス制御に与える影響を示します。

| オブジェクト | この変更の前 | この変更後 |
|:-: | :--: | :-:|
| Message Center Execution (mcExec) キャンペーン | **Message Center の実行 (mcExec)** キャンペーンが **Message Center エージェント (mcExec)** セキュリティグループ。 | **Message Center の実行 (mcExec)** キャンペーンが組織単位に設定されている **すべて** ：すべての子配信をこのキャンペーンに関連付けることができます。</br> すべてのユーザーは、子配信のレポートを表示できますが、配信コンテンツに対する読み取り専用アクセス権のみを持ちます。 |
| 子の配信 | 子の配信は **組織単位** の **Message Center エージェント (mcExec)** セキュリティグループ。 | 子の配信は **組織単位** メッセージテンプレートを作成するユーザーが属するセキュリティグループの名前を指定します。 |
| メッセージテンプレート | メッセージテンプレートは **組織単位** の&#x200B;**Message Center エージェント (mcExec)** セキュリティグループ。 | メッセージテンプレートは **組織単位** メッセージテンプレートを作成するユーザーが属するセキュリティグループの名前を指定します。 |
| トランザクションイベント | 内のユーザーのみ **管理者** セキュリティグループは、イベントを作成および公開できます。 | この **MC ユーザー** の役割を使用すると、ユーザーはイベントを作成および公開できます。 |
| トランザクションメッセージテンプレート | トランザクションメッセージテンプレートが組織単位に設定されている **すべて**. | トランザクションメッセージテンプレートは **組織単位** メッセージテンプレートを作成するユーザーが属するセキュリティグループの名前を指定します。 |