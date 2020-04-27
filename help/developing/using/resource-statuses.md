---
title: リソースのステータス
description: 発行状態に応じて異なるリソースのステータスを見つけます。
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# リソースのステータス{#resource-statuses}

リソースのステータスは、発行またはアクティベーションのステータスによって異なります。

画面にこれらのステータスを表示する列が2つあり **[!UICONTROL Custom resources]** ます。

![](assets/schema_colonne_1.png)

**パブリケーションのステータス**

* **ドラフト**:リソースが作成または再ドラフトされたとき。 対応するAPIと共にデータベーステーブルを作成するには、リソースを再公開する必要があります。 リソースの再ドラフト中は、発行手順の後に自動的に非アクティブになります。
* **再ドラフトの保留**:資源が再起草された。 再ドラフト処理は次のパブリケーションで行われます。 再作図は元に戻せません。 ユーザに通知する警告メッセージがいくつか表示されます。このメッセージは、再作図時とパブリッシュの準備時の両方に表示されます。

   再作図の詳細については、「リソースの削除」を [参照してください](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >このオ **[!UICONTROL Cancel re-draft]** プションは、再ドラフトするリソースに、「発行済み」ステータスの他のリソースを経由するリンクが含まれている場合に使用できます。 このオプションを使用すると、「再ドラフト」プロセスを元に戻すことができます。 その後、カスタムリソースは元のステータスに戻ります。

* **発行済み**:リソースが公開されました。 リソースが最後の変更日より後に変更された場合は、最新の変更を考慮してリソースを再発行するように促すメッセージが表示されます。

このフィ **[!UICONTROL Do not publish latest modifications]** ールドを使用すると、今後のパブリケーションで変更が考慮されなくなります。

このフィールドは、カスタムリソース定義で設定できます。
