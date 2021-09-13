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

リソースのステータスは、パブリッシュステータスやアクティベーションステータスに応じて異なる場合があります。

**[!UICONTROL Custom resources]**&#x200B;画面には、これらのステータスの表示専用の列が2つあります。

![](assets/schema_colonne_1.png)

**公開ステータス**

* **ドラフト**:リソースが作成されたか、再ドラフトされました。対応するAPIと共にデータベーステーブルを作成するには、リソースを再公開する必要があります。 リソースを再ドラフト中の場合、パブリッシュステップの後、リソースは自動的に非アクティブになります。
* **再ドラフトの保留中**:資源は再起草された。再ドラフト処理は、次の公開時におこなわれます。 再ドラフトは元に戻せません。 いくつかの警告メッセージが表示され、再ドラフト時とパブリッシュの準備時の両方でユーザーに通知されます。

   再ドラフトの詳細については、「[リソースの削除](../../developing/using/deleting-a-resource.md)」を参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL Cancel re-draft]**&#x200B;オプションは、再ドラフトするリソースに、「公開済み」ステータスの他のリソースを介したリンクが含まれている場合に使用できます。 このオプションを使用すると、「再ドラフト」処理を元に戻すことができます。 カスタムリソースは元のステータスに戻ります。

* **公開済み**:リソースが公開されている。最終変更日の後にリソースが変更された場合は、最新の変更を考慮するために、リソースを再公開するように促すメッセージが表示されます。

**[!UICONTROL Do not publish latest modifications]**&#x200B;フィールドは、今後のパブリケーションで変更が考慮されないようにします。

このフィールドは、カスタムリソース定義で設定できます。
