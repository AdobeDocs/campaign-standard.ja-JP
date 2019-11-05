---
title: トラブルシューティング
description: リソースを共有する際の問題のトラブルシューティング方法を説明します。
page-status-flag: 非活性化の
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとオーディエンスの管理者または人々のコアサービスの利用
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# トラブルシューティング{#troubleshooting}

Audience ManagerまたはPeopleコアサービスとの統合を使用中にエラーが発生する場合があります。

この場合、次の要素が正しく設定されていることを確認します。

* **外部アカウント**

   &gt; **[!UICONTROL Administration]** &gt;で、 **[!UICONTROL Application settings]** 次の外部S3ア **[!UICONTROL External accounts]**&#x200B;カウントが正しく設定されていることを確認します。 前述のS3サーバは、プロビジョニング中に設定する必要があります。

   * **[!UICONTROL importSharedAudience]**:オーディエンスのインポート専用のS3アカウント。
   * **[!UICONTROL exportSharedAudience]**:オーディエンスの書き出し専用のS3アカウント。

* **共有データソース**

   // **[!UICONTROL Administration]** で、共 **[!UICONTROL Application settings]** 有デ **[!UICONTROL Shared Data Sources]**&#x200B;ータソースが正しく設定されていることを確認します。

   **[!UICONTROL Priority]** は、複数のデータソースを定義している場合に使用します。 優先度は、定義された順序で受け取ったエイリアスとの照合に使用するデータソースを決定します。 **[!UICONTROL Priority]** は、Triggers実装でのみ必要です。

   調整キーが正しいことを確認します。 オーディエンスの書き出しおよび読み込みに使用される、このフィールドのハッシュ化/暗号化された値です。

   宣言済みIDをハッシュまたは暗号化する場合は、Webサイトで同じパラメーター/暗号化アルゴリズムが使用されていることを確認します。

   1つの暗号化アルゴリズムのみがサポートされます。キーサイズが128、192または256ビットのCBCモードのAES。PKCSパディングを使用します。

   AES暗号化アルゴリズムを選択する場合は、次の追加フィールドを正しく設定する必要があります。

   * **Encryption Key** for AES
   * **AES用のEncryption IV** (Initialization Vector)
   * **チャネル** （電子メール/SMS/その他）:このフィールドでは、電子メールアドレスとSMS番号を直接復号化できます。 調整キーが「チャネル」フィールドの設定と一致することを確認 **します** 。 「その他」を選択した場合、この特定の復号は行われず、調整キーを使用してデータが調整されます。
   技術ワークフローが停止または一時停止したため、Experience cloudオーディエンスが共有されない場合があります。 データソースのオ **[!UICONTROL Import shared audience]** プションを直接クリックして、ワ **[!UICONTROL Show ImportShared Audience workflow]** ークフローにアクセスします。

People コアサービス経由でオーディエンスを共有したり、オーディエンスをインポートしたりすると、データが一部失われることがあります。ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションに紐付けることができたレコードだけが転送されます。Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。
