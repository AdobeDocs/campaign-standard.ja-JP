---
title: リソースステータス
seo-title: リソースステータス
description: リソースステータス
seo-description: パブリケーション状態に応じて様々なリソースステータスを見つけます。
page-status-flag: 常にアクティブ化されていない
uuid: 215c0a2e-27ec-43f3- baac-1eaac7640784
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: about- custom- resources
discoiquuid: 85516477-1b95-4273- a0a7- d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Resource statuses{#resource-statuses}

リソースには、パブリケーションまたはアクティベーションステータスに応じて異なるステータスを含めることができます。

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**パブリケーションのステータス**

* **ドラフト**:リソースが作成または再作成されました。データベーステーブルおよび対応するAPIを作成するには、リソースを再公開する必要があります。リソースが再度ドラフト化されている場合、パブリッシュ手順に従って非アクティブにレンダリングされます。
* **保留中の再ドラフト**:リソースが再作成されました。次のパブリケーションの中で再ドラフト処理が実行されます。再描画は元に戻すことができません。いくつかの警告メッセージは、再ドラフト時にこの事実をユーザーに警告し、公開準備の際にそのユーザーに警告します。

   For more on re-drafting, see [Deleting a resource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >**[!UICONTROL Cancel re-draft]** このオプションは、再ドラフトするリソースに、「公開済み」ステータスの他のリソースによるリンクが含まれている場合に使用できます。このオプションを使用すると、「再ドラフト」プロセスを元に戻すことができます。カスタムリソースが元のステータスに戻ります。

* **発行**&#x200B;済み:リソースが公開されました。最終変更日の後にリソースが変更された場合は、最新の変更を考慮するために、ユーザに再公開を求めるメッセージが表示されます。

**[!UICONTROL Do not publish latest modifications]** このフィールドを使用すると、今後のパブリケーション中に変更を考慮することができなくなります。

このフィールドは、カスタムリソース定義で設定できます。
