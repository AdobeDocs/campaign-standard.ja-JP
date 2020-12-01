---
solution: Campaign Standard
product: campaign
title: 地理的単位について
description: 地理的な単位とAPIについて詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---


# 地理的単位について{#about-geographical-units}

>[!CAUTION]
>
>Campaign Standard18.7リリースでは、地理単位機能は非推奨となりました。
>
>その結果、新しいCampaign Standardインスタンスと、地理的単位が作成されていない既存のインスタンスは、18.7リリースからこの機能を実装できません。
>
>この点について詳しくは、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">非推奨機能</a>のページを参照してください。

**geoUnitBase**&#x200B;エンドポイントを使用すると、地理的単位を操作できます。例えば、プロファイルの属性を更新したり、エンドポイントを更新したりできます。

プロファイルリソースを拡張する際に、プロファイルに&#x200B;**Geographical unit**&#x200B;フィールドが追加されます。 その結果、**profileAndServicesExt**&#x200B;エンドポイントを必ず使用して、地理的な単位とやり取りします。 プロファイルのリソース拡張子について詳しくは、[キャンペーンドキュメント](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)を参照してください。
