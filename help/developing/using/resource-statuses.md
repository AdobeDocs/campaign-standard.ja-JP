---
title: リソースのステータス
description: 公開の状態に応じて、様々なリソースのステータスを確認できます。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---

# リソースのステータス{#resource-statuses}

公開またはアクティブ化のステータスに応じて、リソースのステータスは異なる場合があります。

これらのステータスを **[!UICONTROL Custom resources]** 画面に表示する専用の 2 つの列があります。

![](assets/schema_colonne_1.png)

**公開ステータス**

* **ドラフト**：リソースが作成または再作成されました。 データベーステーブルおよび対応する API を作成するには、リソースを再公開する必要があります。 リソースを再ドラフト化する場合、公開ステップの後、リソースは自動的に非アクティブになります。
* **再ドラフトを保留中**：リソースが再ドラフトされました。 再ドラフトプロセスは、次回の公開時に実行されます。 再ドラフトは元に戻せません。 再作図およびパブリッシュの準備中に、ユーザに通知するためのいくつかの警告メッセージが表示されます。

  再作図の詳細については、[ リソースの削除 ](../../developing/using/deleting-a-resource.md) を参照してください。

  >[!NOTE]
  >
  >**[!UICONTROL Cancel re-draft]** オプションは、再ドラフト化するリソースに、「公開済み」ステータスの他のリソースを介したリンクがまだ含まれている場合に使用できます。 このオプションを使用すると、「再ドラフト」プロセスを元に戻すことができます。 その後、カスタムリソースは元のステータスに戻ります。

* **公開済み**：リソースが公開されています。 最終変更日以降にリソースが変更された場合は、最新の変更を考慮してリソースを再公開するよう促すメッセージが表示されます。

**[!UICONTROL Do not publish latest modifications]** フィールドを使用すると、今後のパブリケーションで変更が考慮されなくなります。

このフィールドは、カスタムリソース定義で設定できます。
