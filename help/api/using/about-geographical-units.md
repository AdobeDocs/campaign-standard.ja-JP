---
title: 地理的単位について
description: 地理的単位とAPIについて詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# 地理的単位について {#about-geographical-units}

>[!CAUTION]
>
>地理的単位機能は、Campaign Standard18.7リリースで非推奨（廃止予定）となりました。
>
>その結果、新しいCampaign Standardインスタンスと、地理的単位が作成されていない既存のインスタンスには、18.7リリース以降、この機能を実装できません。
>
>詳しくは、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=ja">非推奨（廃止予定）の機能</a>のページを参照してください。

**geoUnitBase**&#x200B;エンドポイントを使用して、地理的単位を操作できます。例えば、属性を更新したり、プロファイルの単位を更新したりできます。

プロファイルリソースを拡張する際に、「**地理的単位**」フィールドがプロファイルに追加されます。 そのため、必ず&#x200B;**profileAndServicesExt**&#x200B;エンドポイントを使用して地理的単位とやり取りするようにしてください。 プロファイルのリソース拡張について詳しくは、[Campaignのドキュメント](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)を参照してください。
