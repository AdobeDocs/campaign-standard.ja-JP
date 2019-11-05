---
title: リソースのステータス
description: 発行状態に従って、様々なリソースのステータスを見つけます。
page-status-flag: 非活性化の
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# リソースのステータス{#resource-statuses}

リソースのステータスは、発行またはアクティベーションの状態に応じて異なる場合があります。

画面にこれらのステータスを表示する列が2つあり **[!UICONTROL Custom resources]** ます。

![](assets/schema_colonne_1.png)

**パブリケーションのステータス**

* **ドラフト**:リソースが作成または再ドラフトされたとき。 データベーステーブルと対応するAPIを作成するには、リソースを再公開する必要があります。 リソースが再起動中の場合、発行手順に従って自動的に非アクティブになります。
* **再ドラフトの保留**:資源は再起草された。 再ドラフト処理は次のパブリケーションで行われます。 再作図は元に戻せません。 いくつかの警告メッセージは、ユーザに対して、再作図時とパブリッシュの準備時の両方でこの事実を警告するものです。

   再作図の詳細については、「リソースの削除」を [参照してください](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >このオ **[!UICONTROL Cancel re-draft]** プションは、再ドラフトするリソースに、「発行済み」ステータスの他のリソースを経由するリンクが含まれている場合に使用できます。 このオプションを使用すると、「再ドラフト」プロセスを元に戻すことができます。 その後、カスタムリソースは元のステータスに戻ります。

* **発行済**:リソースが公開されています。 リソースが最後の変更日より後に変更された場合は、最新の変更を考慮して再発行するようにユーザーに求めるメッセージが表示されます。

このフィ **[!UICONTROL Do not publish latest modifications]** ールドを使用すると、今後のパブリケーションで変更が考慮されなくなります。

このフィールドは、カスタムリソース定義で設定できます。
