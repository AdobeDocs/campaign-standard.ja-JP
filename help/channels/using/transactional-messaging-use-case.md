---
solution: Campaign Standard
product: campaign
title: トランザクションメッセージの使用例
description: Adobe Campaignトランザクションメッセージング機能のエンドツーエンドの例を見つけ出します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 2%

---


# トランザクションメッセージングの使用例{#transactional-messaging-use-case}

この例では、Adobe Campaignトランザクションメッセージング機能を使用して、Webサイトでの各購入後に確認電子メールを送信し、CRM IDを介して顧客を特定します。

前提条件は次のとおりです。

* **[!UICONTROL Profile]**&#x200B;リソースが、CRM IDに対応する新しいフィールドで拡張されていることを確認します。

* 購入に対応するカスタムリソースを作成して発行し、**[!UICONTROL Profile]**&#x200B;リソースにリンクします。 この方法を使用すると、このリソースから情報を取得して、メッセージの内容を拡張できます。

リソースの拡張、作成、および公開について詳しくは、[このセクション](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

この使用例を実装する主な手順は次のとおりです。

>[!NOTE]
>
>トランザクションメッセージングの一般的なプロセスのグラフィカル表現については、[このスキーマ](../../channels/using/getting-started-with-transactional-msg.md#key-steps)を参照してください。

## 手順1 -イベント設定を作成して公開する{#create-event-configuration}

1. **[!UICONTROL Email]**&#x200B;チャネルを使用して新しいイベントを作成します。 詳しくは、[イベントの作成](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照してください。

1. **[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを選択して、[プロファイルベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)を作成します。

1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。 この例では、「CRM ID」フィールドと「製品識別子」フィールドを追加します。 「[イベント属性の定義](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)」を参照してください。

   ![](assets/message-center_usecase1.png)

1. メッセージ内容を顧客の購入に関する情報と共に拡張するには、**[!UICONTROL Purchase]**&#x200B;リソースをターゲットとするエンリッチメントを作成します。 [イベントを豊かにする](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を参照してください。

   ![](assets/message-center_usecase2.png)

1. 以前にイベントに追加した「Product identifier」フィールドと、**[!UICONTROL Purchase]**&#x200B;リソースの対応するフィールドとの結合条件を作成します。

   ![](assets/message-center_usecase3.png)

1. プロファイルベースのイベントでは必須なので、**[!UICONTROL Profile]**&#x200B;リソースをターゲットにしたエンリッチメントも作成する必要があります。

1. 以前にメッセージに追加した「CRM ID」フィールドと、拡張した&#x200B;**[!UICONTROL Profile]**&#x200B;リソースの対応するフィールドとの間に結合条件を作成します。<!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. 「**[!UICONTROL Targeting enrichment]**」セクションで、**[!UICONTROL Profile]**&#x200B;リソース上のエンリッチメントを選択します。このリソースは、配信の実行中にメッセージターゲットとして使用されます。

   ![](assets/message-center_usecase5.png)

1. イベントをプレビューして公開します。 詳しくは、[イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照してください。

## 手順2 -トランザクションメッセージを編集して公開する{#create-transactional-message}

1. イベントの公開時に自動的に作成されたトランザクションメッセージに移動します。 [トランザクションメッセージへのアクセス](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)を参照してください。

1. メッセージを編集してパーソナライズします。 「[プロファイルトランザクションメッセージの編集](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message)」を参照してください。

1. **[!UICONTROL Profile]**&#x200B;リソースに追加した「CRM ID」フィールドとの調整により、すべてのプロファイル情報に直接アクセスして、メッセージを[パーソナライズ](../../designing/using/personalization.md#inserting-a-personalization-field)できます。

   ![](assets/message-center_usecase6.png)

1. 「製品ID」フィールドとの調整により、**[!UICONTROL Purchase]**&#x200B;リソースから任意のフィールドを追加することで、メッセージの内容を顧客の購入に関する情報と共に拡張できます。

   ![](assets/message-center_usecase7.png)

   これを行うには、コンテキストツールバーから&#x200B;**[!UICONTROL Insert personalization field]**&#x200B;を選択します。 **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**&#x200B;ノードから、**[!UICONTROL Purchase]**&#x200B;カスタムリソースに対応するノードを開き、任意のフィールドを選択します。

1. 特定のテストプロファイルを使用してメッセージをテストできます。 [トランザクションメッセージのテスト](../../channels/using/testing-transactional-message.md#testing-a-transactional-message)を参照してください。

1. コンテンツの準備が整ったら、変更を保存し、メッセージを発行します。 [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

## 手順3 -イベントトリガー{#integrate-event-trigger}を統合する

イベントをWebサイトに統合します。 [イベントトリガーの統合](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)を参照してください。

## 手順4 — メッセージ配信{#message-delivery}

これらの手順がすべて完了すると、顧客がWebサイトで製品を購入するとすぐに、購入に関する情報を含むパーソナライズされた確認電子メールが届きます。