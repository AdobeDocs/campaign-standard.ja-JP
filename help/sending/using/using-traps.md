---
title: トラップの使用
description: メッセージでトラップを使用する方法を説明します。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: df70a2165c5d3a4b553565d9a91ec3f8da1b44aa
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---


# トラップの使用 {#using-traps}

トラップを使用する場合は、メインターゲットに送信されるのと同じように、 [テストプロファイルにメッセージが送信され](../../audiences/using/managing-test-profiles.md) 、クライアントファイルが不正に使用されているかどうかを識別する手段として送信されます。

トラップは、元々ダイレクトメール配信向けに設計されていました。 これらの機能により、次のことが可能になります。

* ダイレクトメールプロバイダーが本当に通信を送信していることを確認します。
* お客様と同じ条件で、同時にメールを受信します。
* 送信されたメールの正確なコピーを保存します。
* クライアントリストがダイレクトメールプロバイダーによって誤って使用されていないことを確認します。 実際、テストプロファイルのアドレスに他の通信が送られた場合は、知らない間にクライアントファイルが使われていた可能性があります。 このため、テストプロファイルのアドレスはこの目的にのみ使用する必要があります。

ダイレクトメールのオーディエンスにトラップを追加する方法の詳細については、「テストとトラッププロファイルの [追加](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)」を参照してください。

その他の通信チャネルでは、次の目的でメインターゲットにトラップテストプロファイルを追加できます。

* メッセージが正常に送信されたことを確認します。
* メッセージの正確なコピーを取得し、保持します。
* 送信と受信のタイミングを追跡します。

テストプロファイルをトラップとして使用するには、メッセージのオーディエンスにテストメッセージが含まれている必要があります。

>[!NOTE]
>
>[配達確認](../../sending/using/sending-proofs.md) や [](../../sending/using/email-rendering.md)電子メールのレンダリングに使用されるテストプロファイルとは異なり、メッセージはメインターゲットとトラップとして使用されるテストプロファイルに同時に送信されます。

メッセージのオーディエンスを定義する場合：

1. タブから、テストプロファイルを選択し **[!UICONTROL Test profiles]** ます。 使用目的に合っていること **[!UICONTROL Trap]** を確認します。

   ![](assets/trap_select.png)

1. メッセージの内容の準備が整ったら、 **[!UICONTROL Prepare]** ボタンをクリックします。 See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >メインターゲットが選択されていることを確認します。 そうしないと、メッセージを送信できません。

1. 「**[!UICONTROL Confirm]**」ボタンをクリックします。[送信の確認](../../sending/using/confirming-the-send.md)を参照してください。

   ![](assets/trap_confirm.png)

メッセージがメインターゲットとテストプロファイルに送信されます。

トランザクションメッセージの送信時にトラップを使用できます。 この場合、テストプロファイルは、イベント設定ごとに1つのメッセージを受け取ります。 For more on transactional messaging, see this [section](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>テストプロファイルをトラップとして使用する場合、メッセージ内のリッチフィールドに対して、対応する追加データが実際のターゲットプロファイルからランダムに選択され、トラップテストプロファイルに割り当てられます。 エンリッチメントについて詳しくは、 [次の例を参照してください](../../automating/using/enriching-profile-data-file.md)。
