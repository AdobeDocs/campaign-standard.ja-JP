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
>Adobe Experience Platform Data Connectorは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

マッピングの定義が完了したら、マッピングを公開できます。 デプロイメント手順の後、Campaign StandardとAdobe Experience Platform間のデータレプリケーションが自動的に開始されます。 **[!UICONTROL Stop]**&#x200B;ボタンをクリックすれば、いつでもレプリケーションを停止できます。

マッピングの変更に応じて、すべてのレコードをAdobe Experience Platformに再送信するように選択できます。

![](assets/aep_publishmapping.png)

デプロイメントタイルから、パブリッシュログにアクセスし、ログをエクスポートできます。

![](assets/aep_publog.png)

「**[!UICONTROL Export jobs]**」タブで、公開済みマッピングの書き出しジョブを監視できます。

![](assets/aep_jobstatus.png)

すべてのデータ書き出しジョブを監視する場合は、 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;メニューに移動します。

![](assets/aep_statusmapping.png)

データ取り込みジョブのステータスは次のとおりです。

* **[!UICONTROL Created]**:データ取り込みジョブが作成され、データ取り込みが進行中です。
* **[!UICONTROL Failed]**:データ取り込みジョブが失敗しました。理由フィールドには、失敗の理由が表示されます。 エラーは、一時的または永続的に発生する場合があります。 一時的なエラーが発生した場合、設定された間隔の後に新しい取り込みジョブが作成されます。 トラブルシューティングの最初の手順として、ユーザーは失敗の理由フィールドを確認できます。 理由がユーザーをAdobe Experience Platform UIにリダイレクトする場合、ユーザーはAdobe Experience Platformにログインし、データセット内のバッチステータスを確認して、エラーの正確な理由を特定できます。
* **[!UICONTROL Uploaded]**:最初にバッチがAdobe Experience Platformで作成され、データがバッチに取り込まれます。「バッチID 」フィールドには、Adobe Experience PlatformでのバッチのバッチIDが表示されます。 Adobe Experience Platformは、バッチに対して後処理の検証も実行します。 Adobe Experience Platformが検証後の手順を完了するまで、バッチは最初にアップロード済みとしてマークされます。 ジョブは、アップロード後にバッチのステータスに関するAdobe Experience Platformをポーリングし続けます。 バッチは、Adobe Experience Platformでの失敗または成功状態の後検証に移動できます。
* **[!UICONTROL Success]**:バッチがAdobe Experience Platformにアップロードされた後、設定された間隔の後にジョブのステータス（platformでの後検証）がチェックされます。「成功」ステータスにより、Adobe Experience Platformでのデータの取り込みが成功したことが特定されました。

場合によっては、マッピングを公開する際に、以下の検証エラーが発生することがあります。

![](assets/aep_datamapping_ccpa.png)

これは、使用しているXDMスキーマが、プライバシー管理に関連する最新のXDMフィールドで更新されておらず、非推奨の「ccpa」XDMフィールドが含まれている場合に発生します。

XDMスキーマを更新するには、次の手順に従います。

1. XDMマッピングページに存在するリンクを使用して、Adobe Experience Platformのデータセットに移動します。

1. XDMスキーマに移動します。

1. **[!UICONTROL Profile Privacy]** mixinをスキーマに追加します。

   ![](assets/aep_datamapping_privacyfield.png)

1. スキーマを保存してから、マッピングの公開を再試行します。 これでパブリケーションがパスします。

   ![](assets/aep_save_mapping.png)
