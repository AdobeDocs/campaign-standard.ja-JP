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

Audience Managerまたは People コアサービスとの統合を使用中にエラーが発生する場合があります。

この場合、次の要素が正しく設定されていることを確認します。

* **外部アカウント**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;を設定し、次の外部 S3 アカウントが正しく設定されていることを確認します。 前述の S3 サーバーは、プロビジョニング中に設定されている必要があります。

   * **[!UICONTROL importSharedAudience]**:オーディエンスのインポート専用の S3 アカウント。
   * **[!UICONTROL exportSharedAudience]**:オーディエンスのエクスポート専用の S3 アカウント。

* **共有データソース**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**」で、共有データソースが正しく設定されていることを確認します。

   **[!UICONTROL Priority]** は、複数のデータソースを定義している場合に使用されます。 優先度は、定義された順序で受け取ったエイリアスと照合するために使用されるデータソースを決定します。 **[!UICONTROL Priority]** は、トリガー実装にのみ必要です。

   紐付けキーが正しいことを確認します。 オーディエンスの書き出しとインポートに使用される、このフィールドのハッシュ/暗号化された値です。

   宣言済み ID をハッシュまたは暗号化する場合は、Web サイトで同じパラメーター/暗号化アルゴリズムが使用されていることを確認します。

   1 つの暗号化アルゴリズムのみがサポートされます。PKCS パディングを使用した、キーサイズが 128、192、または 256 ビットの CBC モードの AES。

   AES 暗号化アルゴリズムを選択した場合は、次の追加フィールドを正しく設定する必要があります。

   * **暗号化キー** （AES 用）
   * **暗号化 IV** AES 用（初期化ベクトル）
   * **チャネル** （電子メール/SMS/その他）:このフィールドでは、E メールアドレスと SMS 番号を直接復号化できます。 紐付けキーが **チャネル** フィールドに入力します。 「その他」を選択した場合、この特定の復号化はおこなわれず、紐付けキーを使用してデータを紐付けします。

   Experience Cloudワークフローが停止または一時停止したので、テクニカルオーディエンスが共有されない可能性があります。 次にアクセス： **[!UICONTROL Import shared audience]** 直接クリックしてワークフローを作成 **[!UICONTROL Show ImportShared Audience workflow]** 」オプションを使用して、データソース内で設定します。

People コアサービス経由でオーディエンスを共有したり、オーディエンスをインポートしたりすると、データが一部失われることがあります。ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションに紐付けることができたレコードだけが転送されます。Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。
