---
title: 統合に関する問題のトラブルシューティング
description: リソースの共有時の問題のトラブルシューティング方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 18%

---

# トラブルシューティング{#troubleshooting}

Audience Managerまたは People コアサービスとの統合の使用中にエラーが発生する場合があります。

この場合、次の要素が正しく設定されていることを確認します。

* **外部アカウント**

  **[!UICONTROL Administration]**/**[!UICONTROL Application settings]**/**[!UICONTROL External accounts]** で、次の外部 S3 アカウントが正しく設定されていることを確認します。 前述の S3 サーバは、プロビジョニング時に構成する必要があります。

   * **[!UICONTROL importSharedAudience]**：オーディエンスのインポート専用の S3 アカウント。
   * **[!UICONTROL exportSharedAudience]**: オーディエンスの書き出し専用の S3 アカウント。

* **共有データソース**

  **[!UICONTROL Administration]**/**[!UICONTROL Application settings]**/**[!UICONTROL Shared Data Sources]** で、共有データソースが正しく設定されていることを確認します。

  **[!UICONTROL Priority]** は、複数のデータソースを定義している場合に使用します。 優先度は、定義された順序で受信したエイリアスと照合するために使用するデータソースを決定します。 **[!UICONTROL Priority]** は、トリガーの実装にのみ必要です。

  紐付けキーが正しいことを確認します。 オーディエンスの書き出しと読み込みに使用されるのは、このフィールドのハッシュ化/暗号化された値です。

  宣言された ID のハッシュや暗号化を行う場合は、web サイトで同じパラメーター/暗号化アルゴリズムが使用されていることを確認します。

  サポートされている暗号化アルゴリズムは 1 つだけです。キーサイズが 128、192 または 256 ビットで、PKCS パディングを使用する CBC モードの AES。

  AES 暗号化アルゴリズムが選択されている場合、次の追加フィールドを正しく設定する必要があります。

   * AES 用 **暗号化キー**
   * AES の **Encryption IV** （初期化ベクトル）
   * **チャネル** （メール/SMS/その他）：このフィールドでは、メールアドレスと SMS 番号を直接復号化できます。 紐付けキーが「**チャネル**」フィールドの設定と一致することを確認します。 「その他」を選択した場合、この特定の復号化は実行されず、紐付けキーがデータの紐付けに使用されます。

  テクニカルワークフローが停止または一時停止しているので、Experience Cloud オーディエンスが共有されない可能性があります。 データソースの「**[!UICONTROL Import shared audience]**」オプションを直接クリックして、**[!UICONTROL Show ImportShared Audience workflow]** ワークフローにアクセスします。

People コアサービス経由でオーディエンスを共有したり、オーディエンスをインポートしたりすると、データが一部失われることがあります。ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションに紐付けることができたレコードだけが転送されます。Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。
