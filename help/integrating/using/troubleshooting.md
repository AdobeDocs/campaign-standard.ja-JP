---
title: トラブルシューティング
seo-title: トラブルシューティング
description: トラブルシューティング
seo-description: リソースを共有する際の問題のトラブルシューティング方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 1c764dd8- e09f-4e8e-9pcb-88ab3d714284
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- audiences- manager- or- people- core- service
discoiquuid: c28e1d90-8074-4127- a6fc- ed39d69cmdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Troubleshooting{#troubleshooting}

Audience ManagerまたはPeopleコアサービスとの統合中にエラーが発生する可能性があります。

この場合、次の要素が正しく構成されていることを確認してください。

* **外部アカウント**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. 前述のS3サーバーはプロビジョニング中に設定されている必要があります。

   * **[!UICONTROL importSharedAudience]**:オーディエンスの読み込み専用のS3アカウント。
   * **[!UICONTROL exportSharedAudience]**:オーディエンスのエクスポート専用のS3アカウント。

* **共有データソース**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** は、複数のデータソースが定義されている場合に使用します。優先度によって、定義された順序で受け取ったエイリアスとの照合に使用されるデータソースが決定されます。**[!UICONTROL Priority]** は、Triggersの実装にのみ必要です。

   紐付けキーが正しいことを確認します。これは、オーディエンスの書き出しおよび読み込みに使用される、このフィールドのハッシュ/暗号化された値です。

   宣言されたIDのハッシュまたは暗号化の場合、Webサイトで同じパラメーター/暗号化アルゴリズムが使用されていることを確認してください。

   サポートされる暗号化アルゴリズムは1つだけです。CBCモード（128、192または256ビット）のキーサイズ（PKCSパディングを含む）。

   AES暗号化アルゴリズムが選択されている場合、以下の追加フィールドを正しく設定する必要があります。

   * **AESの暗号化キー**
   * **AES for AESのEncryption IV** （初期化ベクトル）
   * **チャネル** （電子メール/SMS/その他）:このフィールドでは、電子メールアドレスとSMS番号を直接復号できます。Make sure that the reconciliation key matches the setting of the **Channel** field. 「その他」を選択すると、この特定の復号化は行われず、紐付けキーを使用してデータが調整されます。
   技術ワークフローが停止または一時停止されているので、Experience Cloudオーディエンスが共有されていない可能性があります。Access the **[!UICONTROL Import shared audience]** workflow by clicking directly the **[!UICONTROL Show ImportShared Audience workflow]** option in your Data source.

Peopleコアサービスを介してオーディエンスを共有したり、オーディエンスをインポートしたりするときに、一部のデータが欠落する可能性があります。プロファイルディメンションとの紐付けが可能なID（「訪問者ID"または「宣言済みID"）のみが転送されます。Adobe Campaignで認識されないPeopleコアサービスセグメントからのIDはインポートされません。
