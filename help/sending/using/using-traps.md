---
solution: Campaign Standard
product: campaign
title: トラップの使用
description: メッセージでトラップを使用する方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---


# トラップの使用 {#using-traps}

トラップを使用する場合、クライアントファイルが不正に使用されているかどうかを識別する手段として、メインターゲットに送信されるのと同じように、メッセージが[テストプロファイル](../../audiences/using/managing-test-profiles.md)に送信されます。

トラップは、元々ダイレクトメール配信向けに設計されていました。 これらの機能により、次のことが可能になります。

* ダイレクトメールプロバイダーが本当に通信を送信していることを確認します。
* お客様と同じ条件で、同時にメールを受信します。
* 送信されたメールの正確なコピーを保存します。
* クライアントリストがダイレクトメールプロバイダーによって誤って使用されていないことを確認します。 実際、テストプロファイルのアドレスに他の通信が送られた場合は、知らない間にクライアントファイルが使われていた可能性があります。 このため、テストプロファイルのアドレスはこの目的にのみ使用する必要があります。

ダイレクトメールのオーディエンスにトラップを追加する方法の詳細については、[テストとトラップのプロファイルの追加](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)を参照してください。

その他の通信チャネルでは、次の目的でメインターゲットにトラップテストプロファイルを追加できます。

* メッセージが正常に送信されたことを確認します。
* メッセージの正確なコピーを取得し、保持します。
* 送信と受信のタイミングを追跡します。

テストプロファイルをトラップとして使用するには、メッセージのオーディエンスにテストメッセージが含まれている必要があります。

>[!NOTE]
>
>[配達確認](../../sending/using/sending-proofs.md)や[電子メールレンダリング](../../sending/using/email-rendering.md)に使用されるテストプロファイルとは異なり、メッセージはメインターゲットとトラップとして使用されるテストプロファイルに同時に送信されます。

メッセージのオーディエンスを定義する場合：

1. 「**[!UICONTROL Test profiles]**」タブから、テストプロファイルを選択します。 **[!UICONTROL Trap]**&#x200B;が意図した用途にあることを確認してください。

   ![](assets/trap_select.png)

1. メッセージの内容の準備が整ったら、「**[!UICONTROL Prepare]**」ボタンをクリックします。 [送信の準備](../../sending/using/preparing-the-send.md)を参照してください。
   >[!NOTE]
   >
   >メインターゲットが選択されていることを確認します。 そうしないと、メッセージを送信できません。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。[送信の確認](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/trap_confirm.png)

メッセージがメインターゲットとテストプロファイルに送信されます。

トランザクションメッセージの送信時にトラップを使用できます。 この場合、テストプロファイルは、イベント設定ごとに1つのメッセージを受け取ります。 トランザクションメッセージについて詳しくは、[](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

>[!NOTE]
>
>テストプロファイルをトラップとして使用する場合、メッセージ内のリッチフィールドに対して、対応する追加データが実際のターゲットプロファイルからランダムに選択され、トラップテストプロファイルに割り当てられます。 エンリッチメントについて詳しくは、[この例](../../automating/using/enriching-profile-data-file.md)を参照してください。
