---
title: トラップの使用
description: メッセージでトラップを使用する方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# トラップの使用 {#using-traps}

トラップを使用すると、メッセージは [テストプロファイル](../../audiences/using/managing-test-profiles.md) クライアントファイルが不正に使用されているかどうかを識別する手段として、メインターゲットに送信されるのと同様です。

トラップは、もともと、ダイレクトメール配信用に設計されていました。 次のことが可能です。

* ダイレクトメールプロバイダーが実際に通信を送信していることを確認します。
* 同時に、顧客と同じ条件でメールを受信します。
* 送信されたメールの正確なコピーを保持します。
* ダイレクトメールプロバイダがクライアントリストを誤用していないことを確認します。 実際、テストプロファイルのアドレスに他の通信が送信された場合は、クライアントファイルが知らずに使用されていた可能性があります。 そのために、テストプロファイルのアドレスを使用する必要があります。

ダイレクトメールのオーディエンスへのトラップの追加について詳しくは、 [テストおよびトラッププロファイルの追加](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

その他の通信チャネルでは、次の目的でトラップテストプロファイルをメインターゲットに追加できます。

* メッセージが正常に送信されたことを確認します。
* メッセージの正確なコピーを取得し、保持します。
* 送信および受信された日時を追跡します。

テストプロファイルをトラップとして使用するには、メッセージのオーディエンスにプロファイルを含める必要があります。

>[!NOTE]
>
>に使用されるテストプロファイルとは異なります。 [配達確認](../../sending/using/sending-proofs.md) または [電子メールのレンダリング](../../sending/using/email-rendering.md)に設定すると、メッセージがメインターゲットとトラップとして使用されるテストプロファイルに同時に送信されます。

メッセージのオーディエンスを定義する場合：

1. 次から： **[!UICONTROL Test profiles]** 「 」タブで、テストプロファイルを選択します。 必ず **[!UICONTROL Trap]** 意図した用途として。

   ![](assets/trap_select.png)

1. メッセージコンテンツの準備が整ったら、 **[!UICONTROL Prepare]** 」ボタンをクリックします。 詳しくは、 [送信の準備](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >メインターゲットを選択していることを確認します。 そうしないと、メッセージは送信されません。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。[送信の確認](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/trap_confirm.png)

メッセージはメインターゲットとテストプロファイルに送信されます。

トランザクションメッセージの送信時にトラップを使用できます。 この場合、テストプロファイルは、イベント設定ごとに 1 つのメッセージを受け取ります。 トランザクションメッセージについて詳しくは、 [セクション](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>テストプロファイルをトラップとして使用する場合、メッセージ内のエンリッチメントされたフィールドに対して、対応する追加データが実際のターゲットプロファイルからランダムに選択され、トラップテストプロファイルに割り当てられます。 エンリッチメントについて詳しくは、 [この例](../../automating/using/enriching-profile-data-file.md).
