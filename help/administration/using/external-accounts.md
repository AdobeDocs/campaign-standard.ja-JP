---
title: 外部アカウント
description: 外部アカウントを設定して、SFTPサーバーなどの外部システムとの接続を設定します。
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: tm+mt
source-git-commit: 68921819a5335626e45678ec569172ffef46a636

---


# 外部アカウント{#external-accounts}

外部アカウントとは、Adobe Campaignの外部にあるサーバーへのアクセスを設定およびテストできる設定です。

これらの外部アカウントは、Campaignワークフローで使用して、データにアクセスし、管理できます。

次のタイプの外部アカウントを設定できます。

* SFTP. 詳しくは、[この節](#sftp-external-account)を参照してください。
* Amazon Storage Service(S3)。 詳しくは、[この節](#amazon-s3-external-account)を参照してください。
* Adobe Experience Managerを参照してください。 詳しくは、[この節](#adobe-experience-manager-external-account)を参照してください。
* Adobe Analytics。 詳しくは、[この節](../../integrating/using/configure-campaign-analytics-integration.md)を参照してください。
* Google reCAPTCHA。 詳しくは、[この節](#google-recaptcha-external-account)を参照してください。

>[!NOTE]
>
>その他のタイプの外部アカウントは、製品のプロビジョニングプロセス中にアドビによって使用されます。 Campaign Standard 17.9リリースからは、FTP外部アカウントは引き続き定義できますが、新しいワークフローアクティビティでは使用できなくなりました。 既に接続が設定されている場合は、その接続は有効のままです。

外部アカウントは、メニューの下の管理者が設定で **[!UICONTROL Administration > Application settings > External accounts]** きます。

## 外部アカウントの作成 {#creating-an-external-account}

Adobe Campaignには、事前定義された外部アカウントのセットが付属しています。 ファイル転送に使用するFTPサーバーなどの外部システムとの接続を設定するには、独自の外部アカウントを作成します。

外部アカウントは、技術ワークフローやキャンペーンワークフローなどの技術プロセスで使用されます。 ワークフロー内のファイル転送や、他のアプリケーション（Adobe Target、Experience Managerなど）とのデータ交換を設定する場合は、外部アカウントを選択する必要があります。

1. Click the **[!UICONTROL Create]** button.
1. ラベルを入力します。 ワークフローで外部アカウントを選択する際に、ラベルとIDが使用されます。
1. 作成するアカウントのタイプを選択します。
1. 関連する場合は、資格情報、サーバーアドレス、ポート番号またはキーを指定して、アカウントへのアクセスを設定します。

   必要な情報は、通常、接続先のサーバーのプロバイダーから提供されます。

1. アカウントを保存します。

外部アカウントが作成され、アカウントリストに追加されます。 これで、ワークフローアクティビティと配信プロパティのデータ/ファイル転送またはルーティング設定で使用できるようになります。

## SFTP外部アカウント {#sftp-external-account}

外部アカウントの種類ごとに異なる情報を指定する必要があります。

SFTP外部アカウントの場合は、次の詳細を入力します。

* サーバーアドレス. 例： **ftp.domain.com**。
* ポート番号。 例えば、 **22と入力します**。
* SFTPサーバー資格情報：サーバーへの接続に使用するアカウント名とパスワード。

### アドビがホストするSFTPサーバーの推奨事項 {#adobe-hosted-sftp-server-recommendations}

ETLの目的でファイルとデータを管理する場合、これらのファイルはアドビが提供するホストされたSFTPサーバーに保存されます。 このSFTPは、ファイルの保存と削除を管理できる一時的なストレージ領域にするように設計されています。

正しく使用または監視されない場合、この領域は、サーバー上で利用可能な物理領域をすぐに満たし、重大な問題を引き起こす可能性があります。 プラットフォーム上でデータの消失や破損が発生する可能性があります。

このような問題を回避するには、次のベストプラクティスに従うことをお勧めします。

* 可能な限り最小限のデータを保持します。
* キーベースの認証を使用して、パスワードの有効期限を回避します。 サポートされてい **る形式は** OpenSSH **、** SSH2のみです。 公開鍵をCampaignサーバーにアップロードするには、アドビのサポートチームに公開鍵を提供する必要があります。
* 必要な期間だけデータを保持します。 15日が上限です。
* ワークフローを使用して、データを正しく削除します（データを消費するワークフローから保持を管理します）。
* ワークフローと同様に、SFTPアップロードでのバッチ処理を使用します。
* エラー/例外を処理します。
* SFTPにログインして、そこに何があるかを直接確認する場合があります。
* SFTPディスク管理は主にお客様の責任です。

また、SFTP接続を開始しようとするパブリックIPは、Campaignインスタンスでホワイトリストに登録されている必要があります。 IPアドレスのホワイトリストは、認証に使用する公開鍵 [を提供すると共に](https://support.neolane.net)、サポートチケットを通じてリクエストできます。

SFTPサーバーは、コントロールパネルから管理できます。 詳細については、「コントロールパネル」のドキュメ [ントを参照してくださ](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html)い。

>[!NOTE]
>
>コントロールパネルは、AWSでホストされるお客様の管理者ユーザーのみが使用できます。
インスタンスがAWSでホストされているかどうかを確認 [します](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID)。

## Amazon S3外部アカウント {#amazon-s3-external-account}

Amazon S3サーバーのフィールドには、次のように入力します。

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

ファイルをS3暗号化モードで保存するには、ボックスをオンに **[!UICONTROL Keep files in S3 encrypted]** します。

![](assets/external_accounts_2.png)

必要な情報は、通常、接続先のサーバーのプロバイダーから提供されます。

エンドポイントに **[!UICONTROL AWS Region]** 関連付けられているを指定します。 サポートされている地域と署名のバージョンは、 [Amazon S3の公式ドキュメントで確認できます](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)。

>[!NOTE]
>
>AWSリー **[!UICONTROL Receiver server]** ジョンを入力しないでお客様のURLに入力する必要があります。後で、URLに自動的に追加されます。

### Amazon S3アカウントの推奨事項 {#amazon-s3-account-recommendations}

Amazon S3アカウントの設定を支援するため、以下の推奨事項に従うことをお勧めします。

* S3バケットへのアクセスを制限する厳密なバケットポリシーを作成します。 バケットポリシーは、バケットの作成時に設定できます。 詳しくは、 [Amazon S3のドキュメントを参照してください](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)。
* 外部アカウントを作成する際に、このチェックボックスをオンにして、S3バケットに機密データを保存する暗号化を有効に **[!UICONTROL Keep files in S3 encrypted]** します。
* バケット権限を付与して、バケット内のオブジェクトにアクセスできるユーザーを指定します。 バケット権限について詳しくは、 [Amazon S3のドキュメントを参照してください](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager外部アカウント {#adobe-experience-manager-external-account}

Adobe Experience Managerの外部アカウントは、CampaignとExperience Managerを統合する際に使用します。

この統合に関連するプロセスと要件は、このドキュメントで [説明します](../../integrating/using/about-campaign-integrations.md)。

この新しい外部アカウントを設定する際は、次の詳細を指定する必要があります。

* サーバー：adobe Experience ManagerサーバーのURLを入力します。 例えば、http://aem.domain.com:4502 **です**。
* AEMアカウント資格情報：adobe Experience Managerインスタンスにアクセスするアカウントを使用します。 Experience Managerのキャンペーンリモートグループのアカウント部分にする必要があります。

## Google reCAPTCHA外部アカウント {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA設定にはGoogleアカウントが必要です。

Google reCAPTCHAメカニズムを使用すると、ボットによるスパムや悪用からランディングページを保護できます。 顧客からのインタラクションは不要で、サイトでのインタラクションに基づいているので、顧客にとってこれは押し付けがましいものです。 サイトを登録するには、このページを参照してく [ださい](https://www.google.com/recaptcha/admin/create)。 V3 reCAPTCHAタイプを選択する必要があります。

Google reCAPTCHA V3をランディングページに追加するには、まず外部アカウントでGoogle ReCAPTCHA V3を設定する必要があります。 ランディングページに追加する方法の詳細については、この節を参照してく [ださい](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)。

Google reCAPTCHA V3外部アカウントの場合は、次の情報を入力します。

* お客様 **[!UICONTROL Label]** の外部ア **[!UICONTROL ID]** カウントの
* **[!UICONTROL Type]**:Google reCAPTCHA
* お **[!UICONTROL Site key]** よび **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   0.0の値は、ボッ **[!UICONTROL Threshold]** トの可能性が高く、1.0の場合は適切な相互作用を示します。 デフォルトでは、しきい値0.5を使用できます。

![](assets/external_accounts_3.png)
