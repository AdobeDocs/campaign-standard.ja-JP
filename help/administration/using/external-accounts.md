---
title: 外部アカウント
description: 外部アカウントを設定して、SFTP サーバーなどの外部システムとの接続をセットアップする方法を説明します
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 747e82ff-d3e6-4945-8f29-80e4a190c96f
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 78%

---

# 外部アカウント{#external-accounts}

外部アカウントとは、Adobe Campaign 外部にあるサーバーへのアクセスを設定およびテストできる設定です。

これらの外部アカウントをキャンペーンワークフローで使用して、データへアクセスしたり、データを管理したりできます。

次のタイプの外部アカウントをセットアップできます。

* SFTP。詳しくは、[この節](#sftp-external-account)を参照してください。
* アマゾンストレージサービス（S3）。詳しくは、[この節](#amazon-s3-external-account)を参照してください。
* Adobe Experience Manager。詳しくは、[この節](#adobe-experience-manager-external-account)を参照してください。
* Adobe Analytics。詳しくは、[この節](../../integrating/using/configure-campaign-analytics-integration.md)を参照してください。
* Google reCAPTCHA。詳しくは、[この節](#google-recaptcha-external-account)を参照してください。
* Microsoft Azure Blob ストレージ。詳しくは、[この節](#microsoft-azure-external-account)を参照してください。
* OAuth 2.0。詳しくは、[ この節 ](#oauth-account) を参照してください。

>[!NOTE]
>
>製品のプロビジョニングプロセス中に、アドビでは他のタイプの外部アカウントを使用します。Campaign Standard 17.9 リリース以降も、FTP 外部アカウントは定義可能ですが、新しいワークフローアクティビティでは使用できなくなりました。既に接続がセットアップされている場合は、それがそのまま有効になります。

外部アカウントは、**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;メニューを使用して管理者が設定できます。

## 外部アカウントの作成 {#creating-an-external-account}

Adobe Campaign には、事前定義済みの外部アカウントのセットが付属します。外部システム（ファイル転送に使用される FTP サーバーなど）との接続をセットアップするために、独自の外部アカウントを作成できます。

外部アカウントは、テクニカルワークフローやキャンペーンワークフロー等の技術プロセスで使用されます。ワークフローのファイル転送や、その他のアプリケーション（Adobe Target、Experience Manager など）とのデータ交換をセットアップする際には外部アカウントを選択する必要があります。

1. 「**[!UICONTROL Create]**」ボタンをクリックします。
1. ラベルを入力します。ラベルと ID は、ワークフローで外部アカウントを選択するときに使用されます。
1. 作成するアカウントのタイプを選択します。
1. 必要に応じて、資格情報、サーバーアドレス、ポート番号、キーなどを指定して、アカウントへのアクセスを設定します。

   必要な情報は通常、接続しているサーバーのプロバイダーから提供されます。

1. アカウントを保存します。

外部アカウントが作成され、アカウントリストに追加されます。ワークフローアクティビティと配信プロパティで、データ／ファイル転送またはルーティング設定を利用できるようになりました。

## SFTP 外部アカウント {#sftp-external-account}

外部アカウントのタイプが異なれば、指定する必要がある情報も異なります。

SFTP 外部アカウントの場合は、次の詳細情報を入力します。

* サーバーアドレス。例えば、**ftp.domain.com**。
* ポート番号。例えば、**22**。
* SFTP サーバーの資格情報：サーバーへの接続時に使用するアカウント名とパスワード。

### Adobeがホストする SFTP サーバーの推奨事項 {#adobe-hosted-sftp-server-recommendations}

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

また、SFTP 接続を開始しようとしているパブリック IP を、Campaign インスタンスの許可リストに追加する必要もあります。 許可リストへの IP アドレスの追加は、認証に使用する公開鍵と共に [ サポートチケット ](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) を介してリクエストできます。

SFTP サーバーは、コントロールパネルから管理できます。詳しくは、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=ja)を参照してください。

>[!NOTE]
>
>コントロールパネルは、すべての管理者ユーザーがアクセスできます。 ユーザーに管理者アクセス権を付与する手順については、[このページ](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=ja#discover-control-panel)で詳しく説明しています。

## OAuth 2.0 アカウント {#oauth-account}

OAuth 2.0 外部アカウントの場合は、次の詳細を入力します。

* **付与タイプ**: **クライアント資格情報** のみがサポートされます。
* **セキュア API URL**：認証エンドポイントを入力します。
* **OAuth 2.0 機密資格情報**：このセクションは、本質的に機密性が高い資格情報を対象としています。 資格情報は、追加後、画面上でマスクされます。その時点では、読み取りも編集もできません。 認証エンドポイントで、POST本文パラメーターではなく特定の資格情報を HTTP 認証ヘッダーに挿入する必要がある場合は、その資格情報に対して「ヘッダーに含める」オプションを選択できます。
* **OAuth 2.0 非依存資格情報**：このセクションは、本質的に非機密の資格情報を対象としています。 秘密鍵証明書の値は、追加後に画面に表示され、編集することもできます。  認証エンドポイントで、POST本文パラメーターではなく特定の資格情報を HTTP 認証ヘッダーに挿入する必要がある場合は、その資格情報に対して「ヘッダーに含める」オプションを選択できます。

アカウント情報を入力したら、「**接続をテスト**」をクリックして、外部アカウントが正しく設定されていることを確認します。

![](assets/external_accounts_OAuth.png)

>[!NOTE]
>
>「Content-Type: application/x-www-form-urlencoded」および「grant_type=client_credentials」資格情報が API 呼び出しに自動的に追加されるので、資格情報セクションでそれらを追加する必要はありません。

## Amazon S3 外部アカウント {#amazon-s3-external-account}

Amazon S3 サーバーフィールドには、次のように入力する必要があります。

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

ファイルを S3 暗号化モードで保存するには、「**[!UICONTROL Keep files in S3 encrypted]**」ボックスをオンにします。

![](assets/external_accounts_2.png)

必要な情報は通常、接続しているサーバーのプロバイダーから提供されます。

エンドポイントに関連付けられている「**[!UICONTROL AWS Region]**」を指定します。サポートされているリージョンと署名バージョンについては、[Amazon S3 の公式ドキュメント](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)を参照してください。

>[!NOTE]
>
>「**[!UICONTROL Receiver server]**」には、AWS リージョンを指定せずに入力してください。後で URL に自動的に追加されます。

### Amazon S3 アカウントに関する推奨事項 {#amazon-s3-account-recommendations}

Amazon S3 アカウントの設定に役立つように、次のレコメンデーションに従うことをお勧めします。

* S3 バケットへのアクセスを制限するために、厳密なバケットポリシーを作成する。バケットポリシーは、バケットの作成時に設定できます。詳しくは、[Amazon S3 のドキュメント](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)を参照してください。
* 外部アカウントを作成する際は、「**[!UICONTROL Keep files in S3 encrypted]**」ボックスをオンにして、機密データを S3 バケットに保存するための暗号化を有効にする。
* バケットの権限を付与して、バケット内のオブジェクトにアクセスできるユーザーを指定する。バケット権限について詳しくは、[Amazon S3 のドキュメントを](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)参照してください。

## Adobe Experience Manager の外部アカウント {#adobe-experience-manager-external-account}

Adobe Experience Manager 外部アカウントは、Campaign と Experience Manager を統合する場合に使用します。

この統合に関連するプロセスと要件については、[こちらのドキュメント](../../integrating/using/get-started-campaign-integrations.md)を参照してください。

この新しい外部アカウントを設定する際には、次の詳細を指定する必要があります。

* サーバー：Adobe Experience Manager サーバーの URL を入力します。例：

  ```
  http://aem.domain.com:4502
  ```

* AEM アカウントの資格情報：Adobe Experience Manager インスタンスにアクセスするアカウントを使用します。Experience Manager のキャンペーンリモートグループのアカウントに含める必要があります。

## Google reCAPTCHA 外部アカウント {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA を設定するには、Google アカウントが必要になります。

Google reCAPTCHA のメカニズムによって、ランディングページをスパムやボットによる不正使用から守ることができます。このメカニズムは、ユーザーによる操作が不要で、お客様のサイトとのやり取りに基づいているので、ユーザーにとっては負担になりません。サイトの登録については、[こちらのページ](https://www.google.com/recaptcha/admin/create)を参照してください。V3 reCAPTCHA タイプを選択する必要があります。

Google reCAPTCHA V3 をランディングページに追加するには、外部アカウントで設定します。 ランディングページに Google reCAPTCHA V3 を追加する方法について詳しくは、[この節](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)を参照してください。

Google reCAPTCHA V3 外部アカウントの場合は、次の詳細情報を入力します。

* 外部アカウントの「**[!UICONTROL Label]**」と「**[!UICONTROL ID]**」
* **[!UICONTROL Type]**：Google reCAPTCHA
* お使いの「**[!UICONTROL Site key]**」と「**[!UICONTROL Site secret]**」
* 0～1 の範囲の「**[!UICONTROL Threshold]**」

  「**[!UICONTROL Threshold]**」が 0.0 の場合は、ボットである可能性が高く、1.0 の場合は適正なインタラクションである可能性が高いことを意味します。デフォルトでは、0.5 のしきい値を使用できます。

![](assets/external_accounts_3.png)

## Microsoft Azure Blob ストレージ外部アカウント {#microsoft-azure-external-account}

>[!NOTE]
>
>Adobe Campaign Standard で外部アカウントを設定するのに必要な情報は、Azure Portal で&#x200B;**[!UICONTROL Settings]**／**[!UICONTROL Access keys]**&#x200B;を選択すれば、確認できます。

Azure BLOB ストレージコネクタを使用できるのは、「**[!UICONTROL Transfer file]**」ワークフローアクティビティで Adobe Campaign に対してデータのインポートやエクスポートをおこなう場合です。詳しくは、[この節](../../automating/using/transfer-file.md#azure-blob-configuration-wf)を参照してください。

Microsoft Azure BLOB ストレージ外部アカウントの場合は、次の詳細情報を入力します。

* 外部アカウントの「**[!UICONTROL Label]**」と「**[!UICONTROL ID]**」
* **[!UICONTROL Type]**：Microsoft Azure Blob storage
* お使いの「**[!UICONTROL Account name]**」と「**[!UICONTROL Account key]**」。アカウント名とアカウントキーの確認方法については、[こちらのページ](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)を参照してください。
* お使いの「**[!UICONTROL Endpoint suffix]**」。これは、Azure Portal の&#x200B;**[!UICONTROL Access keys]**&#x200B;メニューの「**[!UICONTROL Connection string]**」内で確認できます。詳しくは、この[ページ](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)を参照してください。
* お使いの「**[!UICONTROL Container]**」。複数のコンテナを使用する場合は、コンテナと同じ数だけ外部アカウントを作成します。
* 「**[!UICONTROL Concurrency]**」オプションを使用すると、ファイル転送速度を微調整できます。

![](assets/external_accounts_4.png)

設定が完了したら、「**[!UICONTROL Test connection]**」をクリックして Adobe Campaign を Microsoft Azure BLOB ストレージにリンクします。

### Microsoft Azure Blob ストレージの推奨事項 {#azure-blob-recommendations}

**暗号化**

Adobe Campaign では、セキュリティで保護された接続（HTTPS）を使用して Microsoft Azure BLOB ストレージアカウントにアクセスします。

**アカウントキー**

外部アカウントを設定する際は、Azure Portal で利用できる&#x200B;**[!UICONTROL Account key]**&#x200B;のいずれかを使用する必要があります。アカウントキーの確認方法について詳しくは、この[ページ](https://docs.microsoft.com/ja-JP/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string)を参照してください。

**ファイル転送速度の最適化**

「**[!UICONTROL Concurrency]**」オプションを使用すると、ファイル転送速度を微調整できます。これは、ファイル転送の実行に使用するスレッドの数を表します。各スレッドで、BLOB の約 1 MB に相当する部分がダウンロードされます。それぞれがキューに格納されたうえで、ディスクに書き込まれます。スレッドの数を増やすと、ファイル転送中にアプリケーションが使用するリソースの負荷も増えることに注意してください。

ファイル転送が完了したら、ワークフローログでパフォーマンス指標を確認できます。

**再試行**

デフォルトでは、Azure BLOB のファイル転送時に最大 4 回まで再試行が可能です。Azure ストレージサービスで 503（サーバーがビジー状態）や 500（操作のタイムアウト）などのエラーコードが返された場合は、ストレージアカウントのスケーラビリティ限界に近づいているか、限界を超えている可能性があります。これは、新しいアカウントを使用している場合やテストを実行している場合に発生する可能性があります。

エラーが解決しない場合は、詳細メニューの&#x200B;**[!UICONTROL Administration]**／**[!UICONTROL Application Settings]**／**[!UICONTROL Options]**&#x200B;でオプションを作成して、再試行の回数を増やすことができます。

実装する場合、オプションは次のように作成する必要があります。

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
