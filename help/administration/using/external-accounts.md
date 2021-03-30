---
solution: Campaign Standard
product: campaign
title: 外部アカウント
description: 外部アカウントを設定して、SFTP サーバーなどの外部システムとの接続をセットアップする方法を説明します。
audience: administration
content-type: reference
topic-tags: application-settings
context-tags: extAccount,main;extAccount,overview
feature: インスタンス設定
role: 管理者
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 83%

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
* OAuth 2.0。詳しくは、[このセクション](#oauth-account)を参照してください。

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

### アドビがホストする SFTP サーバーに関する推奨事項 {#adobe-hosted-sftp-server-recommendations}

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

また、SFTP接続を開始しようとするパブリックIPは、キャンペーンインスタンスの許可リストに追加する必要があります。 許可リストへのIPアドレスの追加は、[サポートチケット](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)を介してリクエストでき、認証に使用する公開鍵を提供できます。

SFTP サーバーは、コントロールパネルから管理できます。詳しくは、[コントロールパネルのドキュメント](https://docs.adobe.com/content/help/ja-JP/control-panel/using/sftp-management/about-sftp-management.html)を参照してください。

>[!NOTE]
>
>Campaign コントロールパネルは、すべての管理者ユーザーがアクセスできます。 ユーザーに管理者アクセスを許可する手順については、[このページ](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel)を参照してください。

## OAuth 2.0アカウント{#oauth-account}

OAuth 2.0外部アカウントの場合は、次の詳細を入力します。

* **許可の種類**:**クライアント資格情報**&#x200B;のみがサポートされます。
* **セキュアAPI URL**:認証エンドポイントを入力します。
* **OAuth 2.0の機密資格情報**:このセクションは、本質的に機密性の高い資格情報を対象としています。秘密鍵証明書の値は、追加された後に画面上でマスクされます。この時点では、読み取りや編集ができなくなります。 認証エンドポイントで、POSTのbodyパラメーターの代わりに特定の秘密鍵証明書をHTTP認証ヘッダーに挿入する必要がある場合は、その秘密鍵証明書の「ヘッダーに含める」オプションを選択できます。
* **OAuth 2.0の機密でない資格情報**:このセクションは、本質的に機密性の低い資格情報を対象としています。秘密鍵証明書の値は、追加された後、画面に表示されます。また、これらは編集可能になります。  認証エンドポイントで、POSTのbodyパラメーターの代わりに特定の秘密鍵証明書をHTTP認証ヘッダーに挿入する必要がある場合は、その秘密鍵証明書の「ヘッダーに含める」オプションを選択できます。

アカウント情報を入力したら、「**接続をテスト**」をクリックして、外部アカウントが正しく構成されていることを確認します。

![](assets/external_accounts_OAuth.png)

>[!NOTE]
>
>秘密鍵証明書「Content-Type:application/x-www-form-urlencoded&quot;と&quot;grant_type=client_credentials&quot;は、自動的にAPI呼び出しに追加されます。したがって、資格情報セクションに追加する必要はありません。

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

Amazon S3 アカウントの設定に役立つように、次の推奨事項に従うことをお勧めします。

* S3 バケットへのアクセスを制限するために、厳密なバケットポリシーを作成する。バケットポリシーは、バケットの作成時に設定できます。詳しくは、[Amazon S3 のドキュメント](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)を参照してください。
* 外部アカウントを作成する際は、「**[!UICONTROL Keep files in S3 encrypted]**」ボックスをオンにして、機密データを S3 バケットに保存するための暗号化を有効にする。
* バケットの権限を付与して、バケット内のオブジェクトにアクセスできるユーザーを指定する。バケット権限について詳しくは、[Amazon S3 のドキュメントを](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)参照してください。

## Adobe Experience Manager 外部アカウント {#adobe-experience-manager-external-account}

Adobe Experience Manager 外部アカウントは、Campaign と Experience Manager を統合する場合に使用します。

この統合に関連するプロセスと要件については、[こちらのドキュメント](../../integrating/using/get-started-campaign-integrations.md)を参照してください。

この新規外部アカウントを設定する際には、次の情報を提供する必要があります。

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

ランディングページに Google reCAPTCHA V3 を追加するには、まず、お使いの外部アカウントで Google ReCAPTCHA V3 を設定する必要があります。ランディングページに Google reCAPTCHA V3 を追加する方法について詳しくは、[この節](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)を参照してください。

Google reCAPTCHA V3 外部アカウントの場合は、次の詳細情報を入力します。

* 外部アカウントの「**[!UICONTROL Label]**」と「**[!UICONTROL ID]**」
* **[!UICONTROL Type]**：Google reCAPTCHA
* お使いの「**[!UICONTROL Site key]**」と「**[!UICONTROL Site secret]**」
* 0～1 の範囲の「**[!UICONTROL Threshold]**」

   「**[!UICONTROL Threshold]**」が 0.0 の場合は、ボットである可能性が高く、1.0 の場合は適正なインタラクションである可能性が高いことを意味します。デフォルトでは、0.5 のしきい値を使用できます。

![](assets/external_accounts_3.png)

## Microsoft Azure BLOB ストレージ外部アカウント {#microsoft-azure-external-account}

>[!NOTE]
>
>Adobe Campaign Standard で外部アカウントを設定するのに必要な情報は、Azure Portal で&#x200B;**[!UICONTROL Settings]**／**[!UICONTROL Access keys]**&#x200B;を選択すれば、確認できます。

Azure BLOB ストレージコネクタを使用できるのは、「**[!UICONTROL Transfer file]**」ワークフローアクティビティで Adobe Campaign に対してデータのインポートやエクスポートをおこなう場合です。詳しくは、[この節](../../automating/using/transfer-file.md#azure-blob-configuration-wf)を参照してください。

Microsoft Azure BLOB ストレージ外部アカウントの場合は、次の詳細情報を入力します。

* 外部アカウントの「**[!UICONTROL Label]**」と「**[!UICONTROL ID]**」
* **[!UICONTROL Type]**：Microsoft Azure Blob storage
* お使いの「**[!UICONTROL Account name]**」と「**[!UICONTROL Account key]**」。アカウント名とアカウントキーの確認方法については、[こちらのページ](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)を参照してください。
* お使いの「**[!UICONTROL Endpoint suffix]**」。これは、Azure Portal の&#x200B;**[!UICONTROL Access keys]**&#x200B;メニューの「**[!UICONTROL Connection string]**」内で確認できます。詳しくは、この[ページ](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)を参照してください。
* お使いの「**[!UICONTROL Container]**」。複数のコンテナを使用する予定がある場合は、コンテナと同じ数の外部アカウントを作成する必要があります。
* 「**[!UICONTROL Concurrency]**」オプションを使用すると、ファイル転送速度を微調整できます。

![](assets/external_accounts_4.png)

設定が完了したら、「**[!UICONTROL Test connection]**」をクリックして Adobe Campaign を Microsoft Azure BLOB ストレージにリンクします。

### Microsoft Azure BLOB ストレージ外部アカウントに関する推奨事項 {#azure-blob-recommendations}

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
