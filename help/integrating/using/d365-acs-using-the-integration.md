---
title: Microsoft Dynamics 365 統合の使用
description: Microsoft Dynamics 365 とCampaign Standard統合の使用方法を説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---

# Microsoft Dynamics 365 統合の使用

Microsoft Dynamics 365 とのAdobe Campaign Standard統合で実行されるデータフローは、複数あります。 これらのフローについて詳しくは、 [このページ](../../integrating/using/d365-acs-self-service-app-workflows.md).

データフローの詳細については、このドキュメントの詳細を参照してください。 [データフロー](#data-flows)  」セクションに入力します。

## Adobe Campaign Standardユーザーエクスペリエンス

Microsoft Dynamics 365 で連絡先が作成、変更または削除されると（削除が有効な場合）、その連絡先はCampaign Standardに送信されます。 これらの連絡先は、Campaign のプロファイル画面に表示され、マーケティングキャンペーンのターゲットに設定できます。 下のプロファイル画面を参照してください。

![](assets/MSdynamicsACS-usage1.png)

Campaign でオプトアウト属性を変更すると、Dynamics 365 で **単方向 (Campaign からMicrosoft Dynamics 365)** または **双方向** オプトアウト設定を使用する場合と、その特定の属性が正しくマッピングされている場合に、個別の属性を選択します。

## Microsoft Dynamics 365 ユーザーエクスペリエンス

エグレスについて、次の電子メールマーケティングイベントが Campaign から Dynamics 365 に送信され、Microsoft Dynamics 365 タイムラインビューにカスタムアクティビティとして表示されます。

* Adobe Campaign電子メール送信

* Adobe Campaign E メールオープン

* Adobe Campaign E メールの URL クリック

* Adobe Campaign電子メールバウンス

連絡先のタイムラインを表示するには、Dynamics 365 ドロップダウンメニューから Sales Hub をクリックして、連絡先リストに移動します。 次に、左側のメニューバーで [ 連絡先 ] をクリックし、連絡先を選択します。

>[!NOTE]
>
>この **Adobe Campaign for Microsoft Dynamics 365** これらのイベントを表示するには、Microsoft Dynamics 365 インスタンスに AppSource のアプリがインストールされている必要があります。 [詳細情報](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

以下に、「Dynamics ユーザ」の連絡先画面のスナップショットを示します。 タイムラインビューでは、Dynamics ユーザーがキャンペーン名「2019LoyaltyCamp」および配信名「DM190」に関連付けられたメールを送信したことがわかります。 Dynamics ユーザーがメールを開き、メール内の URL もクリックしました。これらの両方のアクションによって、以下に示すイベントが作成されました。 右隅を見ると、リレーションシップアシスタント (RA) カードが表示されます。現在、クリックされた URL を追跡するタスクが含まれています。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Dynamics User のタイムラインビューを閉じるには、以下を参照してください。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下は、Relationship Assistant(RA) カードのクローズアップです。 AppSource アプリには、AdobeE メール URL クリックイベントを監視するワークフローが含まれています。 このイベントが発生すると、タスクが作成され、期限が設定されます。 これにより、タスクが RA カードに表示され、可視性が向上します。 「電子メールのバウンス」Adobeにも同様のワークフローがあり、無効な電子メールアドレスを紐付けするためのタスクを追加します。 これらのワークフローは、ソリューションでオフにできます。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

送信イベントの件名をクリックすると、次のようなフォームが表示されます。 open イベントと bounce イベントのフォームは似ています。

![](assets/do-not-localize/mirror_page_url_send.png)

電子メール URL のクリックイベント用のフォームに、クリックされた URL の属性が追加されます。

![](assets/do-not-localize/mirror_page_url_click.png)

以下は、属性と説明のリストです。

* **件名**:イベントの件名E メール配信のキャンペーン ID と配信 ID で構成されます

* **所有者**:プロビジョニング後の手順で作成されたアプリケーションユーザー

* **関連**:連絡先の名前

* **キャンペーン名**:Campaign Standardのキャンペーン ID

* **配信名**:Campaign Standardの配信 ID

* **送信日/開封日/クリック日/バウンス日**:イベントが作成された日時

* **トラッキング URL**:クリックされた URL

* **ミラーページの URL**:送信、開封、クリック、バウンスの順に実行された電子メールのミラーページへの URL。 E メールミラーページの有効期限は、対応する Campaign E メールチャネルアクティビティの設定画面で変更できます。 [詳細情報](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>オプトアウトの場合、Microsoft Dynamics 365 でオプトアウト属性を変更すると、 **単方向 (Campaign からMicrosoft Dynamics 365)** または **双方向** オプトアウト設定を使用する場合と、その特定の属性が正しくマッピングされている場合に、個別の属性を選択します。

## データフロー {#data-flows}

### 連絡先とカスタムエンティティの入力

新規レコード、更新レコード、削除されたレコード ( 注意：削除する必要があります ) をMicrosoft Dynamics 365 の連絡先テーブルから Campaign プロファイルテーブルに送信します。

統合アプリケーション UI で、Microsoft Dynamics 365 テーブル属性を Campaign テーブル属性にマッピングするようにテーブルマッピングを設定できます。 必要に応じて、テーブルマッピングを変更して属性を追加または削除できます。

データフローの初回実行は、「非アクティブ」とマークされたレコードを含む、すべてのマッピングされたレコードを転送するように設計されています。その後、統合で処理されるのは、増分更新のみです。 ただし、データが再生された場合や、フィルターが設定されている場合は例外です。基本的な属性ベースのフィルタリングルールを設定して、Campaign に同期するレコードを決定できます。

統合アプリケーションの UI で、属性値を別の値に置き換えるように基本的な置き換えルールを設定できます ( 例えば、「#00FF00」は「green」、「F」は「1」など )。

レコードの量に応じて、最初のデータ転送に Campaign の SFTP ストレージを使用する必要が生じる場合があります。 [詳細情報](#initial-data-transfer)。

連絡先の入力が機能するには、Campaign プロファイルテーブル属性 externalId に Dynamics 365 連絡先属性 contactId を設定する必要があります。 また、Campaign のカスタムエンティティには、Dynamics 365 の一意の ID 属性を設定する必要があります。ただし、この属性は任意の Campaign カスタムエンティティ属性に保存できます（つまり、externalId を指定する必要はありません）。

>[!NOTE]
>
>カスタムエンティティの入力の場合、同期されたカスタムエンティティに対して、Dynamics 365 内で変更追跡を有効にする必要があります。

#### カスタムエンティティ

この [Microsoft Dynamics 365 とAdobe Campaign Standardの統合](../../integrating/using/d365-acs-get-started.md) はカスタムエンティティをサポートし、Dynamics 365 のカスタムエンティティを Campaign の対応するカスタムリソースに同期できます。

カスタムリソースの新しいデータは、セグメント化やパーソナライゼーションなど、複数の目的で使用できます。

この統合では、リンクされたテーブルとリンクされていないテーブルの両方をサポートしています。 リンクは、最大 3 つのレベル (level1->level2->level3) までサポートされます。

>[!IMPORTANT]
>
>Campaign のカスタムリソースレコードに個人情報が含まれている場合は、特定の推奨事項が適用されます。 詳しくは、[この節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data)を参照してください。

カスタムエンティティのデータフローを設定する場合は、次の点に注意する必要があります。

* Campaign のカスタムリソースの作成と変更は機密性の高い操作で、エキスパートユーザーのみが実行する必要があります。
* カスタムエンティティのデータフローの場合、同期されたカスタムエンティティに対して、Dynamics 365 内で変更追跡を有効にする必要があります。
* Dynamics 365 で、親レコードとリンクされた子レコードがほぼ同じ時間で作成された場合、統合の並列処理により、親レコードの前に新しい子レコードが Campaign に書き込まれる可能性がわずかに高くなります。

* 親と子が **基数 1 のシンプルリンク** 」オプションを選択した場合、親レコードが Campaign に届くまで、子レコードは非表示のままになり、（UI または API を介して）アクセスできなくなります。

* ( 仮定 **基数 1 のシンプルリンク** Campaign 内 ) Dynamics 365 で子レコードが更新または削除され、その変更が Campaign に表示される前に Campaign に書き込まれた場合（可能性は低いがリモートの場合）、その更新または削除は Campaign で処理されず、エラーがスローされます。 更新の場合、更新されたレコードを同期するには、問題のレコードを Dynamics 365 で再度更新する必要があります。 削除または更新するレコードが Dynamics 365 になくなったので、削除の場合は、問題のレコードを Campaign 側で個別に処理する必要があります。

* 非表示の子レコードがあり、それらにアクセスできないと思われる状況が発生した場合は、カーディナリティリンクの種類を一時的に **基数 0 または 1 のシンプルリンク** をクリックして、これらのレコードにアクセスします。

Campaign のカスタムリソースの包括的な概要については、を参照してください。 [この節](../../developing/using/key-steps-to-add-a-resource.md).

### 電子メールマーケティングイベントフロー{#email-marketing-event-flow}

電子メールマーケティングイベントは、Campaign からMicrosoft Dynamics 365 に送信され、タイムラインビューに表示されます。

サポートされるマーケティングイベントタイプ：
* 送信 — 受信者に送信した電子メール
* 開く — 受信者が開封した E メール
* クリック — 受信者がクリックした電子メール内の URL
* バウンス — 受信者への E メールがハードバウンスを経験しました

Dynamics 365 内には、次のイベント属性が表示されます。
* マーケティングキャンペーン名
* E メール配信名
* タイムスタンプ
* E メールミラーページの URL
* URL のクリック（クリックイベントのみ）

電子メールマーケティングイベントは、タイプ（送信、開く、クリック、バウンス）ごとに有効/無効を切り替え、選択したイベントタイプのみが Dynamics 365 に渡されるようにします。

### オプトアウトフロー {#opt-out-flow}

オプトアウト ( 例：ブロックリスト) 値はシステム間で同期されます。オンボーディングの際に、次の選択肢から選択できます。

* **単方向 (Microsoft Dynamics 365 ～ Campaign)**:Dynamics 365 は、オプトアウトの情報源です。 オプトアウト属性は、Dynamics 365 からCampaign Standardへの一方向で同期されます。
* **単方向 (Campaign からMicrosoft Dynamics 365)**:Campaign Standardは、オプトアウトの情報源です。 オプトアウト属性は、Campaign Standardから Dynamics 365 への一方向で同期されます
* **双方向**:Dynamics 365 ANDCampaign Standardはどちらも真実の源です。 オプトアウト属性は、Dynamics と Dynamics 365 の間で双方向にCampaign Standardされます

また、システム間でオプトアウト同期を管理する別のプロセスがある場合は、統合のオプトアウトデータフローを無効にできます。

>[!NOTE]
>
>統合アプリケーション UI で、 **単方向 (Microsoft Dynamics 365 ～ Campaign)** そして **双方向** オプトアウトの使用例は、別のオプトアウトワークフローで設定します。 [詳細情報](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>この **単方向 (Campaign からMicrosoft Dynamics 365)** オプトアウトの使用例は例外です。これは、入口（プロファイルへの連絡）ワークフロー内で設定されます。

ビジネス要件は会社によって異なる場合があるので、オプトアウトフローマッピングは顧客が指定します。 キャンペーン側では、オプトアウトマッピングに使用できるのは OOTB オプトアウト属性のみです。

* ブロックリスト
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

Dynamics 365 では、ほとんどのオプトアウトフィールドには「donot」プレフィックスが付きます。ただし、データタイプに互換性がある場合は、他の属性をオプトアウト用に利用することもできます。

### 初期データ転送 {#initial-data-transfer}

Microsoft Dynamics 365 から取り込むレコード数によっては、初期データ転送に時間がかかる場合があります。 最初のデータ転送の後、統合は増分更新を受け取ります。
