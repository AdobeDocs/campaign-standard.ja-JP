---
title: ダイレクトメール視聴者の定義
seo-title: ダイレクトメール視聴者の定義
description: ダイレクトメール視聴者の定義
seo-description: ダイレクトメール配信のターゲットを定義する方法を説明します。
page-status-flag: 決して活性化されていない
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: チャンネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: 配信， DirectMailContent，背面
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# ダイレクトメール視聴者の定義{#defining-the-direct-mail-audience}

作成ウィザードで対象者を定義することも、配信ダッシュボードの **「対象者」** セクションをクリックすることもできます。

![](assets/direct_mail_15.png)

## メインターゲットの定義 {#defining-the-main-target}

ダイレクトメールの場合、ターゲットプロファイルは、ダイレクトメールプロバイダーに送信する抽出ファイルに含まれるプロファイルです。

ターゲットプロファイルごとに、抽出ファイルに新しい行が追加されます。各受信者に含まれるプロファイル情報の量は、「定義 [の定義](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) 」画面で定義されます。

>[!CAUTION]
>
>ダイレクトメールプロバイダーに必要な情報がプロファイルに含まれていることを確認してください。また、プロファイルの情報の **[!UICONTROL Address specified]** ボックスをチェックしたことを確認してください。[推奨](../../channels/using/about-direct-mail.md#recommendations)事項を参照してください。

## テストプロファイルとトラッププロファイルの追加 {#adding-test-and-trap-profiles}

少数のプロファイルでファイルをテストできるように、テストプロファイルを追加します。実際のファイルを準備する前に、ファイルサンプルをすばやく作成して、構造体をテストおよび検証することができます。「 [テストプロファイルの管理および証明書の送信」を参照](../../sending/using/managing-test-profiles-and-sending-proofs.md)してください。

メール配信にはトラップの使用が不可欠です。ダイレクトメールプロバイダーが実際に通信を送信していることを確認し、クライアントリストを別のプロバイダーに送信していないことを確認します。トラップ [の使用を参照](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps)してください。

ダイレクトメール配信の場合、トラップは抽出時に追加され、出力ドキュメントに混合されます。既定では、出力ファイルの並べ替え順序に挿入されますが、ファイルの末尾または先頭に挿入することもできます。対象者を定義するときに、 **[!UICONTROL Trap insertion mode]** タブから目的のオプションを選択します。

![](assets/direct_mail_trap_insertion_mode.png)
