---
title: 組織単位について
description: 組織単位と API の詳細を説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---


# 組織単位について {#about-organizational-units}

この **orgUnitBase** endpoint を使用すると、組織単位を操作して、例えば、属性を更新したり、プロファイルの組織単位を更新したりできます。 Campaign の組織単位について詳しくは、 [Campaign ドキュメント](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=en#administrating).

この **組織単位** プロファイルリソースを拡張する際に、フィールドがプロファイルに追加されます。 そのため、必ず **profileAndServicesExt** 地理的単位とやり取りするエンドポイント。 プロファイルのリソース拡張について詳しくは、 [Campaign ドキュメント](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=en#partitioning-profiles).
