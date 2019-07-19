---
title: 多言語テンプレートの作成
seo-title: 多言語テンプレートの作成
description: 多言語テンプレートの作成
seo-description: 自動的にセグメント化された顧客の好みの言語に基づいて、複数言語の電子メール/SMS配信を定義して実行する方法について説明します。言語および個々のレベルまでのすべての配信のパフォーマンスについてレポートします。
page-status-flag: 常にアクティブ化されていない
uuid: 7a2cd5f7- c0fc-4825- a770- a62816c66b3f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: 参照
topic-tags: managing- templates
discoiquuid: 064c5c4a- f579-4bab- adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a multilingual template{#creating-a-multilingual-template}

多言語テンプレートは、多言語メッセージを管理するための特定テンプレートです。

This kind of template is available for **Email and SMS messages** and useable in standalone mode, within a workflow or in a recurring delivery.

多言語機能テンプレートでは、言語管理はバリアントに基づいています。**各バリアントは1つの言語を表します。**

Adobe Campaign Standardでは、最大40個のバリアントを設定できます。

Adobe Campaignには、ENに設定されているデフォルトの言語が付属しています。デフォルトの言語は別のバリアントに変更できますが、削除しないでください。

テンプレートの作成時に、メッセージに必要な言語の数に対応するバリアントの数を追加できます。

SMSまたは電子メールテンプレートを作成するには、次の手順に従います。

1. 既存の多言語テンプレート（SMSまたは電子メール）を複製します。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >You can also modify an existing standard template in a multilingual template by clicking on the **[!UICONTROL Initialize content variant]** button in the template properties.

1. ラベル、トラッキングなどをカスタマイズするプロパティを変更します。
1. バリアントタイルをクリックして、目的のバリアントの数を変更します。バリアントウィンドウが表示されます

   ![](assets/multi_template_variants.png)

   バリアントを追加または削除できます。To add a variant, complete the **[!UICONTROL New content variant]** window.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >"default"バリアントは、プロファイルに送信されたバリアントではなく、プロファイルに送信されないようにしてください。

1. 必要に応じてラベルバリアントをカスタマイズし、確認をクリックします。
1. また、各バリアントのコンテンツを直接追加することもできます。

これで、この多言語テンプレートに基づいて電子メールまたはSMSメッセージを作成する準備が整いました。

**関連トピック:**

* [多言語電子メールの作成](../../channels/using/creating-a-multilingual-email.md)
* [プロファイルの作成](../../audiences/using/creating-profiles.md)

