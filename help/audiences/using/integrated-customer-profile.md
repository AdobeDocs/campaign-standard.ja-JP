---
title: Integrated Customer Profile
description: あらゆる顧客インタラクションを単一画面で追跡：Adobe Campaignと連携した顧客プロファイルは、顧客ライフサイクル全体を通じて更新されます。
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
feature: Profiles
role: User
level: Beginner
exl-id: cf3c6408-7fa0-423a-b34b-f4fee771fb47
TQID: 'https://experienceleague.adobe.com/a-v47cX0DxN6dzLQs-r4e2yMajLD6GHIVXXEX9Ol-lY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
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
topic_v2:
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 41%
---
# Integrated Customer Profile{#integrated-customer-profile}

統合顧客プロファイルは、データベースの連絡先ごとに使用できます。 このマーケティング履歴では、顧客との連絡に関するあらゆる関連マーケティング情報が 1 つのビューにまとめられます。 その結果、連絡先情報、受信したメール、トラッキングログ、購読、購読解除など、すべてのデジタル動作、オンラインおよびオフラインのトランザクションに一元的にアクセスできます。

統合顧客プロファイルにアクセスする手順は次のとおりです。

1. Adobe Campaignのホームページで、「**[!UICONTROL Customer profiles]**」カードまたは「**プロファイル**」タブをクリックして、プロファイルリストを表示します。

1. 特定のフィールドに基づいてプロファイルを検索するには、検索ペインを開き、検索を実行するフィールドを選択します。


   ![](assets/profile-search.png)

1. 検索する値を指定し、Enter キーを押します。

   >[!NOTE]
   >
   >検索は、電子メール、名、姓のフィールド、およびリソースの拡張時に追加されたカスタムフィールドに基づいて実行できることに注意してください。
   >
   >検索では大文字と小文字が区別され、プレフィックスに対してのみ実行されます。 例えば、姓の最後の文字を使用してプロファイルを検索することはできません。

1. 連絡先を選択してプロファイルを開きます。

   ![](assets/mkt_hist_access.png)

その結果、この連絡先の&#x200B;**マーケティング履歴**&#x200B;にアクセスできます。

プロファイルに関する主要な情報は、イベントのリストと共に、このページで収集されます。

リスト内のイベントをクリックして開きます。送信されたメッセージまたはプロファイルが購読したサービスにアクセスできます。

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>マーケティング履歴は、Adobe Campaign Standard API を使用してアクセスすることもできます。 詳しくは、[該当するドキュメント](../../api/using/interacting-with-marketing-history.md)を参照してください。
