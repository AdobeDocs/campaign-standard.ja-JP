---
title: 年齢層別の分類
description: このページでは、データベースプロファイルの年齢グループに基づくセグメント化を示します。 このワークフローの目的は、各年齢層に対して特定の電子メールを送信することです。
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# 年齢層別の分類 {#segmentation-age-groups}

次の例は、データベースプロファイルを年齢グループに従って分類する例です。

このワークフローの目的は、各年齢層に対して特定の電子メールを送信することです。 このワークフローがテストキャンペーンの一部であることを考慮すると、制限があり、同時に表示するオーディエンスを使用するために、各セグメントには最大100個のプロファイルしか含めることができません。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* ワークフローの実行日を指定する [スケジューラーアクティビティ](../../automating/using/segmentation.md) 。
* 誕生日と電子メールアドレスが入力された人のターゲットプロファイルに対する [クエリ](../../automating/using/query.md) アクティビティ。
* 3つのセグメントを異なるアウトバウンドトランジションに分割して作成する [セグメント化](../../automating/using/segmentation.md) アクティビティ: 18-25歳、26-32歳、32歳以上のプロファイル。 セグメントは、次のパラメーターに従って定義します。

   ![](assets/wkf_segment_example_3.png)

   * セグメントの年齢グループを定義する年齢に関するフィルター

      ![](assets/wkf_segment_new_segment.png)

   * 制限値100にリンクされた **[!UICONTROL Random sampling]** 種類 **[!UICONTROL Maximum size]** 制限

      ![](assets/wkf_segment_example_1.png)

* セグメントごとの [電子メール配信](../../automating/using/email-delivery.md) アクティビティ。
