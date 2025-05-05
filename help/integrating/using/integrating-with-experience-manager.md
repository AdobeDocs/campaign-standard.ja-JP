---
title: Campaign と Experience Manager の統合について
description: Adobe Experience Manager統合を使用すると、コンテンツをAEMで直接作成して、後からAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# Campaign と Experience Manager の統合について{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignのメールで使用できます。

そのため、Adobe Experience Managerのコンテンツ編集機能とAdobe Campaignの配信およびデータ管理機能を最大限に活用できます。 Adobe Experience Managerから読み込んだコンテンツに対しては、A/B テストを実行できません。

Adobe Campaign Standardは、Adobe Experience Manager 6.1、6.2、6.3、6.4、6.5 と互換性があります。以下の節では、実行可能なアクションの概要を説明します。 詳しくは、統合の [ 設定 ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=ja) と [ 使用 ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=ja) に関する節を参照してください。

>[!NOTE]
>
> Adobe Campaign Standard テンプレートは、Adobe Experience Manager 6.5 では使用できなくなりました。

## Campaign とExperience Managerの統合の使用方法に関するヒント {#tips-aem}

* **統合で使用するテンプレートを把握する**

  メールテンプレートはAdobe Experience Manager内で編集できるので、Adobe Experience Managerでテンプレートを編集した方が簡単に見える場合があります。 しかし、特定のテンプレートは簡単には対応できません。 1 人のお客様に固有の個別のテンプレートは、この統合ではお勧めしません。Adobe Campaign Standardで直接編集する必要があります。

  テンプレートについて詳しくは、この [ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=ja) を参照してください。

* **実装時に Externalizer が設定されていることを確認してください**

  Adobe Campaign StandardのExperience Managerを実装する際に Externalizer を設定すると、リソースパスを URL に変換できます。 これにより、画像をページに表示できます。 Externalizer が適切に設定されていない場合、メールには壊れた画像が含まれます。

  Externalizer の設定方法については、この [ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html?lang=ja) を参照してください。

* **誤用を避けるためにメールテンプレートを整理します。**

  テンプレートを整理しておくと、適切なテンプレートが適切なフォルダーに配置され、間違って選択されることがなくなります。 実装時には、テンプレートを適切な場所に保存するためのパスを作成する必要があります。

  テンプレートについて詳しくは、この [ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=ja#template-availability) を参照してください。

* **既製のコンポーネントをすぐに使用できます。**

  Adobe Campaign Standard用Adobe Experience Managerの標準コンポーネントを使用すると、テンプレートが複雑でない場合にすばやく開始できます。
Experience Managerには、次の 7 つの標準コンポーネントが用意されており、それらを使用して開始できます。

   * 見出し
   * 画像
   * リンク
   * Scene7画像テンプレート
   * ターゲット参照
   * テキストと画像
   * テキストとPersonalization

* **E メールのHTMLは、Web のHTMLとは異なります**

  メールテンプレートには、web コンテンツで使用されるのと同じコンポーネントを使用することはできないことを理解しておくことが重要です。 標準のコンポーネントを使用すると、コンポーネントにメール互換性が生じます。

* **テンプレートからコンテンツのリンクを解除して、何度も何度も再利用する。**

  Campaign Standardでメールを設定し、Experience Managerテンプレートを選択する場合、別のキャンペーンにまだリンクされていないテンプレートのみを選択できます。 そうでない場合は、あるキャンペーンのAdobe Experience Managerのコンテンツを変更して更新すると、他のキャンペーンのコンテンツに意図せず影響を与える可能性があります。
これを回避するには、テンプレートの使用が完了したら、リンクを解除して再度使用します。 テンプレートを選択して「**[!UICONTROL Delete the link with Adobe Experience Manager content]**」をクリックするだけです。

* **Adobe Experience Managerを使用して、Adobe Campaign Standard用のメールのバリエーションを作成します。**

  この統合により、セグメント化を使用して 1 つのメールを複数のバージョンに簡単に変換できます。
Adobe Experience Managerでセグメント化を設定する方法と、ターゲットコンテンツを含んだメールを作成する方法については、この [ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html?lang=ja#setting-up-segmentation-in-aem) を参照してください。

* **同期を正常に行うには、Experience Managerのセグメント名が Campaign のセグメント名と完全に一致する必要があります。**
