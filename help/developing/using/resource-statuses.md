---
title: リソースのステータス
description: 公開状態に応じて、様々なリソースのステータスを確認します。
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

リソースのステータスは、パブリッシュまたはアクティベーションのステータスに応じて異なる場合があります。

これらのステータスの表示に関して、 **[!UICONTROL Custom resources]** 画面

![](assets/schema_colonne_1.png)

**公開ステータス**

* **ドラフト**:リソースが作成されたか、再ドラフト化されました。 対応する API と共にデータベーステーブルを作成するには、リソースを再公開する必要があります。 リソースが再ドラフト中の場合、パブリッシュステップの後で自動的に非アクティブになります。
* **再ドラフトを保留中**:リソースが再下書きされました。 再ドラフト処理は、次の公開時におこなわれます。 再ドラフトは元に戻せません。 ユーザに対して、再ドラフト化時とパブリッシュ準備時の両方に通知する警告メッセージがいくつか表示されます。

   再ドラフトの詳細については、 [リソースの削除](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >この **[!UICONTROL Cancel re-draft]** オプションは、再ドラフトするリソースに、「公開済み」ステータスの他のリソースを介したリンクが含まれている場合に使用できます。 このオプションを使用すると、「再ドラフト」処理を元に戻すことができます。 カスタムリソースは元のステータスに戻ります。

* **公開済み**:リソースが公開されました。 最終変更日の後にリソースが変更された場合は、最新の変更を考慮してリソースを再公開するように促すメッセージが表示されます。

この **[!UICONTROL Do not publish latest modifications]** 「 」フィールドを使用すると、今後のパブリケーションで変更が考慮されなくなります。

このフィールドは、カスタムリソース定義で設定できます。
