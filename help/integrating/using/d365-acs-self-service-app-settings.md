---
title: CampaignとDynamicsの統合アプリの設定
description: CampaignとDynamicsの統合アプリの設定方法を説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM 統合
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: f75df49e7957437df72c814aa9055d34770f22d6
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 5%

---

# システムと統合アプリの接続

## 統合アプリへの資格情報の追加

**[!UICONTROL Settings]**&#x200B;画面では、Microsoft Dynamics 365とAdobeAPIの資格情報を指定できます。 また、Adobe Campaign SFTPインスタンスに関連する設定を指定することもできます。

### Microsoft Dynamics 365資格情報

Microsoft Dynamics 365資格情報は、Microsoft Dynamics 365からデータを取り込むための統合アプリケーション権限を付与します。  この画面に貼り付ける値を生成するには、まず画面[Campaign統合用のMicrosoft Dynamics 365の設定](../../integrating/using/d365-acs-configure-d365.md)の手順に従う必要があります。 以下に示す入力は、この画面を参照します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:クライアントIDの参照方法については、この節を参 [照してください](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:クライアント秘密鍵の生成方法については、この節を [参照してください](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:テナントIDの見つけ方については、この節を参 [照してください](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:URLは  `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI資格情報

Adobe Campaignの資格情報は、[Adobe I/O](https://www.adobe.io/)を使用して生成されます。 この節の入力を行う前に、画面[Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)を設定し、その画面の指示に従う必要があります。

次の画像は、設定画面入力とAdobe I/Oのマッピングの詳細を説明します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *秘密鍵*:これを定義するプロセスは、「公開鍵/秘密鍵を生成」ボタンをクリックして開始します。これにより、ダウンロードする必要のあるzipファイルが作成されます。 ダウンロードしたら、ファイルを解凍し、certificate_pub.crtおよびprivate.keyという名前の2つのファイルを作成します。 秘密鍵は必ず安全な場所に配置し、共有しないでください。 private.keyファイルをテキストエディターで開きます。 テキストエディターの値全体をコピーします（PCではCtrl + Aキー、MacではCommand + Aキー、MacではCommand + Cキー）。 これには、「BEGIN PRIVATE KEY」と「END PRIVATE KEY」全体を含む行を含める必要があります。 この複数行テキスト全体を、設定画面の「秘密鍵」入力に貼り付けます。

* *URL*:この値は、https\://mc.adobe.io/のパターンに適合しま&lt;campaign-instance-name>す。統合アプリのヘッダーには、「組織」と「インスタンス」の両方が含まれます。 URLの「campaign-instance-name」部分は、このインスタンス値にある名前になります。

## Adobe Campaign SFTP設定 {#ac-smtp-settings}

これらの設定はオプションです。 Adobe Campaign SFTPインスタンスを使用してコネクタからログを出力する場合は、定義する必要があります。 これは、統合の実行中に問題が発生し、出力が期待どおりでない理由をデバッグする必要がある場合に役立ちます。

SFTPサーバーを設定するもう1つの理由は、オプトイン/アウトワークフローを実行する予定で、Adobe CampaignからMicrosoft Dynamics 365（**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;または&#x200B;**[!UICONTROL Bidirectional]**）へのデータのフローがある場合です。

>[!IMPORTANT]
>
>SFTPフォルダーにアクセスしてダウンロードする情報は、ユーザーが担当します。 個人情報が含まれる場合は、プライバシーに関する法令に準拠する責任を負います。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。


Microsoft Dynamics 365統合のCampaign SFTP設定を定義するには、次のセクションにアクセスします。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

次を指定する必要があります。

* **SFTPホスト**:このフィールドに &lt;campaign-instance-name>は.campaign.adobe.comが含まれます。統合アプリのヘッダーには、**Org**&#x200B;と&#x200B;**Instance**&#x200B;の両方が含まれます。 URLの「campaign-instance-name」部分は、このインスタンス値にある名前になります。

* **SFTPユーザー**:SFTPユーザーがいる場合は、ここに追加します。それ以外の場合は、[この節](#ac-control-panel-settings)を参照してください。 プロセスの一部として、ユーザー名が表示されます。

* **SFTPキー**:SSHキーを持っている場合は、ここに追加します。それ以外の場合は、[この節](#ac-control-panel-settings)を参照してください。

* Adobe Campaign SFTP設定に&#x200B;**IP範囲**&#x200B;を含める必要があります。 統合でSFTPエンドポイントを許可リストに加えるするには、これらのエンドポイントを使用する必要があります。

* **ログをAdobe Campaign SFTPに書き出しますか？** では、統合によってログ情報がSFTPエンドポイントに出力されるかどうかを指定できます。これは、Adobe CampaignまたはMicrosoft Dynamics 365で期待する情報が表示されていない場合のデバッグに役立ちます。

## Adobe CampaignでのSFTPの設定 {#ac-control-panel-settings}

以下の節で、[キャンペーンCampaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)を使用したSFTP管理について説明します。

* [SFTP 管理について](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=ja#sftp-management)

* [SFTP ストレージ管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [IP範囲の追加](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [キーの管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [SFTPサーバーへのログオン](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

設定が完了したら、秘密鍵でSFTPサーバーにログインし、「d365_loads/exports」ディレクトリを作成します。

[Adobe Campaign Standard SFTPサ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=ja#sftp-management) ーバーについては、このページを参照してください。
