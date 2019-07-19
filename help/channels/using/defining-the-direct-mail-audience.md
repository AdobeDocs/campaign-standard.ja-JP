---
title: ダイレクトメールオーディエンスの定義
seo-title: ダイレクトメールオーディエンスの定義
description: ダイレクトメールオーディエンスの定義
seo-description: ダイレクトメール配信のターゲットを定義する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery， directMailContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail audience{#defining-the-direct-mail-audience}

You can either define the audience in the creation wizard or by clicking on the **Audience** section of the delivery dashboard.

![](assets/direct_mail_15.png)

## Defining the main target {#defining-the-main-target}

ダイレクトメールの場合、ターゲットプロファイルは、ダイレクトメールプロバイダーに送信する抽出ファイルに含まれるプロファイルです。

ターゲットプロファイルごとに、抽出ファイルに新しい行が追加されます。The amount of profile information that will be included for each recipient is defined in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) screen.

>[!CAUTION]
>
>この情報はダイレクトメールプロバイダーにとって重要なので、プロファイルに住所が含まれていることを確認してください。Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. [Recommendationsを](../../channels/using/about-direct-mail.md#recommendations)参照してください。

## Adding test and trap profiles {#adding-test-and-trap-profiles}

少数のプロファイルでファイルをテストできるように、テストプロファイルを追加します。ファイルサンプルをすばやく作成して、実際のファイルを準備する前に、構造をテストし検証することができます。Refer to [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

ダイレクトメール配信には、トラップの使用が不可欠です。例えば、ダイレクトメールプロバイダーが実際に通信を送信していること、およびクライアントリストを別のプロバイダーに送信していないことを確認できます。

ダイレクトメール配信の場合、抽出中にトラップが追加され、出力ドキュメントに混在します。By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file ( **[!UICONTROL Trap insertion mode]** tab).
