---
title: キャンペーンとダイナミクスの統合アプリを構成する
description: キャンペーン-Dynamics統合アプリの構成方法を説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM統合
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 4%

---


# 統合アプリを使用したシステムの接続

## 統合アプリケ追加ーションの資格情報

**[!UICONTROL Settings]**&#x200B;画面では、Microsoft Dynamics 365とAdobeAPIの資格情報を指定できます。 Adobe CampaignのSFTPインスタンスに関連する設定を指定することもできます。

### Microsoft Dynamics 365資格情報

Microsoft Dynamics 365資格情報は、Microsoft Dynamics 365からデータを取り込むための統合アプリケーション権限を与えます。  この画面に貼り付ける値を生成するには、まず画面[キャンペーン統合用のMicrosoft Dynamics 365を構成](../../integrating/using/d365-acs-configure-d365.md)の手順に従う必要があります。 以下に示す入力は、この画面を参照します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:この節では、クライアントIDを参照する方法 [を説明します](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:この節では、クライアントシークレットを生成する方法 [を説明します。](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:テナントIDを見つける方法については、 [この節を参照してください](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:URLの形式は「https://&lt;servername>.api.crm.dynamics.com/」です。

### AdobeAPI証明書

Adobe Campaign資格情報は、[Adobe I/O](https://www.adobe.io/)を使用して生成されます。 この節の入力を行う前に、[Adobe I/Oを設定](../../integrating/using/d365-acs-configure-adobe-io.md)画面を開き、の指示に従う必要があります。

次の図に、Adobe I/Oと設定画面の入力の間のマッピングの詳細を示します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *秘密鍵*:[公開/秘密キーペアの生成]ボタンをクリックして、この開始を定義するプロセス。これにより、ダウンロードする必要のあるzipファイルが作成されます。 ダウンロードしたファイルを解凍すると、certificate_pub.crtとprivate.keyという2つのファイルが作成されます。 private.keyは、安全な場所に配置し、共有しないでください。 private.keyファイルをテキストエディターで開きます。 テキストエディターで値全体をコピーします（PCではctrl-A、PCではctrl-C、Macではcommand-A、MCではcmd-C）。 これには、「BEGIN PRIVATE KEY」と「END PRIVATE KEY」全体を含む行が含まれます。 この複数行のテキスト全体を、設定画面の「秘密鍵」入力に貼り付けます。

* *URL*:この値は、https\://mc.adobe.io/のパターンに合わせて調整され&lt;campaign-instance-name>ます。統合アプリのヘッダーには、「組織」と「インスタンス」の両方が含まれます。 URLの「キャンペーンインスタンス名」部分は、このインスタンス値に含まれる名前にすぎません。

## Adobe CampaignSFTP設定{#ac-smtp-settings}

これらの設定はオプションです。 Adobe CampaignのSFTPインスタンスを使用してコネクタからログを出力する場合は、これらを定義する必要があります。 これは、統合の実行中に問題が発生し、出力が期待どおりにならない理由をデバッグする必要がある場合に役立ちます。

SFTPサーバーをセットアップするもう1つの理由は、オプトイン/アウトワークフローを実行する予定で、Adobe CampaignからMicrosoft Dynamics 365（**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;または&#x200B;**[!UICONTROL Bidirectional]**）にデータが流れる場合です。

>[!IMPORTANT]
>
>SFTPフォルダーにアクセスし、SFTPフォルダーからダウンロードする情報は、ユーザーが管理する必要があります。 個人情報が含まれる場合は、プライバシーに関する法令に準拠する責任があります。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。


Microsoft Dynamics 365統合のキャンペーンSFTP設定を定義するには、次のセクションにアクセスします。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

次を指定する必要があります。

* **SFTPホスト**:このフィールドには、 &lt;campaign-instance-name>.キャンペーン.adobe.comが含まれます。統合アプリのヘッダーには、**組織**&#x200B;と&#x200B;**インスタンス**&#x200B;の両方が含まれます。 URLの「キャンペーンインスタンス名」部分は、このインスタンス値に含まれる名前にすぎません。

* **SFTP User**:SFTPユーザーがいる場合は、ここに追加します。そうでない場合は、[このセクション](#ac-control-panel-settings)を参照してください。 プロセスの一部として、ユーザー名が表示されます。

* **SFTPキー**:SSHキーをお持ちの場合は、ここに追加します。そうでない場合は、[このセクション](#ac-control-panel-settings)を参照してください。

* **IP範囲**&#x200B;は、Adobe CampaignのSFTP設定に含める必要があります。 統合でSFTPエンドポイントを使用するには、これらを許可する必要があります。

* **ログをAdobe CampaignのSFTPにエクスポートしますか？** 統合によってログ情報がSFTPエンドポイントに出力されるかどうかを指定できます。これは、Adobe CampaignまたはMicrosoft Dynamics 365が期待する情報を表示していない場合のデバッグに使用できます。

## Adobe Campaign{#ac-control-panel-settings}のSFTPセットアップ

[キャンペーンCampaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)を使用してSFTP管理を検出するには、次のセクションを参照してください。

* [SFTP 管理について](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [SFTP ストレージ管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [追加IP範囲](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [キーの管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [SFTPサーバーにログオンする](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

設定が完了したら、秘密鍵を使用してSFTPサーバーにログインし、「d365_loads/exports」ディレクトリを作成します。

[Adobe Campaign StandardSFTPサーバの詳細については、この](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=ja#sftp-management) ページを参照してください。
