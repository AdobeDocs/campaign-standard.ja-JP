---
title: Microsoft Dynamics 365統合用のUnifiの構成
description: Microsoft Dynamics 365統合用のUnifiを構成する方法を説明します。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---



# Microsoft Dynamics 365統合用のUnifiの構成

Microsoft Dynamics 365 - Adobe Campaign統合をセットアップし、アクティブ化するようにUnifiを設定します。

## 前提条件

この記事のプロビジョニング後の手順を実行する前に、キャンペーンおよび [Dynamics 365のプロビジョニング後の手順が正常に完了してい](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) る [ことを前](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)提としています。  この問題が発生しない場合は、次の手順に従って、Campaign StandardとDynamics 365のプロビジョニング後を完了する必要があります。

また、Unifiに接続し、Unifiアカウントを作成済みで、正常にログインできたことも前提となります。  この問題が発生しない場合は、この記事で説明されている手順に従 [ってください](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

>[!CAUTION]
>
>Unifiを設定する際は、Unifiまたはアドビのコンサルティング（Adobe CSMにお問い合わせください）を利用することを強くお勧めします。

## キャンペーン統合の設定

最初の接続時に、をクリックして **[!UICONTROL Adobe Campaign Standard]** キャンペーンの資格情報を入力します。

これらの資格情報のほとんどは、 [Campaign Standardの設定手順でAdobe I/Oコンソールで作成した統合から取得されます](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

>[!NOTE]
>
>セキュリティとプライバシーを確保するため、これらの設定画面を再訪する際に、機密性の高い資格情報のフィールドが空白で表示されます。

1. 「Adobe認証URL」に、 `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. とを入力 **[!UICONTROL Adobe IO Organization ID]** します **[!UICONTROL Adobe IO Integration ID]**。

Adobe IO組織と統合IDを取得するには、Adobe I/Oコンソール統合画面に移動し、Web URLをメモします。

次のようになります。組 `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`織IDと整数IDは数値です。

1. 入力した **[!UICONTROL Tenant ID]**

テナントIDを取得するには、次の手順に従います。

1. Adobe Admin Consoleに移 [動し](https://adminconsole.adobe.com/) 、右上のドロップダウンメニューからIMS組織を選択します。
1. Adobe Campaign Standard製品を選択し、Campaign Standardインスタンスを選択します（複数ある場合）。  これにより、製品のリストが表示されます。

   製品プロファイルの説明は、通常、次のいずれかの形式で表示されます。 `<tenantID>` はインスタンスのテナントIDです。

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>テナントIDの識別で問題が発生した場合は、担当者/アドビのテクニカルサポート担当者またはアドビカスタマーケアにお問い合わせください。
>
>通常、パートナーサンドボックスインスタンステナントIDは、のパタ `https://<tenantId>`ーンに従い `tenantId` ます（を参照） `tbd.campaign-sandbox.adobe.com`。

1. を入力しま **[!UICONTROL Campaign Instance ID]**&#x200B;す。

インスタンスIDを取得するには、次の手順に従います。

    1.Webブラウザーに&#39;https://&lt;acs-instance-url>/r/test&#39;と入力し、`&lt;acs-instance-url>&#39;をCampaign StandardインスタンスのURLに置き換えます。
    1.応答には、&#39;instance=&#39;が含まれ、その後にインスタンスIDが続きます。

1. 領域インスタンスのキャンペーンを選択します。

1. 空白にしておいてもか **[!UICONTROL Base Directory]** まいません。

1. オプションを選 **[!UICONTROL Allow as Output Destination]** 択します。

パラメーターを設定したら、をクリックし、接 **[!UICONTROL CONNECT]** 続が成功したことを確認します。

そうでない場合は、をクリックしてパラ **[!UICONTROL CLOSE]** メータを確認してください。

>[!NOTE]
>
>この手順を完了できない場合は、 [Unifiカスタマーサービスにお問い合わせください](mailto:support@unifisoftware.atlassian.net)。

## Dynamics 365統合の構成

[Microsoft Dynamics CRM]をクリックして、Dynamics 365資格情報を構成します。 これらの資格情報のほとんどは、Microsoft Dynamics 365の構成手順でMicrosoft Dynamics 365で作成した統合から取得されます。

>[!NOTE]
>
>セキュリティとプライバシーを確保するため、これらの設定画面を再訪する際に、機密性の高い資格情報のフィールドが空白で表示されます。

1. 例え **[!UICONTROL URL]**&#x200B;ば、Dynamics 365インスタンスのURLを入力し、「.crm」の前に「.api」を挿入するように注意します(例： `https://mydynamicsinstance.api.crm.dynamics.com`)

1. たとえ **[!UICONTROL clientid]**&#x200B;ば、Dynamics 365を設定する際にアプリの登録を作成したときに生成されたアプリケーション ID [を使用します](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. たとえ **[!UICONTROL clientsecret]**&#x200B;ば、Dynamics 365を設定する際にアプリの登録にクライアントシークレットを追加したときに生成されたクライアントシークレ [ットを使用します](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. に、を **[!UICONTROL callbackurl]**&#x200B;追加しま `http://localhost:33333`す。

1. の場合は、 **[!UICONTROL refresh token]**&#x200B;空白のままにします。

1. テナ **[!UICONTROLントIDにつ]**&#x200B;いては [、portal.azure.comから取得したテナントIDをDynamics 365の構成として](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)使用します。

1. 最後に、のチェックボックスをオンにしま **[!UICONTROL Allow as Output Destination]**&#x200B;す。

パラメーターを入力したら、をクリックし、接 **[!UICONTROL CONNECT]** 続が成功したことを確認します。

そうでない場合は、をクリックしてパラ **[!UICONTROL CLOSE]** メータを確認してください。

>[!NOTE]
>
>この手順を完了できない場合は、 [Unifiカスタマーサービスにお問い合わせください](mailto:support@unifisoftware.atlassian.net)。

## Unifiの設定の完了

資格情報を設定したら、統合の設定を完了する前に、追加の手順を実行する必要があるので、Unifiに通知する必要があります。  資格情報を設定したことを示すUnifiの連絡先情報を表示します。

オプトアウトオプションを選択し、完了したらUnifiに通知する必要があります（オプトアウトオプションを選択するUnifiを指定します）。  オプトアウトオプションの説明は、『 [Unifi User Guide』を参照してください](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)。

Unifiが作業を完了すると、Unifiインスタンスの設定、データ入力の実行、完了後のスケジュールの有効化に役立つ詳細情報が通知されます。

様々な使用例では、次の頻度をお勧めします。

* 入力：15分ごと
* 出力：15分ごと
* 削除：毎日
* オプトアウト：毎日

>[!NOTE]
>
>デフォルトでは、SENDマーケティングイベントは除外ジョブから除外されます。  Dynamics 365でSENDマーケティングイベントを表示する場合は、Unifiで出力ジョブのフィルタ（手順5）を変更する必要があります。

Unifiには、所有者ユーザーと読み取り専用アナリストユーザーの2つの役割があります。 所有者ユーザーはジョブとスケジュールを変更できますが、読み取り専用のアナリストは変更できません。  特定の顧客インスタンスに対して所有者ユーザーを1人だけ指定できます。  お客様が所有者ユーザーとして割り当てられた個人を変更する必要がある場合は、adobe-support@unifisoftware.com [(mailto]:adobe-support@unifisoftware.com)に変更を加えます。

Unifiの設定、ジョブの詳細、セットアップ、監視については、以下のビデオを参照してください。

## Unifiジョブ

### Unifiジョブの概要

>[!VIDEO](https://video.tv.adobe.com/v/27392)

このビデオでは、Adobe Campaign StandardとMicrosoft Dynamics 365の統合に必要な様々なUnifiジョブ（02:10分）を説明します。

### Unifiジョブの詳細：入力と出力

>[!VIDEO](https://video.tv.adobe.com/v/27396)

このビデオでは、Unifiでの入力ジョブと出力ジョブ（04:27分）を説明します。

### 運用と監視

>[!VIDEO](https://video.tv.adobe.com/v/27391)

このビデオでは、ワークフローとスケジュール（03:03分）を説明します。

その他の関連ヘルプ
* [Adobe Campaign Standardの使用 — Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Microsoft Dynamics 365をキャンペーン統合用に構成](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Microsoft Dynamics 365用Adobe IOの設定 —Campaign Standard統合](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Microsoft Dynamics 365統合機能ページ](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)