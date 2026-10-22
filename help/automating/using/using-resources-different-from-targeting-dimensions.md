---
title: ターゲティングディメンションとは異なるリソースの使用
description: ターゲティングディメンションとは異なるリソースの使用方法を説明します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
TQID: 'https://experienceleague.adobe.com/tGVP20eQpo7EuB1xluX2AQHHMZ-IM-q6JmgFGp6Iwk4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%
---
# ターゲティングディメンションとは異なるリソースの使用 {#using-resources-different-from-targeting-dimensions}

このユースケースでは、ターゲティングディメンションとは異なるリソースを使用して、例えば、遠いテーブル内の特定のレコードを検索する方法を示します。

ターゲティングディメンションとリソースについて詳しくは、[この節](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください

**例 1：配信が「お帰りなさい」というラベルでターゲットするプロファイルの識別**。

* この場合、プロファイルをターゲットします。 ターゲティングディメンションを **[!UICONTROL Profiles (profile)]** に設定します。
* 配信のラベルに従って、選択したプロファイルをフィルターします。 したがって、リソースを **[!UICONTROL Delivery logs]** に設定します。 これにより、配信ログテーブルで直接フィルタリングできるので、パフォーマンスが向上します。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**例 2：配信が「お帰りなさい」というラベルでターゲットしなかったプロファイルの識別**

前の例では、ターゲティングディメンションとは異なるリソースを使用しました。 この操作は、距離テーブル（この例では配信ログ）に&#x200B;**存在する**&#x200B;レコードを検索する場合にのみ実行できます。

距離テーブルに&#x200B;**存在しない**&#x200B;レコード（特定の配信がターゲットしなかったプロファイルなど）を検索する場合は、距離テーブル（配信ログ）にレコードが存在しないので、同じリソースとターゲティングディメンションを使用する必要があります。

* この場合、プロファイルをターゲットします。 ターゲティングディメンションを **[!UICONTROL Profiles (profile)]** に設定します。
* 配信のラベルに従って、選択したプロファイルをフィルターします。 配信ログテーブルに存在しないレコードを検索するので、配信ログを直接フィルターすることはできません。 したがって、リソースを **[!UICONTROL Profile (profile)]** に設定し、プロファイルテーブルでクエリを作成します。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
