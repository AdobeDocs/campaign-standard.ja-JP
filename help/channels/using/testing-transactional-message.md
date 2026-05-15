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
TQID: https://experienceleague.adobe.com/13JYxn86ZNf9mBAnNCLGCW4M80IvRvkYvnEWmkqGnAU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 31%

---

# トランザクションメッセージのテスト {#testing-a-transactional-message}

トランザクションメッセージを公開する前に、メッセージを適切にチェックできる特定のテストプロファイルを作成できます。

## 特定のテストプロファイルの定義 {#defining-specific-test-profile}

イベントにリンクされるテストプロファイルを定義します。これにより、メッセージをプレビューし、関連するプルーフを送信できます。

1. [&#x200B; トランザクションメッセージダッシュボード &#x200B;](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)で、**[!UICONTROL Create test profile]** ボタンをクリックします。

   ![](assets/message-center_test-profile.png)

1. JSON 形式で送信する情報を「**[!UICONTROL Event data used for personalization]**」セクションに指定します。 これは、メッセージをプレビューするとき、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >メッセージを強化した場合は、**[!UICONTROL Profile]**&#x200B;など、別のテーブルに関連する情報を入力することもできます。 [&#x200B; イベントの強化](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)および[&#x200B; トランザクションメッセージのパーソナライズ &#x200B;](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)を参照してください。

1. 作成したテストプロファイルは、トランザクションメッセージで事前に指定されます。 配達確認のターゲットを確認するには、メッセージの「**[!UICONTROL Test profiles]**」ブロックをクリックします。

   ![](assets/message-center_5.png)

新しいテストプロファイルを作成するか、**[!UICONTROL Test profiles]** メニューに既に存在するテストプロファイルを使用することもできます。 手順は次のとおりです。

1. 左上隅の&#x200B;**Adobe** ロゴをクリックし、**[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**&#x200B;を選択します。
1. **[!UICONTROL Event]** セクションで、作成したばかりのイベントを選択します。 この例では、「買い物かごの放棄（EVTcartAbandant）」を選択します。
1. JSON 形式で送信する情報を「**[!UICONTROL Event data]**」テキストボックスに指定します。

   ![](assets/message-center_3.png)

1. 変更内容を保存します。
1. [作成したメッセージ &#x200B;](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)にアクセスし、更新されたテストプロファイルを選択します。

**関連トピック：**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## 配達確認の送信 {#sending-proof}

1つ以上の特定のテストプロファイルを作成し、トランザクションメッセージを保存したら、プルーフを送信してテストできます。

![](assets/message-center_10.png)

プルーフを送信する手順について詳しくは、[&#x200B; プルーフの送信](../../sending/using/sending-proofs.md) セクションを参照してください。
