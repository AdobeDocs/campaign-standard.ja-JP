---
title: インポートテンプレートを使用したデータのインポート
description: データを収集してキャンペーンデータベースをフィードする方法を説明します。
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# インポートテンプレートを使用したデータのインポート{#importing-data-with-import-templates}

データを読み込むと、データを収集してキャンペーンのデータベースをフィードできます。

また、 [ワークフロー](../../automating/using/get-started-workflows.md)、Adobe Campaignオファーは、管理者が定義した特定の種類のインポートを管理できる、シンプルなインポート機能を使用します。

運営原則は以下の通り。 インポートテンプレートの定義と管理は **管理者が行います** (インポートテンプレートの [定義を参照](../../automating/using/defining-import-templates.md))。 これらのインポートテンプレートは、 **[!UICONTROL Profiles & audiences]** /メニューのシンプル化された表示を使用するユーザーに対して表示 **[!UICONTROL Imports]** されます。

したがって、実行するインポートのタイプを選択し、インポートするデータと共にファイルをアップロードするだけで済みます。 管理者が定義したワークフローは、ユーザに対して透過的に実行され、ユーザはインポートの完了後にインポートの結果の詳細にアクセスできます。

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. 役割について詳しくは、[この節](../../administration/using/list-of-roles.md)を参照してください。

インポートは、実行元のテンプレート、実行日、実行ステータスに従ってフィルタリングできます。

1. インポートの概要で、ボタンをクリックし **[!UICONTROL Create]** ます。 ウィザードが開きます。
1. 実行するインポートのタイプを選択します。 読み込みタイプは、使用可能なインポートテンプレートに対応します。
1. 必要に応じて、テンプレートにリンクされたサンプルファイルをコンピューターにダウンロードし、読み込むファイルに必要なデータタイプを表示します。
1. インポートするデータを含むファイルをウィザードにダウンロードします。
1. インポートの開始。 ウィザードが閉じ、使用したテンプレートで実行されたインポートのリストに戻ります。
1. ページを更新し、実行の詳細を表示するために実行したインポートを選択します。

   ![](assets/simplified_import1.png)

インポートの実行の詳細が利用可能になりました。 読み込まれたファイルと、拒否されたデータ（読み込まれなかったデータ）を含むファイルの両方を、コンピューターにダウンロードできます。
