---
title: Campaign と Experience Manager の統合について
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用することができます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# Campaign と Experience Manager の統合について{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerのこの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaign E メールで使用できます。

そのため、Adobe Experience Managerのコンテンツ編集機能と、Adobe Campaignの配信およびデータ管理機能を最大限に活用できます。 A/B テストは、Adobe Experience Managerから読み込んだコンテンツに対しては実行できないことに注意してください。

Adobe Campaign Standardは、Adobe Experience Manager 6.1、6.2、6.3、6.4 および 6.5 と互換性があります。次の節では、実行できるアクションの概要を示します。 詳しくは、 [設定](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) そして [use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 統合の。

>[!NOTE]
>
> Adobe Campaign Standardテンプレートは、Adobe Experience Manager 6.5 では使用できなくなりました。

## Campaign とExperience Managerの統合の使用方法に関するヒント {#tips-aem}

* **統合で使用するテンプレートを理解する。**

   電子メールテンプレートはAdobe Experience Manager内で編集できるので、Adobe Experience Managerで任意のテンプレートを編集すると簡単になる場合があります。 ただし、特定のテンプレートは容易には対応できません。 1 人の顧客に固有の個々のテンプレートは、この統合では推奨されないので、Adobe Campaign Standardで直接編集する必要があります。

   テンプレートについて詳しくは、 [ページ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **実装時に Externalizer が設定されたことを確認します。**

   Adobe Campaign StandardのExperience Managerを実装する際に Externalizer を設定すると、リソースパスを URL に変換できます。 これにより、画像がページに表示されるようになります。 Externalizer が正しく設定されていない場合、電子メールには壊れた画像が含まれます。

   Externalizer の設定方法については、こちらを参照してください。 [ページ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **誤用を避けるために、電子メールテンプレートを整理します。**

   テンプレートを整理しておくと、適切なテンプレートが適切なフォルダーに配置され、間違って間違ったテンプレートが選択されないようになります。 実装時に、適切な場所にテンプレートを保存するためのパスを作成する必要があります。

   テンプレートについて詳しくは、 [ページ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **すぐに使用できるコンポーネントをすばやく使い始めます。**

   Adobe Experience Manager for Adobe Campaign Standardの既製のコンポーネントを使用すると、テンプレートが複雑でない場合に、すばやく使い始めることができます。
次の 7 つの標準コンポーネントをExperience Managerで使用できます。

   * 見出し
   * 画像
   * リンク
   * Scene7画像テンプレート
   * ターゲット参照
   * テキストと画像
   * テキストとパーソナライゼーション

* **メールのHTMLが Web のHTMLと異なる**

   Web コンテンツで使用されるのと同じコンポーネントを、E メールテンプレートに使用することはできないことを理解することが重要です。 標準搭載のコンポーネントを使用すると、コンポーネントは E メールに対応します。

* **テンプレートからコンテンツのリンクを解除し、何度も再利用します。**

   Campaign Standardで E メールを設定し、Experience Managerテンプレートを選択する場合、選択できるのは、まだ別のキャンペーンにリンクされていないメールのみです。 そうしないと、1 つのキャンペーンに対してAdobe Experience Managerのコンテンツを変更して更新した場合に、意図せず他のキャンペーンのコンテンツに影響を与える可能性があります。
テンプレートの使用が終了したら、リンクを解除して再び使用できます。 テンプレートを選択し、「 **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Adobe Experience Managerを使用して、Adobe Campaign Standardの E メールのバリエーションを作成します。**

   この統合により、1 つの E メールをセグメント化を使用して簡単に複数のバージョンに変換できます。
Adobe Experience Managerでのセグメント化の設定方法と、ターゲットコンテンツを含む E メールの作成方法については、こちらを参照してください。 [ページ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **同期を正常におこなうには、Experience Managerのセグメント名が Campaign のセグメント名と完全に一致する必要があります。**
