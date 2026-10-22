---
title: 組織単位について
description: 組織単位とAPIについて詳しく見る。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 0%
---

# 組織単位について {#about-organizational-units}

**orgUnitBase** エンドポイントを使用すると、組織単位を操作できます。例えば、属性を更新したり、プロファイルの組織単位を更新したりできます。 Campaignの組織単位について詳しくは、[Campaign ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html#administrating)を参照してください。

プロファイルリソースを拡張すると、**組織単位** フィールドがプロファイルに追加されます。 そのため、地理的単位を操作するには、常に&#x200B;**profileAndServicesExt** エンドポイントを使用することを忘れないでください。 プロファイルのリソース拡張機能について詳しくは、[Campaign ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html#partitioning-profiles)を参照してください。
