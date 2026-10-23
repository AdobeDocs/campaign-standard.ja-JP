---
title: リソースのステータス
description: 公開状態に応じて、さまざまなリソースステータスを確認できます。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
TQID: 'https://experienceleague.adobe.com/f0ihge9X4opmgRRdswkBt7yMWSmJc36viZKWXPoQCe4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%
---
# リソースのステータス{#resource-statuses}

リソースのステータスは、公開ステータスやアクティベーションステータスに応じて異なります。

これらのステータスを&#x200B;**[!UICONTROL Custom resources]**&#x200B;画面に表示する専用の列が2つあります。

![](assets/schema_colonne_1.png)

**公開状況**

* **ドラフト**: リソースが作成または再作成されました。 データベーステーブルと対応するAPIを作成するには、リソースを再公開する必要があります。 リソースが再作成される場合、公開ステップの後にリソースは自動的に非アクティブになります。
* **リドラフトの保留中**: リソースがリドラフトされました。 再作成プロセスは、次の公開中に行われます。 再作成は不可逆的です。 再作成と公開の準備の両方で、ユーザーに通知する警告メッセージがいくつか表示されます。

  再作成について詳しくは、[&#x200B; リソースの削除](../../developing/using/deleting-a-resource.md)を参照してください。

  >[!NOTE]
  >
  >**[!UICONTROL Cancel re-draft]** オプションは、再作成するリソースに「公開済み」ステータスの他のリソースを介したリンクが引き続き含まれている場合に使用できます。 このオプションを使用すると、「再ドラフト」プロセスを元に戻すことができます。 カスタムリソースは元のステータスに戻ります。

* **公開済み**: リソースが公開されました。 リソースが最終変更日の後に変更された場合、最新の変更を考慮するためにリソースの再公開を促すメッセージが表示されます。

**[!UICONTROL Do not publish latest modifications]** フィールドは、今後の公開中に変更が考慮されないようにします。

このフィールドは、カスタムリソース定義で設定できます。
