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
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# マッピングの有効化 {#mapping-activation}

>[!IMPORTANT]
>
>キャンペーン標準データサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

マッピングの定義が完了したら、マッピングを公開できます。 導入手順の後、Campaign StandardとAdobe Experience Platformの間のデータ複製が自動的に開始されます。 ボタンをクリックすると、いつでも複製を停止でき **[!UICONTROL Stop]**ます。

マッピングの変更に応じて、すべてのレコードをAdobe Experience Platformに再送信するように選択できます。

![](assets/aep_publishmapping.png)

配置タイルから、パブリケーションログにアクセスし、ログをエクスポートできます。

![](assets/aep_publog.png)

タブで、公 **[!UICONTROL Export jobs]**開されたマッピングの書き出しジョブを監視できます。

![](assets/aep_jobstatus.png)

すべてのデータエクスポートジョブを監視する場合は、// **[!UICONTROL Administration]**メニ**[!UICONTROL Development]** ューに **[!UICONTROL Platform]**移動し**[!UICONTROL Status of data export to platform]** ます。

![](assets/aep_statusmapping.png)

データ取り込みジョブのステータス：

* **[!UICONTROL Created]**:データ取り込みジョブが作成され、データ取り込みが進行中です。
* **[!UICONTROL Failed]**:データ取り込みジョブが失敗しました。 理由フィールドは、失敗の理由を示します。 失敗は一時的なものでも永久的なものでもかまいません。 一時的な障害が発生した場合は、設定された間隔の後に新しいインジェストジョブが作成されます。 トラブルシューティングの最初の手順として、ユーザーは失敗の理由フィールドを確認できます。 理由によってユーザーがAdobe Experience Platform UIにリダイレクトされる場合、ユーザーはAdobe Experience Platformにログインし、データセット内のバッチステータスを確認して、正確な失敗理由を判断できます。
* **[!UICONTROL Uploaded]**:最初にAdobe Experience Platformでバッチが作成され、データがバッチに取り込まれます。 「バッチID」フィールドには、Adobe Experience Platform内のバッチのバッチIDが表示されます。 また、Adobe Experience Platformは、バッチに対して後処理の検証を実行します。 バッチは、Adobe Experience Platformが後の検証手順を完了するまで、最初にアップロード済みとマークされます。 ジョブは、アップロード後もAdobe Experience Platformでバッチのステータスをポーリングし続けます。 バッチは、Adobe Experience Platformでの検証後、失敗または成功状態のいずれかになります。
* **[!UICONTROL Success]**:バッチがAdobe Experience Platformにアップロードされた後、設定された間隔の後にジョブのステータス（プラットフォームでの検証後）が確認されます。 ステータス「成功」により、Adobe Experience Platformにデータが正常に取り込まれたことが確認されました。
