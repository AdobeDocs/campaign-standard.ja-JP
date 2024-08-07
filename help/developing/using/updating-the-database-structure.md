---
title: データベース構造の更新
description: Adobe Campaign データベースの更新方法を説明します。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: deploy,main;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: fa39eb54-9ec0-4aff-94a8-5459f4c496d0
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 90%

---

# データベース構造の更新{#updating-the-database-structure}

データモデルの変更を有効にして使用できるようにするには、データベース構造を更新する必要があります。

>[!NOTE]
>
>カスタムリソースは、アドビが実行する自動更新時に自動的に更新されます。

## カスタムリソースの公開 {#publishing-a-custom-resource}

リソースに対して実行された変更を適用するには、データベースの更新を実行する必要があります。

>[!NOTE]
>
>イベントで使用されているカスタムリソースのフィールドが変更または削除された場合、対応するイベントは自動的に非公開になります。[ トランザクションイベントの非公開 ](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) を参照してください。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Administration]**／**[!UICONTROL Development]**／**[!UICONTROL Publishing]** を選択します。
1. デフォルトでは、「**[!UICONTROL Determine modifications since the last publication]**」オプションはオンになっており、最後の更新以降に実行された変更のみが適用されます。

   >[!NOTE]
   >
   >「**[!UICONTROL Repair database structure]**」をオンにすると、公開処理が完了する前に失敗した場合は正しい設定が再確立されます。カスタムリソースを使用せずにデータベース内で直接おこなわれた変更はすべて削除されます。

   ![](assets/schema_extension_12.png)

1. 「**[!UICONTROL Prepare publication]**」ボタンをクリックして、分析を開始します。容量の大きいテーブルの更新は、インスタンスがワークフローの集中的な処理でビジー状態になっているときを避けて実行してください。

   プロファイルおよびサービス API で実行するアクションについて詳しくは、[API 拡張を使用したリソースの公開](#publishing-a-resource-with-api-extension)を参照してください。

   ![](assets/schema_extension_13.png)

   >[!NOTE]
   >
   >重複したインデックスが原因で公開が失敗するため、準備手順では、リソースに対して定義されたインデックスが別のリソースに対して同じ名前で既に存在するかどうかを確認します。 この場合は、インデックスの名前を変更するように求めるエラーメッセージが表示されます。 [ インデックスの定義 ](configuring-the-resource-s-data-structure.md#defining-indexes) を参照してください。

1. 公開が実行されたら、「**[!UICONTROL Publish]**」ボタンをクリックして新しい設定を適用します。
1. 公開された各リソースの&#x200B;**[!UICONTROL Summary]**&#x200B;ウィンドウには、現在の状態が「**[!UICONTROL Published]**」と表示され、最新の公開日が示されます。

   >[!NOTE]
   >
   >リソースに新しい変更を加えた場合、変更を適用するには、この操作を繰り返す必要があります。

   公開前にリソースのステータスが「**[!UICONTROL Pending re-draft]**」である場合は、追加のメッセージが表示されます。公開すると確定的な変更（列やテーブルの削除など）がおこなわれるので、アクションを確認するよう促されます。この部分の変更には、「**[!UICONTROL SQL Script]**」タブを使用すると便利です。公開時に実行される SQL コマンドが用意されています。

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >再ドラフト処理は、「**[!UICONTROL Cancel re-draft]**」ボタンをクリックして停止できます。このアクションにより、リソースのステータスが元の状態に戻ります。

1. 公開が失敗した場合は、いつでも「**[!UICONTROL Back to latest successful publication]**」をクリックして前の公開に戻ることができます。

   公開の状態を失敗のままにしておくと、インスタンスにログインするとすぐにポップアップウィンドウが開き、この公開を修正するように促されます。公開が修正されるまで、インスタンスは新しい製品バージョンにアップグレードされません。

   ![](assets/schema_extension_31.png)

## API 拡張機能を使用したリソースの公開 {#publishing-a-resource-with-api-extension}

次の場合には、プロファイルおよびサービス API を作成できます。

* **[!UICONTROL Profiles]**&#x200B;または&#x200B;**[!UICONTROL Services]**&#x200B;のカスタムリソースを拡張する場合、プロファイルおよびサービス API の更新を実行して、カスタムリソース拡張で宣言されているフィールドを統合できます。
* カスタムリソースを定義し、**[!UICONTROL Profiles]**&#x200B;または&#x200B;**[!UICONTROL Services]**&#x200B;のリソースと、カスタムリソースの間にリンクを作成した場合は、更新を実行して API に新しいリソースを含めることができます。

このオプションは、公開画面で選択できます。

* API がまだ公開されていない場合（つまり、リソースを拡張したことがない場合、またはこのリソースや他のリソースに対してこのオプションを選択したことがない場合）は、API を作成するかどうかを選択できます。

  ![](assets/create-profile-and-services-api.png)

* API が既に公開されている場合（つまり、既にリソースを拡張してこのオプションを 1 回選択したことがある場合）は、API の更新が強制されます。

  実際、API はいったん作成されると、再公開されるたびに自動的に更新されます。これは、この API のプロファイルリソースやサービスリソースが機能しなくなってインスタンスに障害が発生するのを避けるためです。

デフォルトでは、カスタムリソースは統合されますが、特定の動作についてこのリソースを公開したくない場合は、「**[!UICONTROL Hide this resource from APIs]**」オプションを&#x200B;**[!UICONTROL Resource Properties]**&#x200B;で選択できます。

![](assets/removefromextoption.png)

「**[!UICONTROL Prepare Publication]**」ステップの後、Adobe Campaign の「**[!UICONTROL Profiles & Services API Preview]**」タブに、API の現在のバージョンと公開後の将来のバージョンの差分が表示されます。API を初めて拡張した場合は、標準搭載のカスタムリソース定義と拡張が比較されます。

差分の情報は、追加された要素、削除された要素、変更された要素の 3 つのセクションに分かれてタブに表示されます。

![](assets/extendpandsapi_diff.png)

公開ステップで API の動作が変更され、関連する開発に影響が波及する可能性が高いので、差分の分析は必須のステップです。

>[!NOTE]
>
>この公開で **[!UICONTROL profilesAndServicesExt]** API が更新されます。**[!UICONTROL profilesAndServices]** API は更新されません。

Adobe Campaign Standard API について詳しくは、[ この節 ](../../api/using/get-started-apis.md) を参照してください。
