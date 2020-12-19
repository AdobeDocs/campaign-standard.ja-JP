---
solution: Campaign Standard
product: campaign
title: Campaign のカスタムリソースと Dynamics 365 カスタムエンティティのマッピング
description: Adobe Campaign StandardとMicrosoft Dynamics 365の統合に関連して、リソースとエンティティをマッピングする方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# キャンペーンリソースとDynamics 365エンティティのマップ

Adobe Campaign StandardとMicrosoft Dynamics 365の統合のコンテキストで、カスタムリソースとカスタムエンティティをマッピングする方法を説明します。

>[!CAUTION]
>
>この機能は、製品の一部として初期状態では使用できません。実装するには、アドビのコンサルティングサービス部門に依頼する必要があります。詳しくは、アドビ担当者にお問い合わせください。

## 前提条件

[Microsoft Dynamics 365-Adobe Campaign Standard統合](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)は、カスタムエンティティをサポートしており、Dynamics 365のカスタムエンティティをキャンペーン内の対応するカスタムリソースと同期できます。

カスタムリソースの新しいデータは、セグメント化やパーソナライゼーションなど、いくつかの目的で使用できます。

統合では、リンクされたテーブルとリンクされていないテーブルの両方がサポートされます。 リンクは、最大3つのレベル(level1->level2->level3)までサポートされます。

>[!CAUTION]
>
>キャンペーンのカスタムリソースレコードに個人情報が含まれている場合は、特定のレコメンデーションが適用されます。 詳しくは、[この節](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources)を参照してください。

## お知らせ

カスタムエンティティデータフローを設定する場合は、次の点に注意してください。

* キャンペーンのカスタムリソースを作成および変更する操作は、機密性の高い操作です。この操作は、エキスパートユーザーのみが実行する必要があります。
* カスタムエンティティデータフローの場合、同期されたカスタムエンティティに対して、Dynamics 365内で変更追跡を有効にする必要があります。
* Dynamics 365で親子レコードとリンク子レコードがほぼ同時に作成された場合、統合の並行処理が原因で、新しい子レコードが親レコードの前にキャンペーンに書き込まれる可能性が少しあります。

* 親レコードと子レコードがキャンペーン側で&#x200B;**1基の基数単純リンク**&#x200B;オプションを使用してリンクされている場合、親レコードがキャンペーンに到達するまで、子レコードは非表示になり、アクセスできなくなります。

* (キャンペーン内の&#x200B;**1個の基数単純リンク**)Dynamics 365で子レコードが更新または削除され、親レコードがキャンペーンに表示される前にその変更がキャンペーンに書き込まれた場合、その更新または削除はキャンペーンで処理されず、エラーが発生します。 更新の場合、更新したレコードを同期するには、問題のレコードをDynamics 365で再び更新する必要があります。 削除の場合、削除または更新するDynamics 365にレコードがなくなったので、問題のレコードは、キャンペーン側で別々に処理する必要があります。

* 非表示の子レコードがあり、それらにアクセスできないと思われる状況に陥った場合は、カーディナリティリンクの種類を&#x200B;**0または1カーディナリティ単純リンク**&#x200B;に一時的に変更して、これらのレコードにアクセスできます。

キャンペーンのカスタムリソースの詳細な概要は、この節](../../developing/using/key-steps-to-add-a-resource.md)に[あります。
