---
title: 地域ユニットについて
description: 地理的単位とAPIについて詳しく見る。
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
source-wordcount: '145'
ht-degree: 6%
---

# 地域ユニットについて {#about-geographical-units}

>[!CAUTION]
>
>地理的単位機能は、Campaign Standard 18.7 リリースで廃止されました。
>
>その結果、新しいCampaign Standard インスタンスと、地理的単位が作成されていない既存のインスタンスでは、18.7 リリース以降、この機能を実装できません。
>
>詳しくは、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=ja">非推奨の機能</a> ページを参照してください。

**geoUnitBase** エンドポイントを使用すると、地理的単位を操作できます。例えば、属性を更新したり、プロファイルの単位を更新したりできます。

プロファイルリソースを拡張すると、**地理単位** フィールドがプロファイルに追加されます。 そのため、地理的単位を操作するには、常に&#x200B;**profileAndServicesExt** エンドポイントを使用することを忘れないでください。 プロファイルのリソース拡張機能について詳しくは、[Campaign ドキュメント ](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)を参照してください。
