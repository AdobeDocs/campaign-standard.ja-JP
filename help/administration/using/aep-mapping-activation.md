---
title: マッピングの有効化
description: データマッピングをアクティブにする方法を説明します。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 57b87896281efa7dd1e6a612926f59061a0fdcb8

---


# マッピングの有効化 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

マッピングの定義が完了したら、マッピングを公開できます。 デプロイメント手順の後、データとAdobe Experience Platformの間のCampaign Standard複製が自動的に開始されます。 ボタンをクリックすると、いつでも複製を停止でき **[!UICONTROL Stop]** ます。

マッピングの変更に応じて、すべてのレコードをAdobe Experience Platformに再送信するように選択できます。

![](assets/aep_publishmapping.png)

展開タイルから、パブリケーションログにアクセスし、ログをエクスポートできます。

![](assets/aep_publog.png)

タブで、公 **[!UICONTROL Export jobs]** 開されたマッピングの書き出しジョブを監視できます。

![](assets/aep_jobstatus.png)

すべてのデータ書き出しジョブを監視する場合は、//メニ **[!UICONTROL Administration]** ューに **[!UICONTROL Development]** 移動 **[!UICONTROL Platform]** しま **[!UICONTROL Status of data export to platform]** す。

![](assets/aep_statusmapping.png)

データ取り込みジョブのステータス：

* **[!UICONTROL Created]**:データ取り込みジョブが作成され、データ取り込みが進行中です。
* **[!UICONTROL Failed]**:データ取り込みジョブが失敗しました。 理由フィールドには、失敗の理由が表示されます。 障害は一時的なものでも永久的なものでもかまいません。 一時的な障害が発生した場合は、設定された間隔の後に新しい取り込みジョブが作成されます。 トラブルシューティングの最初の手順として、ユーザーは失敗の理由フィールドを確認できます。 理由がユーザーをAdobe Experience Platform UIにリダイレクトする場合、ユーザーはAdobe Experience Platformにログインし、データセット内のバッチステータスを確認して、正確な失敗理由を判断できます。
* **[!UICONTROL Uploaded]**:バッチは、最初にAdobe Experience Platformで作成され、次にデータがバッチに取り込まれます。 「バッチID」フィールドには、Adobe Experience Platform内のバッチのバッチIDが表示されます。 また、Adobe Experience Platformは、バッチに対する後の検証も実行します。 バッチは、Adobe Experience Platformが検証後の手順を完了するまで、最初にアップロード済みとしてマークされます。 ジョブは、アップロード後に、Adobe Experience Platformでバッチのステータスをポーリングし続けます。 バッチは、Adobe Experience Platformでの検証後、「失敗」または「成功」状態になります。
* **[!UICONTROL Success]**:バッチがAdobe Experience Platformにアップロードされた後、設定された間隔の後にジョブのステータス（プラットフォームでの検証後）がチェックされます。 ステータス「成功」により、Adobe Experience Platformでデータが正常に取り込まれたことが確認されました。
