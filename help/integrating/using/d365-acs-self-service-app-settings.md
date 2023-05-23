---
title: Campaign と Dynamics の統合アプリの設定
description: Campaign と Dynamics の統合アプリの設定方法を説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 3%

---

# システムと統合アプリの接続

## 統合アプリへの資格情報の追加

この **[!UICONTROL Settings]** 画面では、Microsoft Dynamics 365 とAdobeAPI の資格情報を指定できます。 また、Adobe Campaign SFTP インスタンスに関連する設定を指定することもできます。

### Microsoft Dynamics 365 資格情報

Microsoft Dynamics 365 資格情報は、統合アプリケーションがMicrosoft Dynamics 365 からデータを取り込む権限を付与します。  まず、画面に表示される手順に従う必要があります [Campaign 統合用のMicrosoft Dynamics 365 の設定](../../integrating/using/d365-acs-configure-d365.md) この画面に貼り付ける値を生成するために。 以下に示す入力は、この画面を参照します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:クライアント ID をで参照する方法を説明します。 [この節](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:でクライアントシークレットを生成する方法を説明します。 [この節](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:でテナント ID を検索する方法を説明します。 [この節](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:URL の形式は次のようになります。 `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI 資格情報

Adobe Campaign資格情報は、 [Adobe I/O](https://www.adobe.io/). 画面にアクセスする必要があります [設定Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) この節の入力を行う前に、ここでの指示に従ってください。

次の図は、設定と設定画面の入力との間のマッピングの詳細をAdobe I/Oで説明しています。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *秘密鍵*:これを定義するプロセスは、まず「公開鍵と秘密鍵のペアを生成」ボタンをクリックします。 これにより、ダウンロードする必要のある zip ファイルが作成されます。 ダウンロードしたら、ファイルを解凍します。これにより、certificate_pub.crt および private.key という 2 つのファイルが作成されます。 秘密鍵は、必ず安全な場所に配置し、共有しないでください。 private.key ファイルをテキストエディターで開きます。 テキストエディターの値全体をコピーします (PC では Ctrl + A キー、Macでは Command + A キー、Command + C キー )。 これには、「BEGIN PRIVATE KEY」と「END PRIVATE KEY」全体を含む行を含める必要があります。 この複数行テキスト全体を、設定画面の「秘密鍵」入力に貼り付けます。

* *URL*:この値は、https\://mc.adobe.io/のパターンに適合します。&lt;campaign-instance-name>. 統合アプリのヘッダーには、「Org」と「Instance」の両方が含まれます。 URL の「campaign-instance-name」部分は、このインスタンス値にある名前に過ぎません。

## Adobe Campaign SFTP 設定 {#ac-smtp-settings}

これらの設定はオプションです。 Adobe Campaign SFTP インスタンスを使用してコネクタからログを出力する場合は、定義する必要があります。 これは、統合の実行中に問題が発生し、出力が期待を満たさない理由をデバッグする必要がある場合に役立ちます。

SFTP サーバーを設定するもう 1 つの理由は、オプトイン/オプトアウトワークフローを実行する予定で、Adobe CampaignからMicrosoft Dynamics 365 にデータが流れている場合です。 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** または **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>SFTP フォルダーにアクセスしてダウンロードする情報は、ユーザーが担当します。 情報に個人データが含まれる場合、お客様は、適用されるプライバシーに関する法令に準拠する責任を負います。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)

Microsoft Dynamics 365 統合の Campaign SFTP 設定を定義するには、次のセクションにアクセスします。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

次を指定する必要があります。

* **SFTP ホスト**:このフィールドには次が含まれます： &lt;campaign-instance-name>.campaign.adobe.com. 統合アプリのヘッダーには、 **組織** および **インスタンス**. URL の「campaign-instance-name」部分は、このインスタンス値にある名前に過ぎません。

* **SFTP ユーザー**:SFTP ユーザーがいる場合は、ここに追加します。 それ以外の場合は、 [この節](#ac-control-panel-settings). プロセスの一部として、ユーザー名が表示されます。

* **SFTP キー**:SSH キーを持っている場合は、ここに追加します。 それ以外の場合は、 [この節](#ac-control-panel-settings).

* この **IP 範囲** がAdobe Campaign SFTP 設定に含まれる必要があります。 統合で SFTP エンドポイントを許可リストに加えるするには、これらの値を使用する必要があります。

* この **ログをAdobe Campaign SFTP に書き出しますか？** では、統合によってログ情報が SFTP エンドポイントに出力されるかどうかを決定できます。 これは、Adobe CampaignまたはMicrosoft Dynamics 365 が期待する情報を表示していない場合のデバッグに役立ちます。

## Adobe Campaignでの SFTP 設定 {#ac-control-panel-settings}

を使用した SFTP 管理の確認 [キャンペーンCampaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja) 以下の節で説明します。

* [SFTP 管理について](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html#sftp-management)

* [SFTP ストレージ管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [IP 範囲を追加](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [キーの管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [SFTP サーバーにログオンする](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

設定が完了したら、秘密鍵で SFTP サーバーにログインし、「d365_loads/exports」ディレクトリを作成します。

[このページにアクセス](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=ja#sftp-management) Adobe Campaign Standard SFTP サーバーに関する情報を参照してください。
