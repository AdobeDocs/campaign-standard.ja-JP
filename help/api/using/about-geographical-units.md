---
title: 地理的単位について
description: 地理的単位と API について詳しく説明します。
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
>地理的単位機能は、Campaign Standard18.7 リリースで廃止されました。
>
>その結果、新しいCampaign Standardインスタンスと、地理的単位が作成されていない既存のインスタンスは、18.7 リリース以降、この機能を実装することができません。
>
>詳しくは、 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=ja">非推奨（廃止予定）の機能</a> ページに貼り付けます。

The **geoUnitBase** endpoint を使用すると、地理的単位を操作して、例えば、属性を更新したり、プロファイルの単位を更新したりできます。

The **地理的単位** プロファイルリソースを拡張する際に、フィールドがプロファイルに追加されます。 そのため、必ず **profileAndServicesExt** 地理的単位とやり取りするエンドポイント。 プロファイルのリソース拡張について詳しくは、 [Campaign ドキュメント](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
