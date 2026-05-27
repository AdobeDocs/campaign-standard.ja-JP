---
title: 統合の問題のトラブルシューティング
description: リソースを共有する際の問題をトラブルシューティングする方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
TQID: https://experienceleague.adobe.com/Im9-z6yuesgiE6sMO-dM9WgPbty2C9d-PWCv5AE-kNY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 350
ht-degree: 18%

---

# トラブルシューティング{#troubleshooting}

Audience ManagerまたはPeople コアサービスとの統合中にエラーが発生する場合があります。

この場合は、次の要素が正しく設定されていることを確認してください。

* **外部アカウント**

  **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;で、次の外部S3 アカウントが正しく設定されていることを確認してください。 前述のS3 サーバーは、プロビジョニング中に設定する必要があります。

   * **[!UICONTROL importSharedAudience]**: オーディエンスの読み込み専用のS3 アカウント。
   * **[!UICONTROL exportSharedAudience]**: オーディエンスの書き出し専用のS3 アカウント。

* **共有データソース**

  **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、共有データソースが正しく設定されていることを確認します。

  **[!UICONTROL Priority]**&#x200B;は、複数のデータソースが定義されている場合に使用されます。 優先度は、定義された順序で受信したエイリアスと一致するために使用するデータソースを決定します。 **[!UICONTROL Priority]**&#x200B;は、トリガーの実装にのみ必要です。

  紐付けキーが正しいことを確認します。 オーディエンスの書き出しと読み込みに使用される、このフィールドのハッシュ化または暗号化された値です。

  宣言されたIDのハッシュまたは暗号化の場合は、同じパラメーター/暗号化アルゴリズムがWeb サイトで使用されていることを確認してください。

  1つの暗号化アルゴリズムのみがサポートされています。キーサイズが128、192または256 ビットのCBC モードのAESと、PKCS パディングです。

  AES暗号化アルゴリズムを選択した場合、次の追加フィールドを正しく設定する必要があります。

   * AESの&#x200B;**暗号化キー**
   * AESの&#x200B;**暗号化IV** （初期化ベクター）
   * **チャネル** （電子メール/SMS/その他）：このフィールドを使用すると、電子メールアドレスとSMS番号を直接復号できます。 紐付けキーが&#x200B;**チャネル** フィールドの設定と一致していることを確認してください。 「その他」を選択すると、この特定の復号化は行われず、紐付けキーがデータの紐付けに使用されます。

  テクニカルワークフローが停止または一時停止したため、Experience Cloud オーディエンスが共有されない可能性があります。 データソースの「**[!UICONTROL Show ImportShared Audience workflow]**」オプションを直接クリックして、**[!UICONTROL Import shared audience]** ワークフローにアクセスします。

People コアサービス経由でオーディエンスを共有したり、オーディエンスをインポートしたりすると、データが一部失われることがあります。 ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションに紐付けることができたレコードだけが転送されます。 Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。
