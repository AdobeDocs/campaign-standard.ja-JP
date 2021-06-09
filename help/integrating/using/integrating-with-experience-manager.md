---
solution: Campaign Standard
product: campaign
title: Campaign と Experience Manager の統合について
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: トリガー
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: f6e94cf98662e708730be672149d836ef0e56522
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 1%

---

# Campaign と Experience Manager の統合について{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe CampaignのEメールで使用できます。

そのため、Adobe Experience Managerのコンテンツ編集機能や、Adobe Campaignの配信およびデータ管理機能を最大限に活用できます。 A/Bテストは、Adobe Experience Managerから読み込んだコンテンツに対しては実行できません。

Adobe Campaign Standardは、Adobe Experience Manager 6.1、6.2、6.3、6.4および6.5と互換性があります。次の節では、実行できるアクションの概要を示します。 詳しくは、[設定](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)と、統合の[使用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)に関する節を参照してください。

>[!NOTE]
>
> Adobe Campaign Standard 6.5では、Adobe Experience Managerテンプレートは使用できなくなりました。

## CampaignとExperience Managerの統合の使用方法に関するヒント{#tips-aem}

* **統合で使用するテンプレートの理解**

   EメールテンプレートはAdobe Experience Manager内で編集できるので、Adobe Experience Managerで任意のテンプレートを編集する方が簡単になる場合があります。 ただし、特定のテンプレートは容易に収まりません。 1人の顧客に固有の個別化されたテンプレートは、この統合では推奨されないので、Adobe Campaign Standardで直接編集する必要があります。

   テンプレートについて詳しくは、この[ページ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)を参照してください。

* **実装時にExternalizerが設定されていることを確認します。**

   Adobe Campaign StandardのExperience Managerを実装する際にExternalizerを設定すると、リソースパスをURLに変換できます。 これにより、画像をページに表示できます。 Externalizerが正しく設定されていない場合、電子メールに壊れた画像が含まれます。

   Externalizerの設定方法については、この[ページ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html)を参照してください。

* **誤用を避けるために、Eメールテンプレートを整理します。**

   テンプレートを整理しておくと、適切なテンプレートが適切なフォルダーに配置され、間違ったテンプレートが誤って選択されるのを防ぐことができます。 実装時に、適切な場所にテンプレートを保存するためのパスを作成する必要があります。

   テンプレートについて詳しくは、この[ページ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability)を参照してください。

* **すぐに使用できるコンポーネントの概要です。**

   Adobe Experience Manager for Adobe Campaign Standardの既製のコンポーネントを使用すると、テンプレートが複雑でない場合でも、すばやく使い始めることができます。
次の7つの標準コンポーネントをExperience Managerで使用できます。

   * 見出し
   * 画像
   * リンク
   * Scene7画像テンプレート
   * ターゲット参照
   * テキストと画像
   * テキストとパーソナライゼーション

* **電子メール用のHTMLはWeb用のHTMLとは異なる**

   Webコンテンツで使用されるのと同じコンポーネントをEメールテンプレートに使用することはできないことを理解することが重要です。 標準搭載のコンポーネントを使用すると、コンポーネントは確実にEメールと互換性を持ちます。

* **テンプレートからコンテンツのリンクを解除し、何度も再利用します。**

   Campaign StandardでEメールを設定し、Experience Managerテンプレートを選択する場合、選択できるのは、まだ別のキャンペーンにリンクされていないEメールのみです。 そうしないと、1つのキャンペーンに対してAdobe Experience Managerのコンテンツを変更して更新すると、意図せず他のキャンペーンのコンテンツに影響を与える可能性があります。
この問題を回避するには、テンプレートの使用を終了した後に、リンクを解除して再び使用します。 必要なのは、テンプレートを選択して**[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;をクリックするだけです。

* **Adobe Experience Managerを使用して、Adobe Campaign Standard用のEメールのバリエーションを作成します。**

   この統合により、1つのEメールをセグメント化機能を使用して複数のバージョンに簡単に変換できます。
Adobe Experience Managerでのセグメント化の設定方法と、ターゲットコンテンツを含むEメールの作成方法については、この[ページ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)を参照してください。

* **同期を正常におこなうには、Experience Manager内のセグメント名がCampaign内のセグメント名と完全に一致する必要があります。**
