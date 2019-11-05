---
title: ダイレクトメールオーディエンスの定義
description: ダイレクトメール配信のターゲットを定義する方法を説明します。
page-status-flag: 非活性化の
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ダイレクトメールオーディエンスの定義{#defining-the-direct-mail-audience}

オーディエンスは、作成ウィザードで定義するか、配信ダッシュボードの「オーディエ **ンス** 」セクションをクリックして定義できます。

![](assets/direct_mail_15.png)

## メインターゲットの定義 {#defining-the-main-target}

ダイレクトメールの場合、ターゲットプロファイルは、ダイレクトメールプロバイダに送信する抽出ファイルに含まれるプロファイルです。

ターゲットプロファイルごとに、新しい行が抽出ファイルに追加されます。 各受信者に含まれるプロファイル情報の量は、抽出の定義画面 [で定義します](#defining-the-extraction) 。

>[!CAUTION]
>
>この情報はダイレクトメールプロバイダーにとって重要なものなので、プロファイルに住所が含まれていることを確認してください。 また、プロファイルの情報のボックスが **[!UICONTROL Address specified]** オンになっていることを確認します。 Recommendationsを参 [照してください](../../channels/using/about-direct-mail.md#recommendations)。

## テストおよびトラッププロファイルの追加 {#adding-test-and-trap-profiles}

少数のプロファイルでファイルをテストできるように、テストプロファイルを追加します。 これにより、実際のファイルを準備する前に、ファイルサンプルをすばやく作成して構造をテストし、検証することができます。 See [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

トラップの使用は、ダイレクトメール配信に不可欠です。 ダイレクトメールプロバイダーが実際に通信を送信していること、およびクライアントリストが別のプロバイダーに送信されていないことを確認できます。 トラップの [使用を参照してください](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps)。

ダイレクトメール配信の場合、抽出中にトラップが追加され、出力ドキュメントに混在します。 デフォルトでは、出力ファイルの並べ替え順に挿入されますが、ファイルの末尾または先頭に挿入するように選択できます。 オーディエンスを定義する際に、タブから目的のオプションを選択 **[!UICONTROL Trap insertion mode]** します。

![](assets/direct_mail_trap_insertion_mode.png)
