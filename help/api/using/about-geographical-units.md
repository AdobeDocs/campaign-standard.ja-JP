---
title: 地理的単位について
description: 地理的単位と API について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# 地理的単位について {#about-geographical-units}

>[!CAUTION]
>
>地理的単位機能は、Campaign Standard 18.7 リリースで廃止されました。
>
>その結果、新しいCampaign Standardインスタンスと、地理的ユニットが作成されていない既存のインスタンスでは、18.7 リリース以降、この機能を実装できません。
>
>詳しくは、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=ja"> 非推奨（廃止予定）の機能 </a> ページを参照してください。

**geoUnitBase** エンドポイントを使用すると、地理的単位を操作でき、例えば、属性を更新したり、プロファイルの単位を更新したりできます。

プロファイルリソースを拡張する際に、「**地理的単位**」フィールドがプロファイルに追加されます。 そのため、地理的単位を操作する場合は、必ず **profileAndServicesExt** エンドポイントを使用してください。 プロファイルのリソース拡張機能について詳しくは、[Campaign ドキュメント &#x200B;](https://helpx.adobe.com/jp/campaign/standard/administration/using/organizational-units.html#partitioning-profiles) を参照してください。
