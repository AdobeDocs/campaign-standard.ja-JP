---
title: ダイレクトメールオーディエンスの定義
description: ダイレクトメール配信のターゲットを定義する方法を説明します。
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705
workflow-type: ht
source-wordcount: '278'
ht-degree: 100%

---


# ダイレクトメールオーディエンスの定義{#defining-the-direct-mail-audience}

ダイレクトメールオーディエンスは、作成ウィザードを使用するか、配信ダッシュボードの「**Audience**」セクションをクリックして定義できます。

![](assets/direct_mail_15.png)

## メインターゲットの定義 {#defining-the-main-target}

ダイレクトメールのターゲットプロファイルは、ダイレクトメールプロバイダに送信する抽出ファイルに含まれるプロファイルです。

ターゲットプロファイルごとに、新しい行が抽出ファイルに追加されます。各受信者のプロファイル情報の量は、[Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction)画面で定義します。

>[!CAUTION]
>
>住所はダイレクトメールプロバイダーにとって重要なものなので、プロファイルに住所が含まれていることを確認してください。また、プロファイル情報の「**[!UICONTROL Address specified]**」ボックスがオンになっていることも確認してください。[推奨事項](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

## テストおよびトラッププロファイルの追加 {#adding-test-and-trap-profiles}

テストプロファイルを追加して、少数のプロファイルを対象にファイルをテストできるようにします。テストプロファイルを使用すると、実際のファイルを準備する前にファイルサンプルをすばやく作成して構造を検証できます。[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

トラップの使用は、ダイレクトメール配信に不可欠です。ダイレクトメールプロバイダが実際に通信を送信していること、また、クライアントリストが別のプロバイダに転送されていないことを確認できます。[トラップの使用](../../sending/using/using-traps.md)を参照してください。

ダイレクトメール配信の場合、抽出中にトラップが追加され、出力ドキュメントに織り込まれます。デフォルトでは出力ファイルの並べ替え順に従って挿入されますが、ファイルの冒頭または末尾に挿入するように選択できます。オーディエンスを定義する際に、「**[!UICONTROL Trap insertion mode]**」タブから目的のオプションを選択します。

![](assets/direct_mail_trap_insertion_mode.png)
