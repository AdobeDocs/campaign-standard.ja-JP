---
title: トラブルシューティング
description: リソースを共有する際の問題のトラブルシューティング方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 18%

---

# トラブルシューティング{#troubleshooting}

Audience ManagerまたはPeopleコアサービスとの統合を使用中にエラーが発生する場合があります。

この場合、次の要素が正しく設定されていることを確認してください。

* **外部アカウント**

   **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;で、次の外部S3アカウントが正しく設定されていることを確認します。 プロビジョニング中に、前述のS3サーバーが設定されている必要があります。

   * **[!UICONTROL importSharedAudience]**:オーディエンスのインポート専用のS3アカウント。
   * **[!UICONTROL exportSharedAudience]**:オーディエンスのエクスポート専用のS3アカウント。

* **共有データソース**

   **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、共有データソースが正しく設定されていることを確認します。

   **[!UICONTROL Priority]** は、複数のデータソースを定義している場合に使用します。優先度は、定義された順序で受け取ったエイリアスと照合するために使用されるデータソースを決定します。 **[!UICONTROL Priority]** は、トリガー実装にのみ必要です。

   紐付けキーが正しいことを確認します。 オーディエンスのエクスポートおよびインポートに使用される、このフィールドのハッシュ/暗号化された値です。

   宣言済みIDをハッシュまたは暗号化する場合は、Webサイトで同じパラメーター/暗号化アルゴリズムが使用されていることを確認します。

   1つの暗号化アルゴリズムのみがサポートされます。PKCSパディングを使用した、128、192、または256ビットのキーサイズのCBCモードのAES。

   AES暗号化アルゴリズムを選択した場合は、次の追加フィールドを正しく設定する必要があります。

   * **AESの** 暗号化キー
   * **AESの暗号化IV** （初期化ベクトル）
   * **チャネル** （Eメール/SMS/その他）:このフィールドでは、EメールアドレスとSMS番号を直接復号化できます。紐付けキーが&#x200B;**Channel**&#x200B;フィールドの設定と一致することを確認します。 「その他」を選択した場合、この特定の復号化は発生せず、紐付けキーを使用してデータを紐付けします。

   Experience Cloudワークフローが停止または一時停止したので、テクニカルオーディエンスが共有されない可能性があります。 データソースの「**[!UICONTROL Show ImportShared Audience workflow]**」オプションを直接クリックして、**[!UICONTROL Import shared audience]**&#x200B;ワークフローにアクセスします。

People コアサービス経由でオーディエンスを共有したり、オーディエンスをインポートしたりすると、データが一部失われることがあります。ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションに紐付けることができたレコードだけが転送されます。Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。
