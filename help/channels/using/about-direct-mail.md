---
title: ダイレクトメールについて
description: Adobe Campaign内のダイレクトメールチャネルの主な特性
page-status-flag: never-activated
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# ダイレクトメールについて{#about-direct-mail}

ダイレクトメールは、ダイレクトメールプロバイダーから求められるファイルのパーソナライズおよび生成を可能にするオフラインチャネルです。ダイレクトメールにより、カスタマージャーニーにオンラインチャネルとオフラインチャネルを混在させることができます。

>[!NOTE]
>
>この機能はオプションです。使用許諾契約書を確認してください。役割は、 **[!UICONTROL Export]** ダイレクトメールを使用する必要があります。 管理者に問い合わせてください。

オンラインチャネルでは、メッセージ（E メール、SMS、モバイルアプリ配信など）を作成し、Adobe Campaign から直接オーディエンスにメッセージを送信できます。オフラインチャネルの場合は異なります。ダイレクトメール配信を準備すると、Adobe Campaign により、すべてのターゲットプロファイルと選択した連絡先情報（例えば、郵便の宛先）を含むファイルが生成されます。その後、このファイルを実際の発送処理をおこなうダイレクトメールプロバイダーに送信できます。

次のセクションでは、ワンショットダイレクトメールの作成方法と生成方法を説明します。配信 また、ワークフローにダイレクトメールアクティビティを含めて、オンラインとオフラインのキャンペーンを組み合わせたチャネルを調整することもできます。 詳しくは、[ワークフロー](../../automating/using/workflow-data-and-processes.md)ガイドを参照してください。

ユーザープロセスのAdobe Campaignは次のとおりです。

1. 配信の作成
1. オーディエンス
1. コンテンツの定義
1. 連絡日の設定
1. ファイルの生成

## 推奨事項 {#recommendations}

### ダイレクトメールプロバイダ {#direct-mail-providers}

まず、ダイレクトメールプロバイダーに連絡し、推奨事項を収集する必要があります。 抽出ファイルに含める必要のあるプロファイル情報を特定し、通信をパーソナライズしてオーディエンスに送信できるようにします。 例えば、姓と名、住所、プロモーションコードなど。 これらのフィールドは、ダイレクトメールの内容の [[抽出](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) ]タブで追加するフィールドです。

ボックスの情報がチェック済みであ **[!UICONTROL Address specified]** ることをプロファイルに確認します。 このオプションを有効にすると、プロファイルがターゲットに追加されます。 準備段階では、除外されません(ダイレクトメールの作成を参照 [してください](../../channels/using/creating-the-direct-mail.md))。 プロファイルのインポート中に、このフィールドを必ず更新してください。

![](assets/direct_mail_22.png)

### 郵送先住所 {#postal-addresses}

抽出ファイルに含めるフィールドを追加すると、そのノードで住所のフィールドを使用でき **[!UICONTROL Location]** ます。

Adobe Campaignオファーには、最も一般的な住所の標準化に従った定義済みの計算フィールドのセットが含まれます。 ノード内でフィールドを使用で **[!UICONTROL Postal address]** きます。

An address can contain up to six lines by default: the first calculated field (**[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

