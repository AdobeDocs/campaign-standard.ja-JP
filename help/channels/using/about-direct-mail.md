---
title: ダイレクトメールについて
seo-title: ダイレクトメールについて
description: ダイレクトメールについて
seo-description: Adobe Campaignのダイレクトメールチャネルの重要性を特定します。
page-status-flag: 常にアクティブ化されていない
uuid: 24add992-2efe-4b73-81c9- cda3e921ab16
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery， directMailContent， back;DeliveryCreation， wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About direct mail{#about-direct-mail}

ダイレクトメールは、ダイレクトメールプロバイダーで必要なファイルをカスタマイズして生成できるオフラインチャネルです。オンラインおよびオフラインのチャネルを顧客ジャーニーで混合できます。

>[!NOTE]
>
>この機能はオプションです。使用許諾契約書を確認してください。**[!UICONTROL Export]** ダイレクトメールを使用するには、ロールが必要です。管理者に問い合わせてください。

オンラインチャネルでは、メッセージ（電子メール、SMS、モバイルアプリ配信など）を作成できます。Adobe Campaignから直接オーディエンスに送信できます。オフラインチャネルでは異なります。ダイレクトメール配信を準備すると、Adobe Campaignでは、ターゲット設定されたすべてのプロファイルと選択した連絡先情報（例:住所）を含むファイルが生成されます。その後、実際の送信を行うダイレクトメールプロバイダーにこのファイルを送信できます。

次の節では、1ショットのダイレクトメール配信を作成して生成する方法について説明します。オンラインおよびオフラインのチャネルを組み合わせるキャンペーンを編成するために、ワークフローにダイレクトメールアクティビティを含めることもできます。For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

Adobe Campaignのユーザープロセスは次のとおりです。

1. 配信の作成
1. オーディエンスの選択
1. コンテンツの定義
1. 連絡先日の設定
1. ファイルの生成

## Recommendations {#recommendations}

### Direct mail providers {#direct-mail-providers}

まず、ダイレクトメールプロバイダーに連絡して、レコメンデーションを収集する必要があります。抽出ファイルに含める必要のあるプロファイル情報を特定して、通信をパーソナライズしてオーディエンスに送信できるようにします。例えば、姓、名、住所、プロモーションコードなどがあります。These fields are the ones that you will add in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) tab of the direct mail's content.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. このオプションを有効にすると、プロファイルがターゲットに追加されます。It is not, it will excluded by a typology rule during the preparation phase (see [Creating the direct mail](../../channels/using/creating-the-direct-mail.md)). プロファイルの読み込み中に、このフィールドを更新しないでください。

![](assets/direct_mail_22.png)

### Postal addresses {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

Adobe Campaignでは、最も一般的な住所の正規化に従う定義済みの計算済みフィールドのセットが提供されます。The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

