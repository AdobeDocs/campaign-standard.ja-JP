---
title: プロファイルについて
description: 連絡先は、Campaign データベースのプロファイルとして保存され、ライフサイクル全体を通じて更新されます。
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: Profiles
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
TQID: 'https://experienceleague.adobe.com/8netKX93BsN9JxgyckV44tpKK5uPjFMrrnD8F4FCpJM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 74%
---
# プロファイルについて{#about-profiles}

Adobe Campaignでは、作成、読み込み、ターゲティング、アクショントラッキング、更新など、ライフサイクル全体を通じて連絡先を管理できます。連絡先は、姓、名、住所、サブスクリプション、配信など、連絡先にリンクされた情報を含むプロファイルとしてデータベースに保存されます。

>[!NOTE]
>
>プロファイルは、Adobe Campaign Standard の API を使用しても利用できます。 詳しくは、[該当するドキュメント](../../api/using/retrieving-profiles.md)を参照してください。

![](assets/marketing_history.png)

キャンペーンを作成する際に、単純な条件または詳細な条件に従ってプロファイルを選択することで、配信のターゲットを定義できます。 専門的に言えば、プロファイルとは、行動のターゲティング、選定、トラッキングに必要なあらゆる情報を含んだ、データベース内のエントリのことです。

例えば、クライアント、見込み客、ニュースレターを購読する個人、受信者、ユーザー、その他組織応じた単位などがプロファイルになります。 各種のプロファイルを定義するには、[ターゲティングディメンション](../../automating/using/query.md#targeting-dimensions-and-resources)を使用します。
