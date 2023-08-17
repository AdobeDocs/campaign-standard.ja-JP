---
title: マッピングのアクティベーション
description: データマッピングを有効化する方法を説明します
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d7ca0de6-7f7b-4e31-877c-909d962c5f53
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# マッピングのアクティベーション {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector は現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

マッピング定義が完了したら、マッピングを公開できます。 デプロイメント手順の後、Campaign StandardとAdobe Experience Platform間のデータレプリケーションが自動的に開始されます。 いつでも、 **[!UICONTROL Stop]** 」ボタンをクリックします。

マッピングの変更に応じて、すべてのレコードをAdobe Experience Platformに再送信するように選択できます。

![](assets/aep_publishmapping.png)

デプロイメントタイルから、パブリッシュログにアクセスし、ログを書き出すことができます。

![](assets/aep_publog.png)

Adobe Analytics の **[!UICONTROL Export jobs]** 「 」タブでは、パブリッシュ済みマッピングの書き出しジョブを監視できます。

![](assets/aep_jobstatus.png)

すべてのデータ書き出しジョブを監視する場合は、次に移動します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** メニュー。

![](assets/aep_statusmapping.png)

データ取り込みジョブのステータスは次のとおりです。

* **[!UICONTROL Created]**：データ取り込みジョブが作成され、データ取り込みが進行中です。
* **[!UICONTROL Failed]**：データ取り込みジョブが失敗しました。 「理由」フィールドに、失敗の理由が表示されます。 エラーは、一時的または永久的に発生する場合があります。 一時的なエラーが発生した場合、設定された間隔で新しい取り込みジョブが作成されます。 トラブルシューティングの最初の手順として、ユーザーは失敗の理由フィールドを確認できます。 理由によってユーザーがAdobe Experience Platform UI にリダイレクトされた場合、ユーザーはAdobe Experience Platformにログインし、データセットでバッチステータスを確認して、エラーの正確な理由を特定できます。
* **[!UICONTROL Uploaded]**：バッチは、最初にAdobe Experience Platformで作成され、次にデータがバッチに取り込まれます。 「バッチ ID 」フィールドに、Adobe Experience Platformでのバッチのバッチ ID が表示されます。 また、Adobe Experience Platformは、バッチに対して後処理の検証を実行します。 Adobe Experience Platformが検証後の手順を完了するまで、バッチはまずアップロード済みとしてマークされます。 ジョブは、アップロード後にバッチのステータスに関するAdobe Experience Platformをポーリングし続けます。 バッチは、Adobe Experience Platformで検証後、「失敗」または「成功」状態になる場合があります。
* **[!UICONTROL Success]**：バッチがAdobe Experience Platformにアップロードされた後、設定された間隔の後にジョブのステータス（platform での検証後）がチェックされます。 「成功」ステータスにより、Adobe Experience Platformでのデータの取り込みが成功していることが示されました。

マッピングを公開する際に、以下の検証エラーが発生する場合があります。

![](assets/aep_datamapping_ccpa.png)

これは、使用している XDM スキーマが、プライバシー管理に関連する最新の XDM フィールドで更新されておらず、非推奨の「ccpa」XDM フィールドが含まれている場合に発生します。

XDM スキーマを更新するには、次の手順に従います。

1. XDM マッピングページに存在するリンクを使用して、Adobe Experience Platformのデータセットに移動します。

1. XDM スキーマに移動します。

1. 次を追加： **[!UICONTROL Profile Privacy]** スキーマへの mixin。

   ![](assets/aep_datamapping_privacyfield.png)

1. スキーマを保存してから、マッピングの公開を再試行します。 これで、パブリケーションが渡されます。

   ![](assets/aep_save_mapping.png)
