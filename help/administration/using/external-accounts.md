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
source-git-commit: 7d31d92197a6bf26b7530b8e8ff42c0dc7f25359

---


# 外部アカウント{#external-accounts}

外部アカウントとは、Adobe Campaign 外部にあるサーバーへのアクセスを設定およびテストできる設定です。

これらの外部アカウントをキャンペーンワークフローで使用して、データへアクセスしたり、データを管理したりできます。

次のタイプの外部アカウントをセットアップできます。

* SFTP. 詳しくは、[この節](#sftp-external-account)を参照してください。
* Amazon Storage Service(S3)。 詳しくは、[この節](#amazon-s3-external-account)を参照してください。
* Adobe Experience Manager. 詳しくは、[この節](#adobe-experience-manager-external-account)を参照してください。
* Adobe Analytics。 詳しくは、[この節](../../integrating/using/configure-campaign-analytics-integration.md)を参照してください。
* Google reCAPTCHA. 詳しくは、[この節](#google-recaptcha-external-account)を参照してください。
* Microsoft Azure BLOBストレージ。 詳しくは、[この節](#microsoft-azure-external-account)を参照してください。

>[!NOTE]
>
>その他のタイプの外部アカウントは、製品のプロビジョニングプロセスでアドビが使用します。 Campaign Standard 17.9リリースからは、FTP外部アカウントは引き続き定義できますが、新しいワークフローアクティビティでは使用できなくなりました。 既に接続が設定されている場合は、その接続は有効です。

外部アカウントは、管理者がメニューの下で設定で **[!UICONTROL Administration > Application settings > External accounts]** きます。

## 外部アカウントの作成 {#creating-an-external-account}

Adobe Campaign には、事前定義済みの外部アカウントのセットが付属します。外部システム（ファイル転送に使用される FTP サーバーなど）との接続をセットアップするために、独自の外部アカウントを作成できます。

外部アカウントは、テクニカルワークフローやキャンペーンワークフロー等の技術プロセスで使用されます。ワークフローのファイル転送や、その他のアプリケーション（Adobe Target、Experience Manager など）とのデータ交換をセットアップする際には外部アカウントを選択する必要があります。

1. ボタンをクリッ **[!UICONTROL Create]** クします。
1. ラベルを入力します。 ワークフローで外部アカウントを選択する際に、ラベルとIDが使用されます。
1. 作成するアカウントのタイプを選択します。
1. 関連する場合は、資格情報、サーバーアドレス、ポート番号、またはキーを指定して、アカウントへのアクセスを設定します。

   必要な情報は通常、接続しているサーバーのプロバイダーから提供されます。

1. アカウントを保存します。

外部アカウントが作成され、アカウントリストに追加されます。 ワークフローアクティビティと配信プロパティで、データファイル転送またはルーティング設定を利用できるようになりました。

## SFTP 外部アカウント {#sftp-external-account}

外部アカウントの種類ごとに異なる情報を指定する必要があります。

SFTP外部アカウントの場合は、次の詳細を入力します。

* サーバーアドレス. 例： **ftp.domain.com**。
* ポート番号。 For example, **22**.
* SFTPサーバー資格情報：サーバーへの接続に使用するアカウント名とパスワード。

### アドビがホストするSFTPサーバーの推奨事項 {#adobe-hosted-sftp-server-recommendations}

ETL のためのファイルやデータを管理する際、これらのファイルはアドビがホストする SFTP サーバー上に保存されます。この SFTP は、ファイルの保持や削除を制御できる一時的なストレージスペースになるように設計されています。

このスペースの使用または監視が適切におこなわれていない場合、サーバー上の使用可能な物理スペースがすぐにいっぱいになって重大な問題が生じる可能性があります。結果として、プラットフォームでのデータの消失や破壊につながるおそれがあります。

こうした問題を回避するために、アドビでは以下のベストプラクティスに従うことをお勧めします。

* データをできるだけ最小限に抑える。
* パスワードの有効期限切れを防ぐために鍵ベースの認証を使用する。サポートされる形式は、**OpenSSH** と **SSH2** のみです。アドビのサポートチームに公開鍵を提供して、Campaign サーバーにアップロードしてもらう必要があります。
* 必要な期間だけデータを保持します。15 日がその期間の上限です。
* データを適切に削除するには、ワークフローを使用します（データを消費しているワークフローから保持を管理）。
* SFTP アップロードやワークフローでバッチ処理を使用します。
* エラー／例外を処理します。
* 時々 SFTP にログインして、問題がないか直接確認します。
* SFTP のディスク管理は、基本的に管理者の責任となります。

また、SFTP 接続の開始の試行元になるパブリック IP は Campaign インスタンスのホワイトリストに登録されている必要があります。ホワイトリストへの IP アドレスの登録は、認証に使用する公開鍵の提供と同様に、[サポートチケット](https://support.neolane.net)によって依頼できます。

SFTPサーバーは、コントロールパネルから管理できます。 For more information, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/sftp-management/about-sftp-management.html).

>[!NOTE]
>
>コントロールパネルは、AWSでホストされるお客様の管理者ユーザーのみが使用できます。
インスタンスがAWSでホストされているかどうかを確認 [します](https://docs.adobe.com/content/help/en/control-panel/using/faq.html#ims-org-id)。

## Amazon S3 external account {#amazon-s3-external-account}

Amazon S3サーバーのフィールドには、次のように入力します。

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

ファイルをS3暗号化モードで保存するには、ボックスをオンに **[!UICONTROL Keep files in S3 encrypted]** します。

![](assets/external_accounts_2.png)

必要な情報は通常、接続しているサーバーのプロバイダーから提供されます。

エンドポイントに **[!UICONTROL AWS Region]** 関連付けられているを指定します。 サポートされる地域と署名のバージョンは、 [Amazon S3の公式ドキュメントで確認できます](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)。

>[!NOTE]
>
>AWSリー **[!UICONTROL Receiver server]** ジョンを入力しないで、後でURLに自動的に追加されます。

### Amazon S3アカウントの推奨事項 {#amazon-s3-account-recommendations}

Amazon S3アカウントの設定を支援するため、以下の推奨事項に従うことをお勧めします。

* S3バケットへのアクセスを制限する厳密なバケットポリシーを作成します。 バケットポリシーは、バケットの作成時に設定できます。 For more information, refer to the [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* 外部アカウントの作成時に、このチェックボックスをオンにして、機密データをS3バケットに保存する暗号化を有効に **[!UICONTROL Keep files in S3 encrypted]** します。
* バケットの権限を付与して、バケット内のオブジェクトにアクセスできるユーザーを指定します。 バケット権限の詳細については、 [Amazon S3のドキュメントを参照してください](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)。

## Adobe Experience Manager の外部アカウント {#adobe-experience-manager-external-account}

Adobe Experience Managerの外部アカウントは、CampaignとExperience Managerを統合する際に使用されます。

このドキュメントでは、この統合に関連するプロセスと要件を [説明します](../../integrating/using/about-campaign-integrations.md)。

この新規外部アカウントを設定する際には、次の情報を提供する必要があります。

* サーバー：adobe Experience ManagerサーバーのURLを入力します。 例えば、 **http://aem.domain.com:4502**。
* AEMアカウントの資格情報：adobe Experience Managerインスタンスにアクセスするアカウントを使用します。 Experience Managerのキャンペーンリモートグループのアカウントの一部にする必要があります。

## Google reCAPTCHA外部アカウント {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHAの設定にはGoogleアカウントが必要です。

Google reCAPTCHAメカニズムを使用すると、ボットによるスパムや悪用からランディングページを保護できます。 顧客からのインタラクションは不要で、サイトでのインタラクションに基づいているので、顧客にとっては侵入しないことです。 サイトを登録するには、このページを参照して [ください](https://www.google.com/recaptcha/admin/create)。 V3 reCAPTCHAタイプを選択する必要があります。

Google reCAPTCHA V3をランディングページに追加するには、まず外部アカウントで設定する必要があります。 ランディングページに追加する方法の詳細については、このセクションを参照してく [ださい](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)。

Google reCAPTCHA V3外部アカウントの場合は、次の詳細を入力します。

* お客様 **[!UICONTROL Label]** の外部ア **[!UICONTROL ID]** カウントの
* **[!UICONTROL Type]**: Google reCAPTCHA
* およ **[!UICONTROL Site key]** び **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** - 0 ～ 1

   値が0.0の場合、ボ **[!UICONTROL Threshold]** ットである可能性が高く、1.0の場合は適切な操作である可能性が高くなります。 デフォルトでは、しきい値0.5を使用できます。

![](assets/external_accounts_3.png)

## Microsoft Azure BLOBストレージ外部アカウント {#microsoft-azure-external-account}

>[!NOTE]
>
>Adobe Campaign Standardで外部アカウントを構成するために必要な情報は、Azure Portalで、>を選択して参照で **[!UICONTROL Settings]** きます **[!UICONTROL Access keys]**。

Microsoft Azure BLOBストレージ外部アカウントの場合は、次の詳細を入力します。

* お客様 **[!UICONTROL Label]** の外部ア **[!UICONTROL ID]** カウントの
* **[!UICONTROL Type]**:Microsoft Azure Blobストレージ
* お前 **[!UICONTROL Account name]** と **[!UICONTROL Account key]**。 To know where to find your account name and key, refer to this [page](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage).
* あなた **[!UICONTROL Endpoint suffix]**&#x200B;の。 Azure Portalのメニュー **[!UICONTROL Connection string]** 内にあ **[!UICONTROL Access keys]** ります。 詳しくは、この[ページ](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)を参照してください。
* お名 **[!UICONTROL Container]** 前。 複数のコンテナを使用する場合は、コンテナと同じ数の外部アカウントを作成する必要があります。
* このオ **[!UICONTROL Concurrency]** プションを使用すると、ファイル転送の速度を微調整できます。

![](assets/external_accounts_4.png)

構成が完了したら、クリ **[!UICONTROL Test connection]** ックしてAdobe CampaignをMicrosoft Azure Blobストレージにリンクします。

### Microsoft Azure BLOBストレージの推奨事項 {#azure-blob-recommendations}

**暗号化**

Adobe Campaignは、セキュリティで保護された接続(HTTPS)を使用してMicrosoft Azure BLOBストレージアカウントにアクセスします。

**アカウントキー**

外部アカウントを構成する場合は、Azure Portalで使用可能ないずれかの **[!UICONTROL Account key]** アカウントを使用する必要があります。 アカウントキーの検索場所の詳細については、このページを参照してく [ださい](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string)。

**ファイル転送速度の最適化**

このオ **[!UICONTROL Concurrency]** プションを使用すると、ファイル転送の速度を微調整できます。
ファイル転送の実行に使用されるスレッドの数を表します。 これらの各スレッドは、約1 MBの部分をBLOBからダウンロードします。 その後、ディスクに書き込むためのキューに格納されます。 スレッドの数を増やすと、ファイル転送中にアプリケーションが使用するリソースの負荷も増えます。

ファイル転送の完了後は、ワークフローログにパフォーマンス指標が表示されます。

**再試行**

既定では、Azure Blobのファイル転送には最大4回の再試行が含まれます。  Azure Storageサービスが503 （サーバービジー）や500 （操作のタイムアウト）などのエラーコードを返す場合は、ストレージアカウントのスケーラビリティに近づいているか、それを超えている可能性があります。 これは、新しいアカウントを使用する場合や、テストを実行する場合に発生する可能性があります。

エラーが引き続き発生する場合は、詳細メニュー/[ ]>[ ]の下のオプションを作成して、再試行回数を増や **[!UICONTROL Administration]** すことが **[!UICONTROL Application Settings]** できま **[!UICONTROL Options]**&#x200B;す。

実装する場合は、次のようにオプションを作成する必要があります。

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
