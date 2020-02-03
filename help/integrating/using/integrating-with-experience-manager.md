---
title: Campaign-Experience Manager 統合について
description: Adobe Experience Managerの統合により、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Campaign-Experience Manager 統合について{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

したがって、Adobe Experience Managerのコンテンツ編集機能と、Adobe Campaignの配信およびデータ管理機能を最大限に活用できます。 Adobe Experience Managerからインポートしたコンテンツに対してはA/Bテストを実行できません。

Adobe Campaign Standardは、Adobe Experience Manager 6.1、6.2、6.3、6.4および6.5と互換性があります。以下の節では、実行できるアクションの概要を示します。 詳しくは、設定と統合の使用に関する節 [を参](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) 照してください [](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 。

>[!NOTE]
>
> Adobe Campaign Standardのテンプレートは、Adobe Experience Manager 6.5では使用できなくなりました。

## CampaignとExperience Managerの統合を使用する方法に関するヒント {#tips-aem}

* **統合で使用するテンプレートの確認**

   電子メールテンプレートはAdobe Experience Manager内で編集できるので、Adobe Experience Managerでテンプレートを編集した方が簡単に見える場合があります。 ただし、特定のテンプレートは容易には収まりません。 1人の顧客に固有の個別化テンプレートは、この統合に対して推奨されないので、Adobe Campaign Standardで直接編集する必要があります。

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **実装中にExternalizerが設定されていることを確認します**

   Experience Manager for Adobe Campaign Standardを実装する際にExternalizerを設定すると、リソースパスをURLに変換できます。 これにより、画像をページに表示できます。 Externalizerが正しく設定されていない場合、電子メールに壊れたイメージが含まれます。

   Externalizerの設定方法については、このページを参照してくだ [さい](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)

* **誤用を防ぐために、電子メールテンプレートを整理します。**

   テンプレートを整理しておくと、適切なテンプレートが適切なフォルダーに配置され、誤って間違ったテンプレートを選択しないようになります。 導入時に、適切な場所にテンプレートを保存するためのパスを作成する必要があります。

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)

* **すぐに使用できるコンポーネントの概要**

   Adobe Experience Manager for Adobe Campaign Standardのあらかじめ用意されたコンポーネントを使用すると、テンプレートが複雑でない場合に、すばやく作業を開始できます。
Experience Managerには、次の7つの標準コンポーネントが用意されています。
   1. 見出し
   1. 画像
   1. リンク
   1. Scene7画像テンプレート
   1. ターゲット参照
   1. テキストと画像
   1. テキストとパーソナライゼーション

* **電子メール用のHTMLがWeb用のHTMLと異なる**

   Webコンテンツで電子メールテンプレートに使用されているのと同じコンポーネントを使用することはできないことを理解することが重要です。 標準搭載のコンポーネントを使用すると、コンポーネントが電子メールとの互換性を保つことができます。

* **テンプレートからコンテンツのリンクを解除し、何度も再利用します。**

   Campaign Standardで電子メールを設定し、Experience Managerテンプレートを選択する場合、別のキャンペーンにリンクされていない電子メールのみを選択できます。 そうしないと、1つのキャンペーンに対してAdobe Experience Managerのコンテンツを変更して更新すると、意図せず他のキャンペーンのコンテンツに影響を与える可能性があります。
これを避けるには、テンプレートの使用が終了したら、テンプレートのリンクを解除して再び使用します。 テンプレートを選択してをクリックするだけで済みま **[!UICONTROL Delete the link with Adobe Experience Manager content]**す。

* **Adobe Experience Managerを使用して、Adobe Campaign Standard用の電子メールのバリエーションを作成します。**

   この統合により、セグメント化により1つの電子メールを複数のバージョンに簡単に変更できます。
Adobe Experience Managerでのセグメントの設定方法、およびターゲットコンテンツを使用した電子メールの作成方法については、このページを参照してく [ださい](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **同期を成功させるには、Experience Managerのセグメント名がCampaignのセグメント名と完全に一致する必要があります。**