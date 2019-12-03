---
title: 地理的単位について
description: 地理的単位とAPIについて詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 地理的単位について {#about-geographical-units}

>[!CAUTION]
>
>地理的単位機能は、Campaign Standard 18.7リリースで廃止されました。
その結果、新しいCampaign Standardのインスタンスと、地理的単位が作成されていない既存のインスタンスでは、18.7リリースからこの機能を実装できません。
For more on this, refer to the <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.

geoUnitBaseエン **ドポイントを使用すると** 、地理的単位を操作できます。例えば、その属性を更新したり、プロファイルの単位を更新したりできます。

プロファ **イルリソースを拡張する際に** 、「地理的単位」フィールドがプロファイルに追加されます。 そのため、必ずprofileAndServicesExtエンドポイントを使用して **地理的単位とやり取りします** 。 プロファイルのリソース拡張機能について詳しくは、 [Campaignのドキュメントを参照してください](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。
