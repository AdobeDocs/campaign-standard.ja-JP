---
title: データベース構造の更新
description: Adobe Campaignデータベースの更新方法を確認します。
page-status-flag: 非活性化の
uuid: 6c802f4f-d298-4ca4-acdb-09f2ad3865b9
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: リソースの追加または拡張
discoiquuid: 2448b126-66b8-4608-aa6c-8028fb1902a4
context-tags: deploy,main;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# データベース構造の更新{#updating-the-database-structure}

データモデルに対する変更を有効にし、それらを使用できるようにするには、データベース構造を更新する必要があります。

>[!NOTE]
>
>カスタムリソースは、アドビが実行した自動更新時に自動的に更新されます。

## カスタムリソースの公開 {#publishing-a-custom-resource}

リソースに対して実行された変更を適用するには、データベースの更新を実行する必要があります。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除されると、対応するイベントは自動的に非公開になります。 See [Configuring Transactional messaging](../../administration/using/configuring-transactional-messaging.md).

1. アドバンスメニューで、Adobe Campaignロゴを使用して/を選 **[!UICONTROL Administration]** 択し、 **[!UICONTROL Development]**&#x200B;次に選択しま **[!UICONTROL Publishing]**&#x200B;す。
1. デフォルトでは、このオ **[!UICONTROL Determine modifications since the last publication]** プションはオンになっており、最後の更新以降に実行された変更のみが適用されます。

   >[!NOTE]
   >
   >完了前 **[!UICONTROL Repair database structure]** にパブリケーションが失敗した場合は、正しい設定が再確立されます。 カスタムリソースを使用せずにデータベース内で直接実行された変更はすべて削除されます。

   ![](assets/schema_extension_12.png)

1. Click the **[!UICONTROL Prepare publication]** button to start the analysis. 大きなテーブルの更新は、インスタンスがワークフローで集中的にビジーでない場合に行う必要があります。

   Profiles &amp; Services APIで実行するアクションについて詳しくは、API拡張を使用したリソ [ースの公開を参照してください](#publishing-a-resource-with-api-extension)。

   ![](assets/schema_extension_13.png)

1. パブリケーションが実行されたら、ボタンをクリック **[!UICONTROL Publish]** して新しい設定を適用します。
1. 発行されると、各リソ **[!UICONTROL Summary]** ースのウィンドウ枠に、現在の状態が示され、最 **[!UICONTROL Published]** 後の発行日が指定されます。

   >[!NOTE]
   >
   >リソースに新しい変更を加える場合は、変更を適用するためにこの操作を繰り返す必要があります。

   発行前にリソースの状態が **[!UICONTROL Pending re-draft]** ある場合、発行すると、列やテーブルの削除などの確定的な変更が行われるので、アクションを確認するよう促す追加のメッセージが表示されます。 この最後の変更を行うのに役立つタブを使 **[!UICONTROL SQL Script]** 用できます。 パブリケーション中に実行されるSQLコマンドを提供します。

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >再ドラフト処理は、ボタンをクリックして停止でき **[!UICONTROL Cancel re-draft]** ます。 この操作を行うと、リソースの状態が元の状態に戻ります。

1. 文書が失敗した場合は、[ ]をクリックして、常に前の文書に戻ることができま **[!UICONTROL Back to latest successful publication]**&#x200B;す。

   パブリケーションの状態を失敗のままにした場合は、インスタンスにログインするとすぐにポップアップウィンドウが開き、このパブリケーションを修正するように指示されます。 パブリケーションが修正されるまで、インスタンスは新しいバージョンの製品でアップグレードされません。

   ![](assets/schema_extension_31.png)

## API拡張機能を使用したリソースの公開 {#publishing-a-resource-with-api-extension}

次の場合に、Profile and Services APIを作成できます。

* カスタムリソースを拡張する場合、ま **[!UICONTROL Profiles]****[!UICONTROL Services]**&#x200B;たは、Profiles &amp; Services APIの更新を実行して、カスタムリソース拡張で宣言されているフィールドを統合できます。
* カスタムリソースを定義し、リソースまたはカスタムリソース間のリンクを作成する **[!UICONTROL Profiles]** と、 **[!UICONTROL Services]** APIに新しいリソースを含める更新を実行できます。

このオプションは、パブリケーション画面で選択できます。

* APIがまだ発行されていない場合（つまり、リソースをまだ拡張していない場合、またはこのリソースや他のリソースに対してこのオプションをまだ選択していない場合）は、APIを作成するかどうかを選択できます。

   ![](assets/create-profile-and-services-api.png)

* APIが既に公開されている場合（つまり、既にリソースを拡張し、このオプションを1回オンにしている場合）は、APIの更新が強制的に行われます。

   実際、APIは作成されると、再公開するたびに自動的に更新されます。 これは、このAPIのプロファイルまたはサービスリソースを壊してインスタンスに害を与えないようにするためです。

デフォルトでは、カスタムリソースは統合されますが、特定の動作でこのリソースを発行しない場合は、で使用できるオプションを選択で **[!UICONTROL Hide this resource from APIs]** きます **[!UICONTROL Resource Properties]**。

![](assets/removefromextoption.png)

ステップの **[!UICONTROL Prepare Publication]** 後、Adobe Campaignは、現在のバージョンのAPIと、タブにパブリケーションした後の将来のバージョンの差分を表示しま **[!UICONTROL Profiles & Services API Preview]**&#x200B;す。 APIを初めて拡張した場合、追加設定不要なカスタムリソース定義と拡張機能とが比較されます。

タブに表示される情報は、次の3つのセクションに分かれています。要素の追加、削除、および変更

![](assets/extendpandsapi_diff.png)

差分の分析は必須の手順です。パブリケーション・ステップによってAPIの動作が変更され、ドミノ効果の周辺の開発に影響を与える可能性が高いからです。

>[!NOTE]
>
>このパブリケーションは **[!UICONTROL profilesAndServicesExt]** APIを更新します。 APIは更 **[!UICONTROL profilesAndServices]** 新されません。

Adobe Campaign APIについて詳しくは、 [Adobe IOに関するAdobe Campaign専用ドキュメントを参照してください](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html)。
