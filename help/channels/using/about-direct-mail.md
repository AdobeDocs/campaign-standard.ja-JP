---
solution: Campaign Standard
product: campaign
title: ダイレクトメールについて
description: Adobe Campaign 内のダイレクトメールチャネルの主な特性について説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ダイレクトメールについて{#about-direct-mail}

ダイレクトメールは、ダイレクトメールプロバイダーから求められるファイルのパーソナライズおよび生成を可能にするオフラインチャネルです。ダイレクトメールにより、カスタマージャーニーにオンラインチャネルとオフラインチャネルを混在させることができます。

>[!NOTE]
>
>この機能はオプションです。使用許諾契約書を確認してください。「**[!UICONTROL Export]**」役割では、ダイレクトメールを使用する必要があります。管理者にお問い合わせください。

オンラインチャネルでは、メッセージ（E メール、SMS、モバイルアプリ配信など）を作成し、Adobe Campaign から直接オーディエンスにメッセージを送信できます。オフラインチャネルの場合は異なります。ダイレクトメール配信を準備すると、Adobe Campaign により、すべてのターゲットプロファイルと選択した連絡先情報（例えば、郵便の宛先）を含むファイルが生成されます。その後、このファイルを実際の発送処理をおこなうダイレクトメールプロバイダーに送信できます。

次の節では、ワンショットダイレクトメール配信の作成方法と生成方法を説明します。また、ワークフローにダイレクトメールアクティビティを追加し、オンラインとオフラインのチャネルを組み合わせてキャンペーンを調整することもできます。詳しくは、[ワークフロー](../../automating/using/get-started-workflows.md)ガイドを参照してください。

Adobe Campaign のユーザープロセスは次のとおりです。

1. 配信の作成
1. オーディエンスの選択
1. コンテンツの定義
1. 連絡日の設定
1. ファイルの生成

**関連トピック：**

* [使用例：電子メールとダイレクトメールの配信の結合](../../automating/using/coupling-email-direct-mail.md)

## 推奨事項 {#recommendations}

### ダイレクトメールプロバイダー{#direct-mail-providers}

まず、ダイレクトメールプロバイダーに問い合わせて、推奨事項を確認する必要があります。抽出ファイルに格納する必要があるプロファイル情報を特定して、コミュニケーションをパーソナライズし、オーディエンスに送信できるようにします。例えば、氏名、住所、プロモーションコードなどです。これらのフィールドは、ダイレクトメールのコンテンツの「[抽出の定義](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction)」タブで追加するフィールドです。

また、プロファイル情報の「**[!UICONTROL Address specified]**」ボックスがオンになっていることも確認してください。このオプションを有効にすると、プロファイルがターゲットに追加されます。有効でない場合、準備段階でタイポロジルールにより除外されます（[ダイレクトメールの作成](../../channels/using/creating-the-direct-mail.md)を参照）。プロファイルのインポート時に必ずこのフィールドを更新してください。

![](assets/direct_mail_22.png)

### 郵送先住所 {#postal-addresses}

抽出ファイルに含めるフィールドを追加すると、「**[!UICONTROL Location]**」ノードで郵送先住所フィールドを使用できます。

Adobe Campaign では、最も一般的な住所の規格に従って定義された計算済みフィールドのセットが含まれます。これらのフィールドは「**[!UICONTROL Postal address]**」ノードで使用できます。

1 つの住所は、デフォルトで最大 6 つの行から構成されます。最初の計算済みフィールド（**[!UICONTROL Line 1]**）には氏名、その後の行には郵送先住所（番地など）、最後の行には郵便番号や市区町村が含まれます。

![](assets/direct_mail_23.png)
