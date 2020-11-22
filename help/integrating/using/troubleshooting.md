---
solution: Campaign Standard
product: campaign
title: トラブルシューティング
description: リソースを共有する際の問題のトラブルシューティング方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 18%

---


# トラブルシューティング{#troubleshooting}

Audience ManagerまたはPeopleコアサービスとの統合を使用中にエラーが発生する場合があります。

この場合、次の要素が正しく設定されていることを確認します。

* **外部アカウント**

   > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]****[!UICONTROL External accounts]**>で、次の外部S3アカウントが正しく設定されていることを確認します。 前述のS3サーバは、プロビジョニング時に設定する必要があります。

   * **[!UICONTROL importSharedAudience]**:オーディエンスの読み込み専用のS3アカウント。
   * **[!UICONTROL exportSharedAudience]**:オーディエンスの書き出し専用のS3アカウント。

* **共有データソース**

   > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;で、共有データソースが正しく設定されていることを確認します。

   **[!UICONTROL Priority]** は、複数のデータソースを定義している場合に使用します。 優先度は、定義された順序で受け取ったエイリアスとの照合に使用されるデータソースを決定します。 **[!UICONTROL Priority]** は、Triggers実装でのみ必要です。

   紐付けキーが正しいことを確認します。 オーディエンスの書き出しと読み込みに使用される、このフィールドのハッシュ/暗号化された値です。

   宣言済みIDをハッシュまたは暗号化する場合は、Webサイトで同じパラメーター/暗号化アルゴリズムが使用されていることを確認します。

   次の暗号化アルゴリズムは1つのみサポートされます。キーサイズが128、192または256ビットのCBCモードのAES。PKCSパディングを使用。

   AES暗号化アルゴリズムを選択した場合は、次の追加フィールドを正しく設定する必要があります。

   * **AES用暗号化キー**
   * **AES用のEncryption IV** (Initialization Vector)
   * **チャネル** （電子メール/SMS/その他）:このフィールドでは、電子メールアドレスとSMS番号を直接復号化できます。 紐付けキーが **チャネルフィールドの設定と一致していることを確認します** 。 「その他」を選択した場合、この特定の復号化は行われず、紐付けキーを使用してデータを調整します。

   テクニカルワークフローが停止または一時停止されたため、Experience Cloudオーディエンスを共有できない可能性があります。 データソースのオプションを直接クリックして、 **[!UICONTROL Import shared audience]** ワークフローにアクセスし **[!UICONTROL Show ImportShared Audience workflow]** ます。

People コアサービス経由でオーディエンスを共有したり、オーディエンスをインポートしたりすると、データが一部失われることがあります。ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションに紐付けることができたレコードだけが転送されます。Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。
