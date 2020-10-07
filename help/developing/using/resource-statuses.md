---
title: リソースのステータス
description: 発行状態に応じて、様々なリソースのステータスを特定します。
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# リソースのステータス{#resource-statuses}

発行またはアクティベーションの状態によっては、リソースの状態が異なる場合があります。

これらのステータスを **[!UICONTROL Custom resources]** 画面に表示するための列は2つあります。

![](assets/schema_colonne_1.png)

**パブリケーションのステータス**

* **ドラフト**:リソースが作成または再ドラフトされたとき。 対応するAPIだけでなくデータベーステーブルも作成するには、リソースを再公開する必要があります。 リソースの再ドラフト中は、発行手順の後、自動的に非アクティブになります。
* **保留中の再ドラフト**:資源は再起草された。 再ドラフト処理は次のパブリケーションで行われます。 再作図は元に戻せません。 ユーザに通知する警告メッセージがいくつか表示されます。このメッセージは、再作図とパブリッシュの準備の両方で表示されます。

   再作図の詳細については、「リソースの [削除](../../developing/using/deleting-a-resource.md)」を参照してください。

   >[!NOTE]
   >
   >この **[!UICONTROL Cancel re-draft]** オプションは、再ドラフトするリソースに、「発行済み」ステータスの他のリソースを経由するリンクが含まれている場合に利用できます。 このオプションを使用すると、「再ドラフト」プロセスを元に戻すことができます。 その後、カスタムリソースは元のステータスに戻ります。

* **発行済み**:リソースが公開されました。 リソースが最終変更日より後に変更された場合は、最新の変更を考慮してリソースを再発行するように勧めるメッセージが表示されます。

この **[!UICONTROL Do not publish latest modifications]** フィールドを使用すると、今後のパブリケーションで変更が考慮されなくなります。

このフィールドは、カスタムリソース定義で設定できます。
