---
solution: Campaign Standard
product: campaign
title: マッピングのアクティベーション
description: データマッピングをアクティブにする方法を説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---


# マッピングのアクティベーション {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platformデータコネクタは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

マッピングの定義が完了したら、マッピングを公開できます。 導入手順の後、Campaign StandardとAdobe Experience Platform間のデータ・レプリケーションが自動的に開始されます。 **[!UICONTROL Stop]**&#x200B;ボタンをクリックすると、いつでもレプリケーションを停止できます。

マッピングの変更に応じて、すべてのレコードをAdobe Experience Platformに再送信するよう選択できます。

![](assets/aep_publishmapping.png)

配置タイルから、パブリケーションログにアクセスし、ログをエクスポートできます。

![](assets/aep_publog.png)

**[!UICONTROL Export jobs]**&#x200B;タブで、パブリッシュされたマッピングの書き出しジョブを監視できます。

![](assets/aep_jobstatus.png)

すべてのデータ書き出しジョブを監視する場合は、**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;メニューに移動します。

![](assets/aep_statusmapping.png)

データ取り込みジョブのステータスは次のとおりです。

* **[!UICONTROL Created]**:データ取り込みジョブが作成され、データ取り込みが進行中です。
* **[!UICONTROL Failed]**:データ取り込みジョブが失敗しました。理由フィールドには、失敗の理由が表示されます。 失敗は一時的なものでも、永久的なものでもかまいません。 一時的なエラーが発生した場合は、設定された間隔の後に新しい取り込みジョブが作成されます。 トラブルシューティングの最初の手順として、ユーザーは失敗の理由フィールドを確認できます。 理由によってユーザーがAdobe Experience PlatformUIにリダイレクトされた場合、ユーザーはAdobe Experience Platformにログインし、データセット内のバッチステータスを確認して、正確な失敗理由を判断できます。
* **[!UICONTROL Uploaded]**:まず、バッチをAdobe Experience Platformで作成し、次に、データをバッチに取り込む。バッチIDフィールドには、Adobe Experience PlatformのバッチのバッチIDが表示されます。 また、Adobe Experience Platformはバッチに対する後の検証も実行します。 バッチは、Adobe Experience Platformが検証後の手順を完了するまで、最初にアップロード済みとしてマークされます。 ジョブは、アップロード後にバッチのステータスをAdobe Experience Platformにポーリングし続けます。 バッチは、Adobe Experience Platformでの検証後、失敗または成功状態にすることができます。
* **[!UICONTROL Success]**:バッチがAdobe Experience Platformにアップロードされた後、設定された間隔の後にジョブのステータス（プラットフォームでの後処理の検証）がチェックされます。ステータス「Success」により、Adobe Experience Platformでのデータの取り込みが成功していることが確認されました。

マッピングを公開すると、次の検証エラーが表示される場合があります。

![](assets/aep_datamapping_ccpa.png)

これは、使用しているXDMスキーマが、プライバシー管理に関連する最新のXDMフィールドで更新されておらず、非推奨の「ccpa」 XDMフィールドが引き続き含まれている場合に発生します。

XDMスキーマを更新するには、次の手順に従います。

1. XDMマッピングページにあるリンクを使用して、Adobe Experience Platformのデータセットに移動します。

1. XDMスキーマに移動します。

1. スキーマ追加に対する&#x200B;**[!UICONTROL Profile Privacy]**&#x200B;ミックスインです。

   ![](assets/aep_datamapping_privacyfield.png)

1. スキーマを保存してから、マッピングの公開を再試行してください。 これでパブリケーションが渡されます。

   ![](assets/aep_save_mapping.png)
