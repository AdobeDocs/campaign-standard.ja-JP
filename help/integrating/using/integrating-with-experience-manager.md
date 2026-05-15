---
title: Campaign と Experience Manager の統合について
description: Adobe Experience Managerとの連携により、AEMで直接コンテンツを制作し、後のAdobe Campaignで使用できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
TQID: https://experienceleague.adobe.com/OuQgaZgJVeL04fw3rvn5nydbp2fOSdQOVpiFhrUcEl4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: a658c786-869b-4194-a780-2594d663addaid: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: df0d6518-6f49-46e2-b46e-3bcc513f553f
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 1%

---

# Campaign と Experience Manager の統合について{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerの連携により、Adobe Experience Managerで作成したコンテンツをAdobe Campaignの電子メールで使用できるようになります。

そのため、Adobe Experience Managerのコンテンツ編集機能と、Adobe Campaignの配信およびデータ管理機能を最大限に活用できます。 Adobe Experience Managerから読み込まれたコンテンツに対して、A/B テストを実行することはできません。

Adobe Campaign Standardは、Adobe Experience Manager 6.1、6.2、6.3、6.4、および6.5と互換性があります。 次の節では、実行できるアクションの概要を示します。 詳しくは、[設定](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)と統合の[use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)に関する専用のセクションを参照してください。

>[!NOTE]
>
> Adobe Campaign Standard テンプレートは、Adobe Experience Manager 6.5では使用できなくなりました。

## CampaignとExperience Managerの連携の使用方法に関するヒント {#tips-aem}

* **統合で使用するテンプレートを確認**

  メールテンプレートはAdobe Experience Manager内で編集可能なので、Adobe Experience Managerで任意のテンプレートを編集する方が簡単に見えるかもしれません。 しかし、特定のテンプレートには容易に対応できません。 1人のお客様に固有の個別テンプレートは、この統合には推奨されないので、Adobe Campaign Standardで直接編集する必要があります。

  テンプレートについて詳しくは、この[ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)を参照してください。

* **Externalizerが実装中に設定されていることを確認してください**

  Adobe Campaign Standard用Experience Managerを実装する際にExternalizerを設定すると、リソースパスをURLに変換できます。 これにより、画像をページに表示できます。 Externalizerが正しく設定されていない場合、メールに壊れた画像が含まれます。

  Externalizerの設定方法については、この[ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html)を参照してください。

* **悪用を避けるために電子メールテンプレートを整理します。**

  テンプレートを整理することで、適切なテンプレートが適切なフォルダー内に配置され、間違って間違ったテンプレートを選択しないようにします。 実装時には、テンプレートを適切な場所に保存するためのパスを作成する必要があります。

  テンプレートについて詳しくは、この[ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability)を参照してください。

* **すぐに利用できるコンポーネントをすぐに使用できます。**

  Adobe Campaign Standard向けのAdobe Experience Managerには、すぐに利用できるコンポーネントが実装されており、テンプレートが複雑でない場合でも、すぐに利用を開始できます。
Experience Managerには、すぐに利用できる7つのコンポーネントがあります。

   * 見出し
   * 画像
   * リンク
   * Scene7画像テンプレート
   * ターゲット参照
   * テキストと画像
   * テキストとPersonalization

* **メール用のHTMLがweb用のHTMLと異なります**

  メールテンプレートでは、web コンテンツで使用されているものと同じコンポーネントは使用できないことを理解することが重要です。 すぐに利用できるコンポーネントを使用することで、メールに対応できるコンポーネントを構築できます。

* **テンプレートからコンテンツのリンクを解除して、何度も再利用してください。**

  Campaign Standardで電子メールを設定し、Experience Manager テンプレートを選択する場合は、別のキャンペーンにまだリンクされていない電子メールのみを選択できます。 それ以外の場合、あるキャンペーンのAdobe Experience Managerでコンテンツを変更して更新すると、別のキャンペーンのコンテンツに意図せず影響を与える可能性があります。
これを回避するには、テンプレートの使用が完了したら、リンクを解除して再び使用します。 テンプレートを選択し、**[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;をクリックするだけです。

* **Adobe Experience Managerを使用して、Adobe Campaign Standardの電子メールのバリエーションを作成します。**

  この統合により、セグメント化を利用して、ひとつの電子メールから複数のバージョンを容易に作成できます。
Adobe Experience Managerでセグメント化を設定する方法と、ターゲットコンテンツを使用してメールを作成する方法については、この[ ページ ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)を参照してください。

* **同期を成功させるには、Experience Managerのセグメント名がCampaignのセグメント名と完全に一致している必要があります。**
