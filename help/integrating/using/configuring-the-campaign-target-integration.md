---
title: Campaign-Target 統合の設定
description: Adobe target統合を設定して、Adobe Campaignで動的コンテンツを使用する方法を説明します。
page-status-flag: 非活性化の
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとターゲットの連携
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Campaign-Target 統合の設定{#configuring-the-campaign-target-integration}

Adobe CampaignとAdobe targetの統合により、配信に動的なコンテンツを挿入できます。

設定は、Adobe targetとの統合機能を使用するために、Adobe Campaignで最初に必要となり、機能管理者が管理する必要があります。

この手順では、次の要素が必要です。

* Adobe Experience cloudテナント
* Adobe targetテナント
* Adobe Campaign との接続を確立するために指定された Adobe Target ローボックス

1. アドバンスメニューで、左上隅のAdobe Campaignロゴを使用して、//を選 **[!UICONTROL Administration]** 択し **[!UICONTROL Application settings]** ます **[!UICONTROL Options]**。
1. Adobe targetのサーバーとテナントのオプションを設定するには、それに応じて以下のフィールドに入力します。

   * **[!UICONTROL TNT_TenantName]**:adobe targetテナントの名前。 This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**:統合に使用するAdobe targetサーバー。 このオプションは既にデフォルトで提供されています。 This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. 例：tt.omtrdc.net/m2 ****.
   ![](assets/tar_options.png)

これで、ユーザーはAdobe targetを使用した配信に動的な画像を追加できるようになりました。
