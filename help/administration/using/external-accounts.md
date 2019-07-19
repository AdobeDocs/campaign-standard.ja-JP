---
title: 外部アカウント
seo-title: 外部アカウント
description: 外部アカウント
seo-description: SFTPサーバーなどの外部システムとの接続を設定する外部アカウントを設定します。
page-status-flag: 常にアクティブ化されていない
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: アプリケーション設定
discoiquuid: d5c6a3d4- f767-46c1- a8c0-3b9dc52depa8
internal: n
snippet: y
context-tags: extAccount， main;ExtAccount，概要
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# External accounts{#external-accounts}

外部アカウントとは、Adobe Campaign以外のサーバーへのアクセスを設定およびテストできる設定です。

これらの外部アカウントは、Campaignワークフローで使用してデータにアクセスし、管理できます。

次のタイプの外部アカウントを設定できます。

* SFTP.For more on this, refer to [this section](../../administration/using/external-accounts.md#sftp-external-account).
* Amazon Storage Service（S3）For more on this, refer to [this section](../../administration/using/external-accounts.md#amazon-s3-external-account).
* Adobe Experience Managerを参照してください。For more on this, refer to [this section](../../administration/using/external-accounts.md#adobe-experience-manager-external-account).
* Adobe Analytics。For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google reCAPTCHA。For more on this, refer to [this section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

>[!NOTE]
>
>その他のタイプの外部アカウントは、製品のプロビジョニングプロセス中にアドビが使用します。キャンペーンStandard17.9リリースからは、FTP外部アカウントを定義できますが、新しいワークフローアクティビティでは使用できなくなります。接続が既に設定されている場合は、まだ有効になっています。

External accounts can be configured by administrators under the **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creating an external account {#creating-an-external-account}

Adobe Campaignには、事前定義済みの外部アカウントのセットが付属しています。ファイル転送に使用するFTPサーバーなどの外部システムと接続を設定するには、独自の外部アカウントを作成します。

外部アカウントは、技術的なワークフローやキャンペーンワークフローなどの技術プロセスで使用されます。ワークフローまたは他のアプリケーションとのデータ交換（Adobe Target、Experience Managerなど）にファイル転送をセットアップする場合は、外部アカウントを選択する必要があります。

1. Click the **[!UICONTROL Create]** button.
1. ラベルを入力します。ラベルとIDは、ワークフローで外部アカウントを選択するときに使用されます。
1. 作成するアカウントのタイプを選択します。
1. 資格情報、サーバーアドレス、ポート番号、またはキーを指定して、アカウントへのアクセスを設定します。

   必要な情報は、通常、接続先のサーバーのプロバイダーによって提供されます。

1. アカウントを保存します。

外部アカウントが作成され、アカウントリストに追加されます。ワークフローアクティビティおよび配信プロパティのデータ/ファイル転送またはルーティング設定に使用できるようになりました。

## SFTP external account {#sftp-external-account}

外部アカウントタイプによっては、異なる情報を指定する必要があります。

SFTPの外部アカウントについては、次の情報を入力してください。

* サーバーアドレス。For example, **ftp.domain.com**.
* ポート番号。For example, **22**.
* SFTPサーバー資格情報:サーバーへの接続に使用するアカウント名とパスワード。

### Adobe hosted SFTP server recommendations {#adobe-hosted-sftp-server-recommendations}

ETLのファイルとデータを管理する場合、これらのファイルはアドビが提供するホストされているSFTPサーバーに保存されます。このSFTPは、ファイルのリテンションと削除を制御できる一時的なストレージ領域になるように設計されています。

正しく使用または監視されていない場合、このスペースはサーバー上で使用可能な物理空間をすばやく埋めることができ、深刻な問題を引き起こす可能性があります。プラットフォームでデータの損失や破損が生じる可能性があります。

このような問題を回避するには、以下のベストプラクティスに従うことをお勧めします。

* 最小限のデータを保持します。
* パスワードの有効期限を避けるために、キーベースの認証を使用します。Supported formats are **OpenSSH** and **SSH2** only. アドビサポートチームに公開鍵を提供して、キャンペーンサーバーにアップロードする必要があります。
* 必要に応じてデータを保持します。15日は最大の時間制限です。
* ワークフローを使用してデータを適切に削除します（データを使用するワークフローから保持を管理します）。
* SFTPアップロードではバッチ処理、ワークフローではバッチ処理を使用します。
* エラー/例外を処理します。
* SFTPにログインして、そこにあるものを直接チェックすることもできます。
* SFTPディスク管理は主にお客様の責任です。

また、SFTP接続を開始するパブリックIPは、キャンペーンインスタンスにホワイトリスト登録されている必要があります。Whitelisting of IP addresses can be requested via a [support ticket](https://support.neolane.net), along with providing the public key to use for authentication.

SFTPサーバーは、コントロールパネルから管理できます。For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>コントロールパネルは、AWSでホストされているユーザーの管理者ユーザーのみが使用できます。
Check if your instance is hosted on AWS [here](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Amazon S3 external account {#amazon-s3-external-account}

Amazon S3サーバーフィールドは、以下のように入力します。

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

To store your file in S3 encrypted mode, check the **[!UICONTROL Keep files in S3 encrypted]** box.

![](assets/external_accounts_2.png)

必要な情報は、通常、接続先のサーバーのプロバイダーによって提供されます。

Specify the **[!UICONTROL AWS Region]** associated to your endpoint. You can check the supported regions and signature versions in the official [Amazon S3 documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) .

### Amazon S3 account recommendations {#amazon-s3-account-recommendations}

Amazon S3アカウントをセットアップするには、次の推奨事項に従うことをお勧めします。

* 厳密なバケットポリシーを作成して、S3バケットへのアクセスを制限します。バケットの作成時にバケットポリシーを設定できます。For more information, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* While creating an external account, enable the encryption to store sensitive data in the S3 bucket by checking the **[!UICONTROL Keep files in S3 encrypted]** box.
* バケットのオブジェクトにアクセスできるユーザーを指定するためのバケット権限を付与します。For more information on bucket permission, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

Adobe Experience Manager外部アカウントは、キャンペーンをExperience Managerと統合するときに使用されます。

Process and requirements related to this integration are available in [this document](../../integrating/using/about-campaign-integrations.md).

この新しい外部アカウントをセットアップする際には、次の情報を提供する必要があります。

* サーバー:Adobe Experience ManagerサーバーのURLを入力します。For example, **http://aem.domain.com:4502**.
* AEMアカウント資格情報:Adobe Experience Managerインスタンスにアクセスするアカウントを使用します。これは、Experience Managerのキャンペーンリモートグループのアカウント部分です。

## Google reCAPTCHA external account {#google-recaptcha-external-account}

>[!NOTE]
>
>GoogleのreCAPTCHA設定にはGoogleアカウントが必要です。

Google reCaptchaメカニズムを使用すると、ボットによるスパムや迷惑行為からランディングページを保護できます。これは顧客にとって不要な顧客であり、サイトのインタラクションに基づいているので、顧客にとって不都合なことです。To register your site, refer to this [page](https://www.google.com/recaptcha/admin/create). V3reCaptchAタイプを選択する必要があります。

ランディングページにGoogle reCAPTCHA V3を追加するには、まず外部アカウントで設定する必要があります。For more information on how to add it to your landing page, refer to this [section](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

Google reCaptCHA V3外部アカウントの場合は、次の情報を提供します。

* **[!UICONTROL Label]** 社外 **[!UICONTROL ID]** アカウント
* **[!UICONTROL Type]**:Google reCaptcha
* **[!UICONTROL Site key]** および **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   The 0.0 **[!UICONTROL Threshold]** value means that it is likely a bot and 1.0 likely a good interaction. デフォルトでは、しきい値0.5を使用できます。

![](assets/external_accounts_3.png)

