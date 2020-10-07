---
title: 地理的単位について
description: 地理的な単位とAPIについて詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 3%

---


# 地理的単位について {#about-geographical-units}

>[!CAUTION]
>
>Campaign Standard18.7リリースでは、地理単位機能は非推奨となりました。
>
>その結果、新しいCampaign Standardインスタンスと、地理的単位が作成されていない既存のインスタンスは、18.7リリースからこの機能を実装できません。
>
>For more on this, refer to the <a href="https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.

geoUnitBase **エンドポイントを使用すると、地理的単位を操作できます。例えば、** 地理的単位を使用して、属性を更新したり、プロファイルの単位を更新したりできます。

プロファイル資源を拡張する際に、 **Geographical unit** （地理的単位）フィールドがプロファイルに追加されます。 その結果、 **profileAndServicesExtエンドポイントを必ず使用して、地理的単位とやり取りします** 。 プロファイルのリソース拡張機能について詳しくは、 [キャンペーンのドキュメントを参照してください](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。
