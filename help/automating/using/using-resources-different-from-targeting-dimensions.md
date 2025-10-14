---
title: ターゲティングディメンションとは異なるリソースの使用
description: ターゲティングディメンションとは異なるリソースの使用方法を説明します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%

---

# ターゲティングディメンションとは異なるリソースの使用 {#using-resources-different-from-targeting-dimensions}

このユースケースでは、ターゲティングディメンションとは異なるリソースを使用する方法を示します（例えば、離れたテーブル内の特定のレコードを検索する場合）。

ターゲティングディメンションとリソースについて詳しくは、[&#x200B; この節 &#x200B;](../../automating/using/query.md#targeting-dimensions-and-resources) を参照してください

**例 1：配信が「お帰りなさい」というラベルでターゲットするプロファイルの識別**。

* この場合、プロファイルをターゲットします。ターゲティングディメンションを **[!UICONTROL Profiles (profile)]** に設定します。
* 配信のラベルに従って、選択したプロファイルをフィルターします。したがって、リソースを **[!UICONTROL Delivery logs]** に設定します。このようにして、配信ログテーブルで直接フィルタリングするので、パフォーマンスが向上します。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**例 2：配信が「お帰りなさい」というラベルでターゲットしなかったプロファイルの識別**

前の例では、ターゲティングディメンションとは異なるリソースを使用しました。この操作は、距離テーブル（この例では配信ログ）に&#x200B;**存在する**&#x200B;レコードを検索する場合にのみ実行できます。

距離テーブルに&#x200B;**存在しない**&#x200B;レコード（特定の配信がターゲットしなかったプロファイルなど）を検索する場合は、距離テーブル（配信ログ）にレコードが存在しないので、同じリソースとターゲティングディメンションを使用する必要があります。

* この場合、プロファイルをターゲットします。ターゲティングディメンションを **[!UICONTROL Profiles (profile)]** に設定します。
* 配信のラベルに従って、選択したプロファイルをフィルターします。配信ログテーブルに存在しないレコードを検索するので、配信ログを直接フィルターすることはできません。したがって、リソースを **[!UICONTROL Profile (profile)]** に設定し、プロファイルテーブルでクエリを作成します。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
