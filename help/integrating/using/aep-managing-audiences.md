---
title: Adobe Experience Platform オーディエンスの管理
description: Campaign Standard内でAdobe Experience Platformを管理する方法について説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%
---
# Adobe Experience Platform オーディエンスの管理 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Serviceは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azure（現在は北米のみベータ版）でホスティングされている必要があります。 アクセスをご希望の場合は、Adobe カスタマーケアにお問い合わせください。

## Adobe Experience Platformオーディエンスへのアクセス

Adobe Experience Platform セグメントビルダーにアクセスするには、Campaign Standard ホームページの&#x200B;**[!UICONTROL Audiences]** カード（またはヘッダーの&#x200B;**[!UICONTROL Audiences]** リンク）に移動し、**[!UICONTROL Adobe Experience Platform]**&#x200B;環境を選択します。

![](assets/aep_audiences_access.png)

最初にAdobe Experience Platform セグメントリストページに移動します。このページでは、既存のAdobe Experience Platform セグメントにアクセスして、さらに編集することができます。

目的のAdobe Experience Platform セグメントを見つけるのに役立つ検索バーとフィルターを使用できます。

![](assets/aep_audiences_list.png)

## Adobe Experience Platform オーディエンスの作成

Campaign StandardでAdobe Experience Platform オーディエンスを直接作成するには、次の手順に従います。

1. Adobe Experience Platform セグメントリストページで、右隅にある「**[!UICONTROL New audience]**」ボタンをクリックします。

   ![](assets/aep_audiences_creation_create.png)

1. セグメントビルダーがワークスペースに表示されます。 Adobe Experience Platformのデータを使用してセグメントを構築し、オーディエンスの構築に活用できます。

1. 右側のペインでセグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. セグメントを正常に作成するには、このセグメントのマーケティング目的に一致する&#x200B;**結合ポリシー**&#x200B;を選択する必要があります。

   設定ペインで、Platformのデフォルトの結合ポリシーが選択されます。 結合ポリシーについて詳しくは、[ セグメントビルダーユーザーガイド ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)の専用セクションを参照してください。

   ![](assets/aep_audiences_mergepolicy.png)

1. オーディエンスで取得するプロファイルを識別するルールを定義します。

   これを行うには、左側のペインから目的の属性やイベントをワークスペースにドラッグし、対応するルールを定義してから&#x200B;**[!UICONTROL Create segment]** ボタンをクリックしてセグメントを保存します（[ セグメントビルダーの使用](../../integrating/using/aep-using-segment-builder.md)を参照）。

   ![](assets/aep_audiences_creation_query.png)

オーディエンスをアクティブ化する準備が整ったので、キャンペーンのターゲットとして使用できます（[Adobe Experience Platform オーディエンスのターゲティング ](../../integrating/using/aep-targeting-audiences.md)を参照）。

## オーディエンスの編集

オーディエンスを編集するには、オーディエンスを開き、セグメントビルダーインターフェイス内で必要に応じてルールを変更します（[ セグメントビルダーの使用](../../integrating/using/aep-using-segment-builder.md)を参照）。

変更が完了したら、**[!UICONTROL Save segment]** ボタンをクリックしてオーディエンスを更新します。

![](assets/aep_audiences_editing.png)
