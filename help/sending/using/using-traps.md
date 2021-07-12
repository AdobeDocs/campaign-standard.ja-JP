---
solution: Campaign Standard
product: campaign
title: トラップの使用
description: メッセージでトラップを使用する方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: シードアドレス
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# トラップの使用 {#using-traps}

トラップを使用する場合、メッセージは、メインターゲットに送信されると同じように、[テストプロファイル](../../audiences/using/managing-test-profiles.md)に、クライアントファイルが不正に使用されているかどうかを識別する手段として送信されます。

トラップは、元々、ダイレクトメール配信用に設計されていました。 次の操作が可能です。

* ダイレクトメールプロバイダーが実際に通信を送信していることを確認します。
* 顧客と同じ条件で同時にメールを受け取る。
* 送信されたメールの正確なコピーを保存します。
* ダイレクトメールプロバイダーがクライアントリストを誤用していないことを確認します。 実際、テストプロファイルのアドレスに他の通信が送信された場合、クライアントファイルが知らないうちに使用されていた可能性があります。 そのため、テストプロファイルのアドレスは、この目的にのみ使用する必要があります。

ダイレクトメールのオーディエンスにトラップを追加する方法について詳しくは、[テストとトラップのプロファイル](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)の追加を参照してください。

その他の通信チャネルでは、次の目的でトラップテストプロファイルをメインターゲットに追加できます。

* メッセージが正常に送信されたことを確認します。
* メッセージの正確なコピーを取得し、保持します。
* 送信および受信された日時を追跡します。

テストプロファイルをトラップとして使用するには、メッセージのオーディエンスに含める必要があります。

>[!NOTE]
>
>[配達確認](../../sending/using/sending-proofs.md)や[Eメールのレンダリング](../../sending/using/email-rendering.md)に使用されるテストプロファイルとは異なり、メッセージはメインターゲットとトラップとして使用されるテストプロファイルに同時に送信されます。

メッセージのオーディエンスを定義する場合：

1. 「 **[!UICONTROL Test profiles]** 」タブで、テストプロファイルを選択します。 使用目的に&#x200B;**[!UICONTROL Trap]**&#x200B;が含まれていることを確認します。

   ![](assets/trap_select.png)

1. メッセージコンテンツの準備が整ったら、「**[!UICONTROL Prepare]**」ボタンをクリックします。 [送信の準備](../../sending/using/preparing-the-send.md)を参照してください。
   >[!NOTE]
   >
   >メインターゲットを選択したことを確認します。 そうしないと、メッセージは送信されません。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。[送信の確認](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/trap_confirm.png)

メッセージはメインターゲットとテストプロファイルに送信されます。

トランザクションメッセージを送信する際に、トラップを使用できます。 この場合、テストプロファイルは、イベント設定ごとに1つのメッセージを受け取ります。 トランザクションメッセージについて詳しくは、[](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

>[!NOTE]
>
>テストプロファイルをトラップとして使用する場合、メッセージ内のエンリッチメントされたフィールドに対して、対応する追加データが実際のターゲットプロファイルからランダムに選択され、トラップテストプロファイルに割り当てられます。 エンリッチメントについて詳しくは、[この例](../../automating/using/enriching-profile-data-file.md)を参照してください。
