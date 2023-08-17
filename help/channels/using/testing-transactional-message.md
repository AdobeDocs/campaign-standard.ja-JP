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
ht-degree: 37%

---

# トランザクションメッセージのテスト {#testing-a-transactional-message}

トランザクションメッセージを公開する前に、メッセージを適切に確認できる特定のテストプロファイルを作成できます。

## 特定のテストプロファイルの定義 {#defining-specific-test-profile}

イベントにリンクするテストプロファイルを定義します。これにより、メッセージをプレビューし、関連する配達確認を送信できます。

1. 次から： [トランザクションメッセージダッシュボード](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)をクリックし、 **[!UICONTROL Create test profile]** 」ボタンをクリックします。

   ![](assets/message-center_test-profile.png)

1. JSON 形式で送信する情報を「**[!UICONTROL Event data used for personalization]**」セクションに指定します。これは、メッセージをプレビューするとき、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >メッセージをエンリッチメントする場合は、別のテーブルに関連する情報 ( 例： **[!UICONTROL Profile]**. 詳しくは、 [イベントのエンリッチメント](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) および [トランザクションメッセージのパーソナライズ](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. 作成後、テストプロファイルはトランザクションメッセージで事前に指定されます。 配達確認のターゲットを確認するには、メッセージの「**[!UICONTROL Test profiles]**」ブロックをクリックします。

   ![](assets/message-center_5.png)

新規テストプロファイルを作成するか、既に「**[!UICONTROL Test profiles]**」メニューにあるテストを使用することもできます。手順は次のとおりです。

1. 次をクリック： **Adobe** ロゴ（左上隅）に、「 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Adobe Analytics の **[!UICONTROL Event]** 「 」セクションで、作成したイベントを選択します。 この例では、「買い物かごの放棄（EVTcartAbandant）」を選択します。
1. JSON 形式で送信する情報を「**[!UICONTROL Event data]**」テキストボックスに指定します。

   ![](assets/message-center_3.png)

1. 変更を保存します。
1. [メッセージにアクセス](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) 作成し、更新されたテストプロファイルを選択したこと

**関連トピック：**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## 配達確認の送信 {#sending-proof}

1 つ以上の特定のテストプロファイルを作成し、トランザクションメッセージを保存したら、配達確認を送信してテストできます。

![](assets/message-center_10.png)

配達確認の送信手順について詳しくは、 [配達確認の送信](../../sending/using/sending-proofs.md) 」セクションに入力します。
