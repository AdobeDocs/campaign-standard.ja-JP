---
title: 多言語メッセージテンプレート
description: 単一の配信を通じて、自動的にセグメント化された顧客の優先言語に基づいた多言語のメールおよび SMS 配信を定義および実行する方法について説明します。 各配信のパフォーマンスを、言語レベルと個人レベルでレポートにまとめます。
audience: start
content-type: reference
topic-tags: managing-templates
feature: Multilingual Messages
role: User
level: Intermediate
exl-id: 3d869f31-7dfb-4546-aba5-80a2787e00be
TQID: 'https://experienceleague.adobe.com/TsDW-1w3j0-CvsR0R0V-KnUOc4VahG7iCg46bgCyBJ0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: fa669864-b1c7-4f0a-8d32-9480adcbe6a2
    internal-label: Multilingual messages
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 100%
---
# 多言語メッセージテンプレート {#multilingual-messages-template}

多言語テンプレートは、多言語メッセージを管理するための固有のテンプレートです。 このテンプレートは、**メール**&#x200B;や **SMS** メッセージに対して、スタンドアロンモード、ワークフロー内、または繰り返し配信で使用できます。

多言語機能テンプレートでは、言語管理はバリアントに基づいています。 **各バリアントは 1 つの言語を表します**。 Adobe Campaign Standard では、最大 40 個のバリアントを設定できます。

Adobe Campaign では、デフォルトの言語が **EN** に設定されています。 デフォルトの言語は別のバリアントに変更できますが、削除しないでください。

テンプレートの作成時に、メッセージで必要な言語の数に対応するバリアントの数を追加できます。

SMS やメールのテンプレート作成を実行するには、次の手順に従います。

1. 既存の多言語テンプレート（SMS またはメール）を複製します。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >また、テンプレートプロパティの「**[!UICONTROL Initialize content variant]**」ボタンをクリックして、多言語テンプレート内の既存の標準テンプレートを変更することもできます。

1. プロパティを変更して、ラベルやトラッキングなどをカスタマイズします。

1. バリアントの数を変更するには、バリアントタイルをクリックします。 バリアントウィンドウが表示されます。

   ![](assets/multi_template_variants.png)

   バリアントを追加または削除できます。 バリアントを追加するには、**[!UICONTROL New content variant]** ウィンドウで必要事項を入力します。

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >「default」バリアントは、指定された優先言語パラメーターがないプロファイルに送信されるバリアントなので、削除しないでください。

1. 必要に応じてラベルのバリアントをカスタマイズし、「**[!UICONTROL Confirm]**」をクリックします。

1. 各バリアントのコンテンツを直接追加することもできます。

これで、この多言語テンプレートに基づくメールまたは SMS メッセージを作成する準備ができました。

**関連トピック：**

* [多言語メールの作成](../../channels/using/creating-a-multilingual-email.md)
* [プロファイルの作成](../../audiences/using/creating-profiles.md)
