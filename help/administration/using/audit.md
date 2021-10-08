---
title: 監査記録
description: キャンペーン監査記録を使用したアクションとイベントの監視
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Access Management
role: Admin
level: Experienced
source-git-commit: df7fce6f2fd98688e5a1fb5bc84603e6b3df5cd4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 2%

---

# 監査記録 {#audit}

**[!UICONTROL Audit trail]** は、インスタンス内でおこなわれた変更の完全な履歴にアクセスできるようにします。

**[!UICONTROL Audit trail]** は、Adobe Campaign Standardインスタンス内で発生するアクションとイベントの包括的なリストをリアルタイムでキャプチャします。データの履歴にアクセスして次のような質問に回答するためのセルフサービスの手段が含まれています。ワークフロー、カスタムリソースおよびオプション（最後に更新したユーザー、またはインスタンスでユーザーがおこなった操作）への影響

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** は、次の 3 つのコンポーネントで構成されます。

* **カスタムリソースの監査記録**:アクティビティと、カスタムリソースに対する最終変更を確認します。

   **[!UICONTROL Custom resources]** の詳細は、[ ページ ](../../developing/using/key-steps-to-add-a-resource.md) を参照してください。

* **ワークフローの監査記録**:ワークフローに対するアクティビティと最後の変更、さらに次のようなワークフローの状態を確認します。

   * 作成日時
   * 変更済み
   * 削除済み
   * ワークフロー開始
   * ワークフローの一時停止
   * ワークフローの停止
   * ワークフローの再起動
   * ワークフローのクリーンアップ
   * ワークフローシミュレート
   * ワークフローのウェイクアップ
   * ワークフローの即時停止
   * 同じユーザーでワークフローを再起動
   * ワークフローの再起動が不明なコマンド

   **[!UICONTROL Workflows]** の詳細は、[ ページ ](../../automating/using/get-started-workflows.md) を参照してください。

* **オプションの監査記録**:「 」アクティビティと「 」オプションに対する最終変更を確認します。

   **[!UICONTROL Options]** の詳細は、[ ページ ](../../administration/using/about-campaign-standard-settings.md) を参照してください。

デフォルトでは、リテンション期間は 30 日です。

## 監査記録へのアクセス {#audit-access}

インスタンスの監査記録にアクセスするには：

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Audit trail]** を選択します。

   ![](assets/audit-trail.png)

1. **[!UICONTROL Audit trail]** ウィンドウが開き、エンティティのリストが表示されます。 Adobe Campaign Standardは、ワークフロー、オプションおよびカスタムリソースの作成、編集および削除アクションに関する監査を実施します。

   **[!UICONTROL Search]** メニューから、次の項目でエンティティをフィルターできます。

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**:エンティティのタイプ（「すべて」、「ワークフロー」、「カスタムリソース」、「オプション」）。
   * **[!UICONTROL Entity name]**:ワークフロー、オプションまたはカスタムリソースの ID

   ![](assets/audit-trail_2.png)

1. エンティティを 1 つ選択して、最後の変更の詳細を確認します。

1. 「監査エンティティ」ウィンドウには、選択したエンティティに関する次のような詳細情報が表示されます。

   * **[!UICONTROL Entity]**:ワークフロー、オプションまたはカスタムリソースの ID。
   * **[!UICONTROL Action]**:このエンティティに対して最後に実行された操作。
   * **[!UICONTROL Changed by]**:このエンティティを最後に変更した人のユーザー名。
   * **[!UICONTROL Changed date]**:このエンティティに対して最後に実行されたアクションの日付。
   * **[!UICONTROL Content]**:エンティティ内で正確に変更された内容に関する詳細情報を提供するコードブロック。

   この例では、このインスタンスのビジネス管理者が 8 月 26 日にワークフロー WKF110 を開始しています。

   ![](assets/audit-trail_3.png)

## 監査記録の有効化/無効化 {#enable-disable-audit}

監査記録は、特定のアクティビティに対して簡単にアクティブ化または非アクティブ化できます。

それには、次の手順に従います。

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** を選択します。

   ![](assets/audit-trail_4.png)

1. 無効にするエンティティに応じて、次のいずれかのオプションを選択します。

   * **[!UICONTROL XtkAudit_Workflows]** 」オプションを使用して、ワークフローの監査記録を管理します。
   * **[!UICONTROL XtkAudit_Option]** オプションを使用して、オプションの監査記録を管理します。
   * **[!UICONTROL XtkAudit_CusResource]** オプションを使用して、カスタムリソースの監査記録を管理できます。
   * **[!UICONTROL XtkAudit_Enable_All]** すべてのエンティティの監査記録を管理するオプション。

      >[!NOTE]
      >
      >**[!UICONTROL XtkAudit_Enable_All]** オプションが 0 に設定されている場合、他の個々のオプション値に関係なく、**[!UICONTROL Audit trail]** 機能は完全に無効になります。
   ![](assets/audit-trail_5.png)

1. **[!UICONTROL Options]** ページで、**[!UICONTROL Audit trail]** を無効にする場合は **[!UICONTROL Value (integer)]** を 0 に、有効にする場合は 1 に設定します。

   ![](assets/audit-trail_6.png)

1. 「**[!UICONTROL Save]**」をクリックします。