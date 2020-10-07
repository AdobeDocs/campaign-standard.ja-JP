---
title: Campaign と Experience Manager の統合について
description: Adobe Experience Manager統合では、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 1%

---


# Campaign と Experience Manager の統合について{#integrating-with-experience-manager}

このAdobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

したがって、Adobe Experience Managerのコンテンツ編集機能だけでなく、Adobe Campaignの配信機能やデータ管理機能も最大限に活用できます。 Adobe Experience Managerからインポートしたコンテンツに対してはA/Bテストを実行できないことにご注意ください。

Adobe Campaign Standardは、Adobe Experience Manager6.1、6.2、6.3、6.4および6.5と互換性があります。次の節では、実行できるアクションの概要を示します。 詳しくは、 [設定](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) および統合の [使用に関する節を参照してください](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 。

>[!NOTE]
>
> Adobe Experience Manager6.5では、Adobe Campaign Standardテンプレートは使用できなくなりました。

## キャンペーンとExperience Managerの統合を使用する方法のヒント {#tips-aem}

* **統合で使用するテンプレートの確認**

   電子メールテンプレートはAdobe Experience Manager内で編集できるので、Adobe Experience Managerではどのテンプレートを編集した方が簡単に見える場合があります。 ただし、特定のテンプレートは容易には収まりません。 1人の顧客に固有の個別のテンプレートは、この統合に対して推奨されないので、Adobe Campaign Standardで直接編集する必要があります。

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **実装中にExternalizerが設定されていることを確認します**

   Adobe Campaign StandardのExperience Managerを実装する際にExternalizerを設定すると、リソースパスをURLに変換できます。 これにより、画像をページに表示できます。 Externalizerが正しく設定されていない場合は、電子メールに壊れた画像が含まれます。

   Externalizerの設定方法については、この [ページを参照してください](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)。

* **誤用を防ぐために、電子メールテンプレートを整理します。**

   テンプレートを整理しておくと、適切なテンプレートが適切なフォルダーに配置され、誤って間違ったテンプレートが選択されないようになります。 導入時に、テンプレートを適切な場所に保存するためのパスを作成する必要があります。

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **すぐに使用できるコンポーネントの使い方を簡単に説明します。**

   テンプレートが複雑でない場合は、Adobe Experience ManagerのAdobe Campaign Standard向けの既成コンポーネントを使用すれば、すばやく作業を開始できます。
Experience Managerには、次の7つの標準コンポーネントがあり、これらを使用して開始できます。

   * 見出し
   * 画像
   * リンク
   * Scene7画像テンプレート
   * ターゲット参照
   * テキストと画像
   * テキストとパーソナライゼーション

* **電子メール用のHTMLはWeb用のHTMLとは異なる**

   Webコンテンツで使用されているのと同じコンポーネントを電子メールテンプレートに使用することはできないことを理解することが重要です。 標準搭載のコンポーネントを使用すると、コンポーネントが電子メール互換性を持つようになります。

* **テンプレートからコンテンツのリンクを解除し、何度も再利用します。**

   Campaign Standardで電子メールを設定し、Experience Managerテンプレートを選択する場合は、別のキャンペーンにリンクされていない電子メールのみを選択できます。 そうしないと、1回のキャンペーンでAdobe Experience Managerのコンテンツを変更して更新した場合、意図せず別のキャンペーンのコンテンツに影響を与える可能性があります。
これを回避するには、テンプレートの使用を終了した後に、テンプレートのリンクを解除して再び使用します。 テンプレートを選択してをクリックするだけで済み **[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;ます。

* **Adobe Experience Managerを使用して、Adobe Campaign Standard向けの電子メールのバリエーションを作成します。**

   この統合により、1つの電子メールをセグメント化の複数のバージョンに簡単に変更できます。
Adobe Experience Managerでセグメントを設定する方法、およびターゲットコンテンツを使用した電子メールの作成方法については、この [ページを参照してください](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **同期を成功させるには、Experience Manager内のセグメント名が、完全一致キャンペーン内のセグメント名と一致する必要があります。**