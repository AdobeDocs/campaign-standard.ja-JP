---
title: インポートテンプレートを使用したデータの読み込み
seo-title: インポートテンプレートを使用したデータの読み込み
description: インポートテンプレートを使用したデータの読み込み
seo-description: キャンペーンデータベースをフィードするデータを収集する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: bfc03235-2032-448a- a9ed-21ff2a83fa09
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: importing- and- exporting- data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cpa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Importing data with import templates{#importing-data-with-import-templates}

データをインポートすると、キャンペーンのデータベースをフィードするデータを収集できます。

[ワークフロー](../../automating/using/discovering-workflows.md)に加えて、Adobe Campaignでは、管理者によって定義された特定のタイプのインポートを管理するための簡易インポート機能を提供しています。

The operating principle is as follows: an **administrator** defines and manages import templates (see [Defining import templates](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** menu.

したがって、インポートするインポートのタイプを選択し、インポートするデータと共にファイルをアップロードする必要があります。管理者によって定義されたワークフローは、ユーザーに対して透過的に実行されます。ユーザーは、完了したらインポートの結果の詳細にアクセスできます。

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. ロールについて詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

インポートは、実行元のテンプレート、実行日および実行ステータスに従って適用できます。

1. From the imports overview, click the **[!UICONTROL Create]** button. ウィザードが開きます。
1. 実行するインポートのタイプを選択します。インポートタイプは、使用可能なインポートテンプレートに対応しています。
1. 必要に応じて、テンプレートにリンクされているサンプルファイルをコンピューターにダウンロードして、読み込まれるファイル内のデータタイプを表示します。
1. ウィザードで読み込むデータを含むファイルをダウンロードします。
1. インポートを開始します。ウィザードが閉じ、使用するテンプレートで実行されたインポートのリストに戻ります。
1. ページを更新し、実行したばかりのインポートを選択して、実行の詳細を表示します。

   ![](assets/simplified_import1.png)

インポートの実行の詳細が利用できるようになりました。読み込まれたファイルと、拒否されたデータ（インポートされなかったデータ）を含むファイルの両方をコンピュータにダウンロードできます。
