---
title: Microsoft Dynamics 365 統合の使用
description: Microsoft Dynamics 365とCampaign Standard統合の使い方を学ぶ
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 1%

---


# Microsoft Dynamics 365 統合の使用

この統合で実行されるジョブはいくつかあります。

* **入力**:

   * Dynamics 365から **連絡先をキャンペーンに取り込む**

   * **カスタムエンティティ**:Dynamics 365からキャンペーンにカスタムテーブルを取り込みます。 詳しくは、[この節](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)を参照してください。

* **出口**:ACSからD365に電子メールマーケティングイベントを取り込む（電子メール送信、開く、クリック、バウンス）

* **オプトアウト**:双方向の同期オプトアウトの状態(ブロックリスト例：)

データフローの詳細については、この節 [を参照してください](#data-flows)。

## Adobe Campaign Standardユーザーエクスペリエンス

Dynamics 365で連絡先が作成または変更(または削除（有効な場合）されると、キャンペーンに送信されます。  これらの連絡先は、キャンペーンのプロファイル画面に表示され、マーケティングキャンペーンでターゲット設定できます。  下のプロファイル画面を参照してください。

![](assets/MSdynamicsACS-usage1.png)

キャンペーンでオプトアウト属性を変更すると、Dynamics 365へのキャンペーン設定または双方向オプトアウト設定を選択し、その特定の属性が正しくマッピングされている場合、Dynamics 365にその属性が反映されます。

## Microsoft Dynamics 365ユーザーエクスペリエンス

出力の場合、次の電子メールマーケティングイベントがキャンペーンからDynamics 365に送信され、カスタムアクティビティとしてDynamics 365タイムライン表示に表示されます。

* Adobe Campaign電子メール送信

* Adobe Campaign電子メールを開く

* Adobe Campaign電子メールのURLのクリック

* Adobe Campaignの電子メールのバウンス

連絡先のタイムラインを表示するには、[Dynamics 365]ドロップダウンメニューの[販売ハブ]をクリックして、連絡先リストに移動します。  次に、左側のメニューバーで[接触]をクリックし、接触を選択します。

>[!NOTE]
>
>これらのイベントを表示するには、AppSourceのDynamics 365アプリのAdobe CampaignがDynamics 365インスタンスにインストールされている必要があります。

下に、「Dynamics User」の連絡先画面のスナップショットが表示されます。  タイムライン表示で、Dynamics Userがキャンペーン名&quot;2019LoyaltyCamp&quot;と配信名&quot;DM190&quot;に関連付けられた電子メールを送信したことがわかります。  Dynamicsユーザーが電子メールを開き、電子メール内のURLもクリックしました。これらの操作の両方でイベントが作成され、次にも示します。  右隅を見ると、Relationship Assistant(RA)カードが表示されます。現在、クリックされたURLを追跡するためのタスクが含まれています。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Dynamics Userのタイムライン表示を閉じる方法については、以下を参照してください。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下は、Relationship Assistant(RA)カードのクローズアップです。  AppSourceアプリには、Adobeの電子メールURLクリックイベントを監視するワークフローが含まれています。  このイベントが発生すると、タスクが作成され、期限が設定されます。  これにより、タスクがRAカードに表示され、さらに目に見えるようになります。  Adobeの電子メールバウンスイベントにも同様のワークフローがあり、無効な電子メールアドレスを調整するタスクを追加します。  これらのワークフローは、ソリューションでオフにできます。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

送信イベントの件名をクリックすると、次のようなフォームが表示されます。  「開く」と「バウンス」のイベントのフォームは似ています。

![](assets/do-not-localize/mirror_page_url_send.png)

電子メールURLのクリックイベントのフォームに、クリックされたURLの属性が追加されます。

![](assets/do-not-localize/mirror_page_url_click.png)

属性と説明のリストを次に示します。

* 件名：イベントの主題電子メール配信のキャンペーンIDと配信IDで構成される

* 所有者：プロビジョニング後の手順で作成されるアプリケーションユーザー

* 関連：連絡先の名前

* キャンペーン名：Campaign Standard内のキャンペーンID

* 配信名：Campaign Standard内の配信ID

* 送信日/開封日/クリック日/バウンス日：イベントが作成された日時

* 追跡URL:クリックされたURL

* ミラーページURL:送信、開く、クリック、バウンスされた電子メールのミラーページへのURL

>[!NOTE]
>
>電子メールミラーページの有効期限は、対応するキャンペーン電子メールチャネルアクティビティの設定画面で変更できます( [有効期間パラメーター](../../administration/using/configuring-email-channel.md#validity-period-parameters))。

>[!NOTE]
>
>オプトアウトの場合、Dynamics 365でオプトアウト属性を変更すると、Dynamics 365からキャンペーンへの設定または双方向のオプトアウト設定を選択し、その属性が正しくマッピングされている場合、キャンペーンに反映されます。

## データフロー {#data-flows}

### 連絡先とカスタムエンティティの入力

新しいレコードと更新（および、有効な場合は削除）レコードが、Dynamics 365連絡先テーブルからキャンペーンプロファイルテーブルに送信されます。

テーブルマッピングは、Dynamics 365のテーブル属性をキャンペーンテーブル属性にマップするように構成できます。 必要に応じて、テーブルのマッピングを変更し、属性を追加または削除できます。

データ・フローの最初の実行は、「非アクティブ」とマークされたレコードを含む、すべてのマッピング済みレコードを転送するように設計されています。その後、統合は増分更新のみ処理します。 ただし、フィルターが設定されている場合は例外です。基本的な属性ベースのフィルタリングルールを設定して、キャンペーンに同期するレコードを決定できます。

基本的な置換規則を設定して、属性値を別の値に置き換えることができます（例：「#00FF00」の場合は「green」、1の場合は「F」）。

レコードの量に応じて、キャンペーンのSFTPストレージを初期データ転送に使用する必要がある場合があります。  「初期データ転送」の節を参照してください。

キャンペーンプロファイルテーブルの属性externalIdには、連絡先の入力が機能するように、Dynamics 365連絡先属性contactIdを設定する必要があります。 キャンペーンのカスタムエンティティにもDynamics 365の一意のID属性を設定する必要があります。ただし、この属性は、キャンペーンのカスタムエンティティ属性に格納できます（externalIdである必要はありません）。

>[!NOTE]
>
>カスタムエンティティの入力の場合、同期されたカスタムエンティティに対してDynamics 365内で変更追跡を有効にする必要があります。

### 電子メールマーケティングイベントのフロー

電子メールマーケティングイベントは、キャンペーンからDynamics 365に送信され、タイムライン表示に表示されます。

サポートされるマーケティングイベントタイプ:
* 送信 —受信者に電子メールを送信
* 開く —受信者が開いた電子メール
* クリック —受信者がクリックした電子メール内のURL
* バウンス —受信者への電子メールがハードバウンスを経験した

D365には、次のイベント属性が表示されます。
* マーケティングキャンペーン名
* 電子メール配信名
* タイムスタンプ
* 電子メールミラーページURL
* URLがクリックされました(クリックイベントのみ)

電子メールマーケティングイベントは、タイプ（送信、開く、クリック、バウンス）別に有効/無効を切り替えることができるので、選択したイベントタイプのみがDynamics 365に渡されます。

### オプトアウトフロー

オプトアウト(例：ブロックリスト)値はシステム間で同期されます。オンボーディングの際は、次のオプションから選択できます。
* Dynamics 365はオプトアウトの真実の原因です：オプトアウト属性は、Dynamics 365からCampaign Standardに1方向で同期されます
* Campaign Standardはオプトアウトの真の原因です。オプトアウト属性は、Campaign StandardからDynamics 365への一方向で同期されます
* Dynamics 365 ANDCampaign Standardはどちらも真実の源です。オプトアウト属性は、Campaign StandardとDynamics 365の間で双方向に同期されます

また、システム間のオプトアウト同期を別のプロセスで管理する場合は、統合のオプトアウトデータフローを無効にできます。

オプトアウトフローマッピングは、会社間でビジネス要件が異なる場合があるので、顧客が指定します。  キャンペーン側では、OOTBオプトアウト属性のみがオプトアウトマッピングに使用できます。
* ブロックリスト
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

Dynamics 365では、ほとんどのオプトアウトフィールドには「ドノット」プレフィックスが付きます。ただし、データタイプに互換性がある場合は、他の属性をオプトアウト目的に使用することもできます。

### 初期データ転送

500kレコードを超えるDynamics 365テーブルは、キャンペーンワークフローを使用してインポートするには、キャンペーンのSFTPストレージにエクスポートする必要があります。

初期データ転送は、1回限りのファイルベースのデータ転送です。 データ転送の後、統合は増分更新にAPIを使用します。
