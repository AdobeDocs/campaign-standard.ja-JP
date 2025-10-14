---
title: トランザクションメッセージのテスト
description: Adobe Campaignでトランザクションメッセージをテストする方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 31%

---

# トランザクションメッセージのテスト {#testing-a-transactional-message}

トランザクションメッセージを公開する前に、特定のテストプロファイルを作成すると、メッセージを適切に確認できます。

## 特定のテストプロファイルの定義 {#defining-specific-test-profile}

イベントにリンクされるテストプロファイルを定義します。これにより、メッセージをプレビューし、関連する配達確認を送信できます。

1. [&#x200B; トランザクションメッセージダッシュボード &#x200B;](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) で、「**[!UICONTROL Create test profile]**」ボタンをクリックします。

   ![](assets/message-center_test-profile.png)

1. JSON 形式で送信する情報を「**[!UICONTROL Event data used for personalization]**」セクションに指定します。これは、メッセージをプレビューするとき、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >メッセージをエンリッチメントした場合は、**[!UICONTROL Profile]** など、別のテーブルに関する情報も入力できます。 [&#x200B; イベントの機能強化 &#x200B;](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) および [&#x200B; トランザクションメッセージのパーソナライズ &#x200B;](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message) を参照してください。

1. 作成したテストプロファイルは、トランザクションメッセージで事前に指定されます。 配達確認のターゲットを確認するには、メッセージの「**[!UICONTROL Test profiles]**」ブロックをクリックします。

   ![](assets/message-center_5.png)

また、新しいテストプロファイルを作成したり、**[!UICONTROL Test profiles]** メニューに既に存在するテストプロファイルを使用したりすることもできます。 手順は次のとおりです。

1. 左上隅の **0&rbrace;Adobe&rbrace; ロゴをクリックし、**&#x200B;[!UICONTROL Profiles & audiences]&#x200B;**/**&#x200B;[!UICONTROL Test profiles]&#x200B;**を選択します。**
1. **[!UICONTROL Event]** セクションで、作成したばかりのイベントを選択します。 この例では、「買い物かごの放棄（EVTcartAbandant）」を選択します。
1. JSON 形式で送信する情報を「**[!UICONTROL Event data]**」テキストボックスに指定します。

   ![](assets/message-center_3.png)

1. 変更を保存します。
1. 作成した [&#x200B; メッセージにアクセス &#x200B;](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) し、更新されたテストプロファイルを選択します。

**関連トピック：**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## 配達確認の送信 {#sending-proof}

1 つ以上の特定のテストプロファイルを作成し、トランザクションメッセージを保存したら、配達確認を送信してテストできます。

![](assets/message-center_10.png)

配達確認の送信手順について詳しくは、[&#x200B; 配達確認の送信 &#x200B;](../../sending/using/sending-proofs.md) の節を参照してください。
