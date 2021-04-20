---
solution: Campaign Standard
product: campaign
title: トランザクションメッセージのテスト
description: Adobe Campaignでトランザクションメッセージをテストする方法を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 41%

---


# トランザクションメッセージのテスト{#testing-a-transactional-message}

トランザクションメッセージを公開する前に、メッセージを正しく確認できる特定のテストプロファイルを作成できます。

## 特定のテストプロファイルの定義{#defining-specific-test-profile}

メッセージをプレビューし、関連配達確認を送信できるように、イベントにリンクするテストプロファイルを定義します。

1. [トランザクションメッセージダッシュボード](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)から、**[!UICONTROL Create test profile]**&#x200B;ボタンをクリックします。

   ![](assets/message-center_test-profile.png)

1. JSON 形式で送信する情報を「**[!UICONTROL Event data used for personalization]**」セクションに指定します。これは、メッセージをプレビューするとき、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >メッセージを強化した場合は、**[!UICONTROL Profile]**&#x200B;など、別のテーブルに関する情報を入力することもできます。 「[イベントの強化](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)」および「[トランザクションメッセージのパーソナライズ](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)」を参照してください。

1. 作成したテストプロファイルは、トランザクションメッセージで事前に指定されます。 配達確認のターゲットを確認するには、メッセージの「**[!UICONTROL Test profiles]**」ブロックをクリックします。

   ![](assets/message-center_5.png)

新規テストプロファイルを作成するか、既に「**[!UICONTROL Test profiles]**」メニューにあるテストを使用することもできます。手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Profiles & audiences]**／**[!UICONTROL Test profiles]** を選択します。
1. **[!UICONTROL Event]**&#x200B;セクションで、先ほど作成したイベントを選択します。 この例では、「買い物かごの放棄（EVTcartAbandant）」を選択します。
1. JSON 形式で送信する情報を「**[!UICONTROL Event data]**」テキストボックスに指定します。

   ![](assets/message-center_3.png)

1. 変更を保存します。
1. [作成した](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) メッセージにアクセスし、更新したテストプロファイルを選択します。

**関連トピック：**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## 配達確認の送信 {#sending-proof}

1つ以上の特定のテストプロファイルを作成し、トランザクションメッセージを保存したら、配達確認を送信してテストできます。

![](assets/message-center_10.png)

配達確認を送信する手順については、「[配達確認の送信](../../sending/using/sending-proofs.md)」の節を参照してください。
