---
title: キャンペーンのカスタムリソースとDynamics 365カスタムエンティティのマップ
description: Adobe Campaign StandardとMicrosoft Dynamics 365の統合に関連して、リソースとエンティティをマッピングする方法を説明します。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e11de4d4482400e62be2db076c88da5ae30d60cc
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---


# キャンペーンリソースとDynamics 365エンティティのマップ

Adobe Campaign StandardとMicrosoft Dynamics 365の統合のコンテキストで、カスタムリソースとカスタムエンティティをマッピングする方法を説明します。

>[!CAUTION]
>
>この機能は、製品の一部として初期状態では使用できません。 導入には、Adobeコンサルティングが関与している必要があります。 詳細については、Adobeの担当者にお問い合わせください。

## 前提条件

[Microsoft Dynamics 365-Adobe Campaign Standard統合は、カスタムエンティティをサポートし](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) 、Dynamics 365のカスタムエンティティをキャンペーン内の対応するカスタムリソースに同期できます。

カスタムリソースの新しいデータは、セグメント化やパーソナライゼーションなど、いくつかの目的で使用できます。

統合では、リンクされたテーブルとリンクされていないテーブルの両方がサポートされます。 リンクは、最大3つのレベル(level1->level2->level3)までサポートされます。

>[!CAUTION]
>
>キャンペーンのカスタムリソースレコードに個人情報が含まれている場合は、特定のレコメンデーションが適用されます。 詳しくは、[この節](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources)を参照してください。

## お知らせ

カスタムエンティティデータフローを設定する場合は、次の点に注意してください。

* キャンペーンのカスタムリソースを作成および変更する操作は、機密性の高い操作です。この操作は、エキスパートユーザーのみが実行する必要があります。
* カスタムエンティティデータフローの場合、同期されたカスタムエンティティに対して、Dynamics 365内で変更追跡を有効にする必要があります。
* Dynamics 365で親子レコードとリンク子レコードがほぼ同時に作成された場合、統合の並行処理により、新しい子レコードが親レコードの前にキャンペーンに書き込まれる可能性が少しあります。

* 親レコードと子レコードがキャンペーン側で1基単純リンク **** オプションを使用してリンクされている場合、親レコードがキャンペーンに到達するまで、子レコードは非表示のまま（UIまたはAPIを介して）アクセスできません。

* ( **1カーディナリティ単純リンク** (キャンペーン内)Dynamics 365で子レコードが更新または削除され、その変更がキャンペーンに表示される前にキャンペーンに書き込まれた場合、その更新または削除はキャンペーンで処理されず、エラーが発生します。 更新の場合、更新したレコードを同期するには、問題のレコードをDynamics 365で再び更新する必要があります。 削除の場合、削除または更新するDynamics 365にレコードがなくなったので、問題のレコードは、キャンペーン側で別々に処理する必要があります。

* 非表示の子レコードがあり、その子レコードにアクセスできないと思われる場合は、基数のリンクの種類を **0または1の基数の単純リンクに一時的に変更して、それらのレコードにアクセスできます** 。

キャンペーンのカスタムリソースの詳細な概要については、こ [の節を参照してください](../../developing/using/key-steps-to-add-a-resource.md)。
