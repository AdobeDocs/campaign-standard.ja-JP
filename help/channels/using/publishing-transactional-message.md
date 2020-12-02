---
solution: Campaign Standard
product: campaign
title: イベントトランザクションメッセージ
description: イベントトランザクションメッセージを作成して公開する方法について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# トランザクションメッセージライフサイクル{#publishing-transactional-message}

[トランザクションメッセージ](../../channels/using/editing-transactional-message.md)を送信する準備ができたら、それを公開できます。

イベントのテスト、公開、一時停止、非公開、削除の手順を以下に示します。 この節では、トランザクションメッセージングの再試行プロセスについても説明します。

## トランザクションメッセージの公開プロセス {#transactional-messaging-pub-process}

以下の表に、トランザクションメッセージングの公開プロセス全体を示します。

![](assets/message-center_pub-process.png)

トランザクションメッセージの公開について詳しくは、[このセクション](#publishing-a-transactional-message)を参照してください。
トランザクションメッセージの一時停止について詳しくは、[このセクション](#suspending-a-transactional-message-publication)を参照してください。
トランザクションメッセージの非公開について詳しくは、[このセクション](#unpublishing-a-transactional-message)を参照してください。

イベントの公開と非公開について詳しくは、[このセクション](../../channels/using/publishing-transactional-event.md)を参照してください。

## トランザクションメッセージのテスト{#testing-a-transactional-message}

まず、トランザクションメッセージを正しく確認できる特定のテストプロファイルを作成する必要があります。

### 特定のテストプロファイルの定義{#defining-specific-test-profile}

メッセージをプレビューし、関連配達確認を送信できるように、イベントにリンクするテストプロファイルを定義します。

1. トランザクションメッセージダッシュボードで&#x200B;**[!UICONTROL Create test profile]**&#x200B;ボタンをクリックします。

   ![](assets/message-center_test-profile.png)

1. JSON 形式で送信する情報を「**[!UICONTROL Event data used for personalization]**」セクションに指定します。これは、メッセージをプレビューするとき、およびテストプロファイルが配達確認を受け取るときに使用されるコンテンツです。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >プロファイルテーブルに関連する情報を入力することもできます。[イベントを豊かにする](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->を参照してください。

1. 作成したテストプロファイルは、トランザクションメッセージで事前に指定されます。 配達確認のターゲットを確認するには、メッセージの「**[!UICONTROL Test profiles]**」ブロックをクリックします。

   ![](assets/message-center_5.png)

新規テストプロファイルを作成するか、既に「**[!UICONTROL Test profiles]**」メニューにあるテストを使用することもできます。手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Profiles & audiences]**／**[!UICONTROL Test profiles]** を選択します。
1. **[!UICONTROL Event]**&#x200B;セクションで、先ほど作成したイベントを選択します。 この例では、「買い物かごの放棄（EVTcartAbandant）」を選択します。
1. JSON 形式で送信する情報を「**[!UICONTROL Event data]**」テキストボックスに指定します。

   ![](assets/message-center_3.png)

1. 変更を保存します。
1. 作成したメッセージにアクセスし、更新したテストプロファイルを選択します。

**関連トピック：**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

### 配達確認の送信 {#sending-proof}

1つ以上の特定のテストプロファイルを作成し、トランザクションメッセージを保存したら、配達確認を送信してテストできます。

![](assets/message-center_10.png)

配達確認を送信する手順については、「[配達確認の送信](../../sending/using/sending-proofs.md)」の節を参照してください。

## トランザクションメッセージの公開{#publishing-a-transactional-message}

トランザクションメッセージを確認したら、それを公開できます。

![](assets/message-center_12.png)

これで、「買い物かごの放棄」イベントがトリガーされるとすぐに、受信者のタイトルと姓、買い物かごの URL、最後に参照した製品、または製品のリスト（製品リストを定義した場合）と送信される買い物かごの総数を含むメッセージが自動的に表示されます。

トランザクションメッセージに関するレポートにアクセスするには、「**[!UICONTROL Reports]**」ボタンを使用します。[動的レポート](../../reporting/using/about-dynamic-reports.md)を参照してください。

![](assets/message-center_13.png)

### トランザクションメッセージ公開の一時停止{#suspending-a-transactional-message-publication}

トランザクションメッセージに含まれるデータを変更する場合など、「**[!UICONTROL Pause]**」ボタンを使用してメッセージの公開を中止できます。したがって、イベントは処理されず、Adobe Campaign データベースのキューに保持されます。

キューに格納されたイベントは、REST APIで定義された期間（[REST APIのドキュメント](../../api/using/managing-transactional-messages.md)を参照）またはTriggersコアサービスを使用している場合はトリガーイベント([Adobe Experience Cloudトリガーについて](../../integrating/using/about-adobe-experience-cloud-triggers.md)を参照)に保持されます。

![](assets/message-center_pause.png)

「**[!UICONTROL Resume]**」をクリックすると、キューに格納されているすべてのイベント（期限切れでない場合）が処理されます。テンプレートのパブリケーションが停止されている間に実行されたすべての変更が含まれています。

### トランザクションメッセージの非公開{#unpublishing-a-transactional-message}

「**[!UICONTROL Unpublish]**」をクリックすると、トランザクションメッセージの公開をキャンセルするだけでなく、対応するイベントの公開もキャンセルします。これにより、REST API から、以前に作成したイベントに対応するリソースが削除されます。

![](assets/message-center_unpublish-template.png)

これで、Web サイトを通じてイベントがトリガーされた場合でも、対応するメッセージは送信されなくなり、データベースには保存されません。

>[!NOTE]
>
>メッセージを再度公開するには、対応するイベント設定に戻り、[イベント](../../channels/using/publishing-transactional-event.md)を公開し、[メッセージ](#publishing-a-transactional-message)を公開する必要があります。

一時停止したトランザクションメッセージを非公開にする場合は、再度公開するまで 24 時間待たなければならない場合があります。これは、キューに送信されたすべてのイベントを「**[!UICONTROL Database cleanup]**」ワークフローで消去するためです。

メッセージを一時停止する手順について詳しくは、[トランザクションメッセージ公開の一時停止](#suspending-a-transactional-message-publication)の節を参照してください。

毎日午前 4 時に実行される「**[!UICONTROL Database cleanup]**」ワークフローは、**[!UICONTROL Administration]**／**[!UICONTROL Application settings]**／**[!UICONTROL Workflows]** からアクセスできます。

### トランザクションメッセージの削除{#deleting-a-transactional-message}

トランザクションメッセージが非公開になっている場合、またはトランザクションメッセージがまだ公開されていない場合は、トランザクションメッセージリストから削除できます。手順は次のとおりです。

1. 左上隅の **[!UICONTROL Adobe Campaign]** ロゴをクリックし、**[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Transactional messages]** を選択します。
1. 選択したメッセージにマウスを合わせます。
1. 「**[!UICONTROL Delete element]**」ボタンをクリックします。

![](assets/message-center_delete-template.png)

ただし、トランザクションメッセージの削除は、次の特定の状況でのみ実行できます。

* トランザクションメッセージのステータスが「**[!UICONTROL Draft]**」であることを確認してください。そうでない場合、削除できません。この「**[!UICONTROL Draft]**」ステータスは、まだ公開されていないメッセージ、または[非公開にする](#unpublishing-a-transactional-message)（または[一時停止](#suspending-a-transactional-message-publication)されていない）メッセージに適用されます。

* **トランザクションメッセージ**：対応するイベントに別のトランザクションメッセージがリンクされている場合を除き、トランザクションメッセージが非公開の場合は、イベントを正常に削除するために、トランザクションメッセージ設定も非公開にする必要があります。詳しくは、[イベントの非公開](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)を参照してください。

   >[!IMPORTANT]
   >
   >既に通知を送信したトランザクションメッセージを削除すると、その送信およびトラッキングログも削除されます。

* **標準搭載のイベントテンプレート（内部トランザクションメッセージ）**：内部トランザクションメッセージが、対応する内部イベントに関連付けられている唯一のものである場合、削除できません。別のトランザクションメッセージを作成する場合は、まず複製するか、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Transactional message templates]** メニューを使用します。

## トランザクションメッセージの再試行プロセス{#transactional-message-retry-process}

一時的に配信されないトランザクションメッセージは、配信が期限切れになるまで自動再試行が実行される場合があります。配信期間について詳しくは、[有効期間パラメーター](../../administration/using/configuring-email-channel.md#validity-period-parameters)を参照してください。

トランザクションメッセージの送信に失敗した場合は、2 つの再試行システムがあります。

* トランザクションメッセージングレベルでは、トランザクションメッセージが実行配信に割り当てられる前（イベントの受信と配信の準備の間）に、イベントが失敗する可能性があります。[イベント処理の再試行プロセス](#event-processing-retry-process)を参照してください。
* 送信プロセスレベルでは、イベントが実行配信に割り当てられると、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。詳しくは、[メッセージ送信の再試行プロセス](#message-sending-retry-process)を参照してください。

### イベント処理の再試行プロセス{#event-processing-retry-process}

イベントを実行配信に割り当てられない場合、イベント処理は延期されます。再試行は、新しい実行配信に割り当てられるまで実行されます。

>[!NOTE]
>
>延期されたイベントは、まだ実行配信に割り当てられていないため、トランザクションメッセージ送信ログには表示されません。

例えば、イベントの内容が正しくない、アクセス権やブランディングに問題がある、タイポロジルールの適用時にエラーが検出されたなどの理由で、実行配信にを割り当てることができない場合があります。この場合、メッセージを一時停止し、編集して問題を修正し、再度公開できます。再試行システムは、その後、新しい実行配信に割り当てます。

### メッセージ送信の再試行プロセス{#message-sending-retry-process}

イベントが実行配信に割り当てられると、受信者のメールボックスがいっぱいになった場合など、一時的なエラーが原因でトランザクションメッセージが失敗する場合があります。詳しくは、[一時的な配信エラーの後の再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

>[!NOTE]
>
>イベントが実行配信に割り当てられると、そのイベントはこの実行配信の送信ログに今回のみ表示されます。失敗した配信は、ログを送信するトランザクションメッセージの&#x200B;**[!UICONTROL Execution list]**&#x200B;タブに表示されます。

### プロセスの制限を再試行{#limitations}

**ログの更新を送信中**

再試行プロセスでは、新しい実行配信の送信ログは直ちに更新されません（更新はスケジュールされたワークフローを介して実行されます）。つまり、トランザクションイベントが新しい実行配信で処理されている場合でも、メッセージの「**[!UICONTROL Pending]**」ステータスが変わる可能性があります。

**失敗した実行配信**

実行配信を停止することはできません。ただし、現在の実行配信が失敗した場合、新しいイベントを受け取るとすぐに新しいイベントが作成され、すべての新しいイベントがこの新しい実行配信で処理されます。失敗した実行配信で新しいイベントが処理されることはありません。

実行配信に既に割り当てられている一部のイベントが延期され、その実行配信に失敗した場合、再試行システムは、延期されたイベントを新しい実行配信に割り当てません。これは、これらのイベントが失われたことを意味します。
