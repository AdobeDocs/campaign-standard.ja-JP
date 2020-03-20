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
source-git-commit: a7c2d444b7d971124b676fa2392b51aab40e5629

---


# トラップの使用 {#using-traps}

トラップを使用する場合、メッセージはメインターゲットに送信されるのと同じように [](../../audiences/using/managing-test-profiles.md) 、クライアントファイルが不正に使用されているかどうかを識別する手段として、テストプロファイルに送信されます。

トラップは、元々ダイレクトメール配信用に設計されていました。 これらのツールを使用すると、次のことができます。

* ダイレクトメールプロバイダが本当に通信を送信していることを確認します。
* 顧客と同じ条件で同時にメールを受け取ります。
* 送信されたメールの正確なコピーを保存します。
* クライアントリストがダイレクトメールプロバイダによって誤って使用されていないことを確認します。 実際、テストプロファイルのアドレスに他の通信が送られた場合は、知らない間にクライアントファイルが使われていた可能性があります。 これが、テストプロファイルのアドレスをこの目的にのみ使用する理由です。

ダイレクトメールのオーディエンスにトラップを追加する方法について詳しくは、テストとトラッ [プのプロファイルの追加を参照してくださ](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)い。

他の通信チャネルの場合は、次の目的でトラップテストプロファイルをメインターゲットに追加できます。

* メッセージが正常に送信されたことを確認します。
* メッセージの正確なコピーを取得し、保持します。
* いつ送信および受信されたかを追跡します。

テストプロファイルをトラップとして使用するには、メッセージのオーディエンスに含める必要があります。

>[!NOTE]
>
>校正や電子メールのレンダリングに使用さ [れる](../../sending/using/sending-proofs.md)[](../../sending/using/email-rendering.md)プロファイルのテストとは異なり、メッセージはメインターゲットとトラップとして使用されるテストプロファイルに同時に送信されます。

メッセージのオーディエンスを定義する場合：

1. タブから、テ **[!UICONTROL Test profiles]** ストプロファイルを選択します。 使用目的に合わせて使用し **[!UICONTROL Trap]** てください。

   ![](assets/trap_select.png)

1. メッセージの内容の準備が整ったら、ボタンをクリック **[!UICONTROL Prepare]** します。 See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >メインターゲットが選択されていることを確認します。 そうしないと、メッセージを送信できません。

1. ボタンをクリッ **[!UICONTROL Confirm]** クします。 See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

メッセージがメインターゲットとテストプロファイルに送信されます。

トラップは、トランザクションメッセージの送信時に使用できます。 この場合、テストプロファイルはイベント設定ごとに1つのメッセージを受け取ります。 トランザクションメッセージについて詳しくは、この節を参照し [てくださ](../../channels/using/about-transactional-messaging.md)い。

>[!NOTE]
>
>テスト・プロファイルをトラップとして使用する場合、メッセージ内の富んだフィールドに対して、対応する追加データが実際のターゲット・プロファイルからランダムに選択され、トラップ・テスト・プロファイルに割り当てられる。 エンリッチメントの詳細については、この例を [参照してくださ](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file)い。
