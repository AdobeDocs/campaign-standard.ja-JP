---
title: ダイレクトメールオーディエンスの定義
description: ダイレクトメール配信のターゲットを定義する方法を説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
feature: Direct Mail
role: User
level: Intermediate
exl-id: ea167fec-d4df-4147-9dcd-33001d8a1c9b
TQID: 'https://experienceleague.adobe.com/iYqxhsfsz95pTh8V-sP-xwGSSQ39YyIov9OHHyfepDI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: ede6e1ec-9279-415e-b828-a09735018d48
    internal-label: Direct mail
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 96%
---
# ダイレクトメールオーディエンスの定義{#defining-the-direct-mail-audience}

ダイレクトメールオーディエンスは、作成ウィザードを使用するか、配信ダッシュボードの「**Audience**」セクションをクリックして定義できます。

![](assets/direct_mail_15.png)

## メインターゲットの定義 {#defining-the-main-target}

ダイレクトメールのターゲットプロファイルは、ダイレクトメールプロバイダに送信する抽出ファイルに含まれるプロファイルです。

ターゲットプロファイルごとに、新しい行が抽出ファイルに追加されます。 各受信者のプロファイル情報の量は、[抽出の定義](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction)画面で定義します。

>[!IMPORTANT]
>
>住所はダイレクトメールプロバイダーにとって重要なものなので、プロファイルに住所が含まれていることを確認してください。 また、プロファイル情報の「**[!UICONTROL Address specified]**」ボックスがオンになっていることも確認してください。 [レコメンデーション](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

## テストおよびトラッププロファイルの追加 {#adding-test-and-trap-profiles}

テストプロファイルを追加して、少数のプロファイルを対象にファイルをテストできるようにします。 テストプロファイルを使用すると、実際のファイルを準備する前にファイルサンプルをすばやく作成して構造を検証できます。 [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

トラップの使用は、ダイレクトメール配信に不可欠です。 ダイレクトメールプロバイダが実際に通信を送信していること、また、クライアントリストが別のプロバイダに転送されていないことを確認できます。 [トラップの使用](../../sending/using/using-traps.md)を参照してください。

ダイレクトメール配信の場合、抽出中にトラップが追加され、出力ドキュメントに織り込まれます。 デフォルトでは出力ファイルの並べ替え順に従って挿入されますが、ファイルの冒頭または末尾に挿入するように選択できます。 オーディエンスを定義する際に、「**[!UICONTROL Trap insertion mode]**」タブから目的のオプションを選択します。

![](assets/direct_mail_trap_insertion_mode.png)
