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
source-git-commit: c2ed4b3c85ceef3b604a8f68d924c7e5d9fad900

---


# マッピングの有効化 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは、現在ベータ版です。この機能は、予告なく頻繁にアップデートされる場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 アドビカスタマーケアにお問い合わせの際は、アドビカスタマーケアにご連絡ください。

マッピングの定義が完了したら、マッピングを公開できます。 デプロイメント手順の後、Campaign StandardとAdobe Experience Platform間のデータレプリケーションが自動的に開始されます。 ボタンをクリックすると、いつでもレプリケーションを停止でき **[!UICONTROL Stop]** ます。

マッピングの変更に応じて、すべてのレコードをAdobe Experience Platformに再送信するように選択できます。

![](assets/aep_publishmapping.png)

配置タイルから、パブリケーションログにアクセスし、ログをエクスポートできます。

![](assets/aep_publog.png)

タブで、公開済みマッピングの書き出しジョブを監視でき **[!UICONTROL Export jobs]** ます。

![](assets/aep_jobstatus.png)

すべてのデータ書き出しジョブを監視するには、// **[!UICONTROL Administration]** / **[!UICONTROL Development]** メニューに移動し **[!UICONTROL Platform]****[!UICONTROL Status of data export to platform]** ます。

![](assets/aep_statusmapping.png)

データ取り込みジョブのステータス：

* **[!UICONTROL Created]**: データ取り込みジョブが作成され、データ取り込みが進行中です。
* **[!UICONTROL Failed]**: データ取り込みジョブが失敗しました。 理由フィールドには、失敗の理由が表示されます。 失敗は一時的なものでも、永久的なものでもかまいません。 一時的なエラーが発生した場合は、設定された間隔の後に新しい取り込みジョブが作成されます。 トラブルシューティングの最初の手順として、ユーザーは失敗の理由フィールドを確認できます。 理由によってユーザーがAdobe Experience Platform UIにリダイレクトされた場合、ユーザーはAdobe Experience Platformにログインし、データセット内のバッチステータスを確認して、正確な失敗理由を判断できます。
* **[!UICONTROL Uploaded]**: バッチは最初にAdobe Experience Platformで作成され、次にデータがバッチに取り込まれます。 バッチIDフィールドには、Adobe Experience Platform内のバッチのバッチIDが表示されます。 また、Adobe Experience Platformは、バッチに対する後の検証も実行します。 バッチは、Adobe Experience Platformが検証後の手順を完了するまで、最初にアップロード済みとしてマークされます。 ジョブは、アップロード後もAdobe Experience Platformのステータスをポーリングし続けます。 バッチは、Adobe Experience Platformでの検証後、「失敗」または「成功」の状態になります。
* **[!UICONTROL Success]**: バッチがAdobe Experience Platformにアップロードされた後、設定された間隔の後にジョブのステータス（プラットフォームでの後検証）がチェックされます。 ステータス「成功」により、Adobe Experience Platformでデータが正常に取り込まれたことが確認されました。
