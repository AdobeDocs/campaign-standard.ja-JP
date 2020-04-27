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
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---


# Campaign-Experience Manager 統合について{#integrating-with-experience-manager}

このAdobe Campaign標準とAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

したがって、Adobe Experience Managerのコンテンツ編集機能だけでなく、Adobe Campaignの配信機能やデータ管理機能も最大限に活用できます。 Adobe Experience Managerから読み込んだコンテンツに対してはA/Bテストを実行できないことに注意してください。

Adobe Campaign標準は、Adobe Experience Manager 6.1、6.2、6.3、6.4および6.5と互換性があります。以下の節では、実行できるアクションの概要を示します。 詳しくは、設定と統合の使用に関する節 [を](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) 参照 [してください](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 。

>[!NOTE]
>
> Adobe Campaign標準テンプレートは、Adobe Experience Manager 6.5では使用できなくなりました。

## Experience Managerとの統合の使用キャンペーンに関するヒント {#tips-aem}

* **統合で使用するテンプレートの把握**

   電子メールテンプレートはAdobe Experience Manager内で編集できるので、Adobe Experience Managerでテンプレートを編集した方が簡単に見える場合があります。 ただし、特定のテンプレートは容易には収まりません。 1人の顧客に固有の個別のテンプレートは、この統合に対して推奨されないので、Template Standardで直接編集する必要があります。Adobe Campaign標準。

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **実装時にExternalizerが設定されていることを確認します。**

   Experience ManagerをAdobe Campaign標準用に実装する際にExternalizerを設定すると、リソースパスをURLに変換できます。 これにより、画像をページに表示できます。 Externalizerが正しく設定されていない場合、電子メールに壊れた画像が含まれます。

   Externalizerの設定方法については、このページを参照してく [ださい](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)。

* **誤用を防ぐために、電子メールテンプレートを整理します。**

   テンプレートを整理しておくと、適切なテンプレートが適切なフォルダーに配置され、誤って間違ったテンプレートを選択しないようになります。 導入時に、適切な場所にテンプレートを保存するためのパスを作成する必要があります。

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **すぐに使用できるコンポーネントの概要**

   Adobe Campaign標準用のAdobe Experience Managerのあらかじめ用意されたコンポーネントを使用すると、テンプレートが複雑でない場合に、すばやく作業を開始できます。
Experience Managerには、次の7つの標準コンポーネントが用意されており、これらを使用して開始できます。

   * 見出し
   * 画像
   * リンク
   * Scene7画像テンプレート
   * ターゲット参照
   * テキストと画像
   * テキストとパーソナライゼーション

* **電子メールのHTMLがWeb用のHTMLと異なる**

   電子メールテンプレートには、Webコンテンツで使用されているのと同じコンポーネントを使用できないことを理解することが重要です。 標準搭載のコンポーネントを使用すると、コンポーネントが電子メール互換性を持つようになります。

* **テンプレートからコンテンツのリンクを解除し、何度も再利用します。**

   電子メールをCampaign Standardで設定し、Experience Managerテンプレートを選択する場合、別のテンプレートにまだリンクされていない電子メールのみをキャンペーンできます。 そうしないと、1つのキャンペーンでAdobe Experience Managerのコンテンツを変更して更新すると、意図せず別のキャンペーンのコンテンツに影響を与える可能性があります。
これを避けるには、テンプレートの使用が終了したら、リンクを解除して再度使用します。 テンプレートを選択し、をクリックするだけで **[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;す。

* **Adobe Experience Managerを使用して、Adobe Standardの電子メールのバリエーションをAdobe Campaignします。**

   この統合により、1つの電子メールをセグメント化の複数のバージョンに簡単に変更できます。
Adobe Experience Managerでセグメントを設定する方法と、ターゲットコンテンツを使用して電子メールを作成する方法については、このページを参照してく [ださい](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **同期を正常に行うには、Experience Managerのセグメント名が完全一致のセグメント名と一致する必要があります(キャンペーン)。**