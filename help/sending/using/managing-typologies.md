---
title: タイポロジの管理
description: タイポロジの使い方を見つけます。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3

---


# タイポロジの管理 {#managing-typologies}

## タイポロジについて {#about-typologies}

タイポロジとは、メッセージを送信する前にメッセージの有効性を確認できる一連のルールです。 例：メッセージの内容が空ではない、購読解除が存在する、メッセージの除外などの重複。

タイポロジには、//メニュ **[!UICONTROL Administration]** ーからア **[!UICONTROL Channels]** クセスで **[!UICONTROL Typologies]** きます。 デフォルトでは、アプリケーションでデフォルトのタイポロジが使用できます。 ニーズに基づいて、独自のタイポロジを作成したり、既存のタイポロジを変更したりできます。

![](assets/typologies-list.png)

各タイポロジに対して、セクシ **[!UICONTROL Typology rules]** ョンでは、リストと共にタイポロジを使用する際に実行される一連のルールを指定します。

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>いずれかのタイポロジルールの詳細を表示するには、重複クリックします。 ルールは読み取り専用モードで表示されます。

## Creating a typology {#creating-a-typology}

新しいタイポロジを作成するには、次の手順に従います。

1. //メニュー **[!UICONTROL Administration]** にアク **[!UICONTROL Channels]** セス **[!UICONTROL Typologies]** します。

1. 類型のリストが表示されます。 ボタンをクリッ **[!UICONTROL Create]** クします。

   ![](assets/typologies-create.png)

1. タイポロジを定義 **[!UICONTROL Label]**&#x200B;し、ボタンをク **[!UICONTROL Add an element]** リックして、含めるタイポロジルールを選択します。 For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >このフ **[!UICONTROL IP affinity]** ィールドでは、設定に従ってアフィニティを管理できます。 これらは、インスタンスの設定ファイルで定義されます。 このユーザーを使用する場合は、アフィニティに問い合わせてください。

1. Click **[!UICONTROL Create]** to confirm your selection. これで、メッセージでタイポロジを使用する準備が整いました。

## メッセージへのタイポロジの適用 {#applying-typologies-to-messages}

タイポロジをメッセージまたはメッセージテンプレートに関連付けると、タイポロジに含まれるタイポロジルールが実行され、メッセージの有効性が確認されます。

>[!NOTE]
>
>各メッセージまたはメッセージテンプレートに割り当てることができるタイポロジは1つだけです。

メッセージにタイポロジをリンクするには、次の手順に従います。

1. メッセージのプロパティにアクセスします。 メッセージテンプレートは、/ナビゲーションメニューからア **[!UICONTROL Resources]** クセスでき **[!UICONTROL Templates]** ることに注意してください。

1. 「/」セク **[!UICONTROL Advanced parameters]** ション **[!UICONTROL Prearation]** で、メッセージにリンクするタイポロジを選択します。

   ![](assets/typology_message.png)

1. クリック **[!UICONTROL Confirm]** .

   選択したタイポロジがメッセージにリンクされます。 関連するすべてのタイポロジルールが実行され、メッセージの有効性が確認されます。
