---
title: ターゲティングディメンションとは異なるリソースの使用
description: ターゲティングディメンションとは異なるリソースを使用する方法を説明します。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# ターゲティングディメンションとは異なるリソースの使用 {#using-resources-different-from-targeting-dimensions}

この使用例では、離れたテーブル内の特定のレコードを検索する場合など、ターゲティングディメンションとは異なるリソースを使用する方法を示します。

ターゲティングディメンションとリソースについて詳しくは、 [この節を参照してください](../../automating/using/query.md#targeting-dimensions-and-resources)

**例1: 配信がターゲットとするプロファイルを「おかえり！」というラベルで識別しています**。

* この場合、ターゲットプロファイルが必要です。 ターゲティングディメンションをに設定しま **[!UICONTROL Profiles (profile)]**&#x200B;す。
* 配信のラベルに従って、選択したプロファイルをフィルタリングします。 そのため、資源をに設定し **[!UICONTROL Delivery logs]**&#x200B;ます。 このように、配信ログテーブルで直接フィルタリングを行い、オファーのパフォーマンスが向上します。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**例2: 「おかえり！」というラベルを付けて、配信がターゲットにしなかったプロファイルを特定する**

前の例では、ターゲティングディメンションとは異なるリソースを使用しました。 この操作は、遠隔テーブルに存在するレコードを探す場合にのみ可能 **です** (この例の配信ログ)。

遠隔テーブルに存在し **ないレコード(特定の配信がターゲットにしていないプロファイルなど** )を探す場合は、遠隔テーブル(配信ログ)にレコードが存在しないので、同じリソースとターゲティングディメンションを使用する必要があります。

* この場合、ターゲットプロファイルが必要です。 ターゲティングディメンションをに設定しま **[!UICONTROL Profiles (profile)]**&#x200B;す。
* 配信のラベルに従って、選択したプロファイルをフィルタリングします。 配信ログテーブルに存在しないレコードを探しているので、配信ログを直接フィルタリングすることはできません。 したがって、リソースをに設定し、プロファイルテーブルでクエリ **[!UICONTROL Profile (profile)]** を構築します。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
