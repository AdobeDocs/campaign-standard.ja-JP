---
title: 多言語メッセージテンプレート
description: 顧客の好みの言語を自動的にセグメント化し、単一の配信を通じて多言語の電子メール/SMS配信を定義し、実行する方法を説明します。 言語レベルと個々のレベルに至るまでの各配信のパフォーマンスに関するレポートを作成します。
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# 多言語メッセージテンプレート {#multilingual-messages-template}

多言語テンプレートは、多言語メッセージを管理するための特定のテンプレートです。 この種のテンプレートは、****Email** / **** SMSメッセージで使用でき、スタンドアロンモード、ワークフロー内、または定期的な配信で使用できます。

多言語機能テンプレートでは、言語管理はバリアントに基づいています。 **各バリアントは1つの言語を表します**。 Adobe Campaign Standardでは、最大40個のバリアントを設定できます。

Adobe Campaignには、 **ENに設定されたデフォルトの言語が付属しています**。 デフォルトの言語は別のバリアントに変更できますが、削除しないでください。

テンプレートの作成時に、メッセージ内の必要な言語の数に対応するバリアントの数を追加できます。

SMSまたは電子メールテンプレートの作成を実行するには、次の手順に従います。

1. 既存の多言語テンプレート（SMSまたは電子メール）を複製します。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >また、テンプレートプロパティのボタンをクリックして、多言語テンプレート内の既存の標準テンプ **[!UICONTROL Initialize content variant]**レートを変更することもできます。

1. プロパティを変更して、ラベル、追跡などをカスタマイズします。
1. 目的のバリアントの数を変更するには、バリアントタイルをクリックします。 「バリアント」ウィンドウが表示されます

   ![](assets/multi_template_variants.png)

   バリアントを追加または削除できます。 バリアントを追加するには、ウィンドウを完 **[!UICONTROL New content variant]**了します。

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >「default」バリアントは、完成した優先言語パラメーターなしでプロファイルに送信されるバリアントなので、削除しないでください。

1. 必要に応じてラベルバリアントをカスタマイズし、をクリックしま **[!UICONTROL Confirm]**す。
1. また、各バリアントのコンテンツを直接追加することもできます。

これで、この多言語テンプレートに基づく電子メールまたはSMSメッセージを作成する準備が整いました。

**関連トピック：**

* [多言語 E メールの作成](../../channels/using/creating-a-multilingual-email.md)
* [プロファイルの作成](../../audiences/using/creating-profiles.md)
