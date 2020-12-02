---
title: トランザクションメッセージの設定
description: トランザクションメッセージを設定する方法について説明します。
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---


# トランザクションメッセージングの使用例{#transactional-messaging-use-case}

この例では、Adobe Campaignトランザクションメッセージング機能を使用して、Webサイトでの各購入後に確認電子メールを送信し、CRM IDを介して顧客を特定します。

前提条件は次のとおりです。

* **[!UICONTROL Profile]**&#x200B;リソースが、CRM IDに対応する新しいフィールドで拡張されていることを確認します。

* 購入に対応するカスタムリソースを作成して発行し、**[!UICONTROL Profile]**&#x200B;リソースにリンクします。 この方法を使用すると、このリソースから情報を取得して、メッセージの内容を拡張できます。

* リソースの拡張、作成、および公開について詳しくは、[このセクション](../../developing/using/key-steps-to-add-a-resource.md)を参照してください。

この使用例を実装する主な手順は次のとおりです。 トランザクションメッセージングの一般的なプロセスのグラフィック表示については、[このグラフ](../../channels/using/getting-started-with-transactional-msg.md#key-steps)を参照してください。

## 手順1 -イベント設定を作成して公開する{#create-event-configuration}

1. **[!UICONTROL Email]**&#x200B;チャネルを使用して新しいイベントを作成します。 [イベントの作成](../../channels/using/configuring-transactional-event.md#creating-an-event)を参照

1. **[!UICONTROL Profile]**&#x200B;ターゲティングディメンションを選択して、[プロファイルベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)を作成します。

1. トランザクションメッセージをパーソナライズするために使用できる属性を定義します。 この例では、「CRM ID」フィールドと「製品識別子」フィールドを追加します。 「[イベント属性の定義](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)」を参照してください。

   ![](assets/message-center_usecase1.png)

1. メッセージ内容を顧客の購入に関する情報と共に拡張するには、**[!UICONTROL Purchase]**&#x200B;リソースをターゲットとするエンリッチメントを作成します。 [イベントを豊かにする](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を参照してください。

   ![](assets/message-center_usecase2.png)

1. 以前にメッセージに追加した「製品識別子」フィールドと、**[!UICONTROL Purchase]**&#x200B;リソースの対応するフィールドとの結合条件を作成します。

   ![](assets/message-center_usecase3.png)

1. イベントをプレビューして公開します。 詳しくは、[イベントのプレビューと公開](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)を参照してください。

## 手順2 -トランザクションメッセージを編集して公開する{#create-transactional-message}

1. イベントの公開時に自動的に作成されたトランザクションメッセージに移動します。 [トランザクションメッセージへのアクセス](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)を参照してください。

1. メッセージを編集してパーソナライズします。 「[プロファイルトランザクションメッセージの編集](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message)」を参照してください。

1. すべてのプロファイル情報に直接アクセスできるので、[をパーソナライズ](../../designing/using/personalization.md#inserting-a-personalization-field)するには、**[!UICONTROL Profile]**&#x200B;リソースに追加した「CRM ID」フィールドを選択します。

1. **[!UICONTROL Purchase]**&#x200B;リソースから「製品識別子」フィールド（または他のフィールド）を追加して、顧客の購入に関する情報でメッセージの内容を拡張します。

1. 特定のテストプロファイルを使用してメッセージをテストできます。 [トランザクションメッセージのテスト](../../channels/using/publishing-transactional-message.md#testing-a-transactional-message)を参照してください。

1. コンテンツの準備が整ったら、変更を保存し、メッセージを発行します。 [トランザクションメッセージの公開](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)を参照してください。

## 手順3 -イベントトリガー{#integrate-event-trigger}を統合する

イベントをWebサイトに統合します(統合イベントトリガー(../../channels/using/getting-started-with-transactional-msg.md#integrate-イベントトリガー)を参照)。

## 手順4 — メッセージ配信{#message-delivery}

これらの手順がすべて完了すると、顧客がWebサイトで購入を行うとすぐに、CRM IDと購入の詳細を記載した確認の電子メールが届きます。