---
title: Microsoft Dynamics 365とCampaign Standard統合の要求と設定
description: Microsoft Dynamics 365とCampaign Standard統合をリクエストおよび設定する方法
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4dd1ada05b6681a4e2f7676b177747bdfb0e9bff

---


# Campaign Standard統合でMicrosoft Dynamics 365を要求しています

この統合をプロビジョニングするには、次の手順に従う必要があります。

この統合では、サードパーティのプロバイダーであるUnifiが使用されています。  サポートの要請に関連して、Adobe Campaignのインスタンス情報をUnifiと共有する必要が生じる場合があります。

統合をリクエストおよび設定するには、以下のフローチャートとフローチャートの詳細に従ってください。

![](assets/provisioning-wf.png)

フローチャートの詳細（上記の手順に対応）:

1. この統合を実装するCampaign Standardの管理者アクセス権を持つ開始とMicrosoft Dynamics 365を、既にプロビジョニングしておく必要があります。

1. この記事、お読みください。お知らせと設定手順を確認してください。

1. アカウントリクエストをadobe-support@unifisoftware.comに送信します。アカウントをリクエストする際に、Unifiには次の情報が必要です。
   * ユーザーの名
   * ユーザーの姓
   * ユーザーの電子メール
   * 会社名
   * 地域（北米、EMEA、APAC）
   * 使用タイプ： 顧客タイプ（この統合で実稼働データを使用するお客様のユーザ）、またはパートナータイプ(キャンペーンのお客様を支援するために統合をテストするパートナーコンサルタント)または内部タイプ（ソリューションをより深く理解するために統合をテストするアドビの内部ユーザ）
   * Campaign Standardデータのステータス（データベースをクリーンにするか、既存のデータを統合するから）
   * キャンペーンテナントID(テナントIDを取得するには、キャンペーン統合の設定セクションの手順3を参照)
   * キャンペーンインスタンスURL
   Unifiの予想応答時間：米国の通常の営業時間（月～金）中1時間（午前9時～午後5時）。

1. Microsoft Dynamics 365およびCampaign Standardのプロビジョニング後の手順を完了します。
また、キャンペーンインスタンスでシングルサインオン機能フラグを有効にするには、チケットを（直接またはアドビの担当者を通じて）アドビカスタマーケアに送信します。 機能フラグを有効にするには、パートナーがアドビカスタマーケアに連絡する代わりに、アドビパートナーサンドボックスの担当者に連絡する必要があります。
統合に組み込む予定のキャンペーンの既存のデータがある場合は、「既存のキャンペーンデータ」の手順に従い、アドビのテクニカルコンタクトに詳細に相談してから、操作を続行します。

1. Unifiでの初期オンボーディング手順を完了するには、Unifiに移動し、オンボーディング画面をクリックし、Dynamics 365とCampaign Standardアカウントの資格情報を入力し、完了時にUnifiに通知します。

1. Unifiは、顧客に対し、希望するオプトアウト設定とオプトアウト属性のマッピングを求めます。

1. 選択したオプトアウト設定とオプトアウト属性のマッピングが表示されます。
Unifiの予想応答時間：1営業日（月～金、祝日を除く）

1. Unifiの設定には、OOTBマッピング、フィルター、ジョブなどの確認が含まれます。 必要に応じて、変更を加えます。  詳しくは、Unifiユーザガイドを参照してください。
この手順では、Unifiスケジュールの実行頻度を設定します
* Unifiのスケジュール画面でスケジュールの実行頻度を設定します。ただし、「入力」および「出力」スケジュールの場合は、スケジュールの頻度を設定する前に、手動で1回実行します
* 次のスケジュールの頻度を推奨します。入力（15分）、出力（15分）、削除（1日1回）、オプトアウト（1日1回）

**Unifiを設定する際は、Unifiまたはアドビのコンサルティング（アドビのアカウントチームにお問い合わせください）を利用することをお勧めします。**

Adobe Campaign StandardとMicrosoft Dynamics 365の統合を有効にするには、このドキュメントで説明するように、サードパーティプロバイダーのUnifiを使用してユーザーアカウントを作成する必要があります。   Unifiシステムのエンドユーザーは、Unifiシステム内の顧客が開始したデータ要求に関する問い合わせについて、Unifiシステムに問い合わせる必要があります。

## この統合の設定

この統合には、次の3つのシステムをプロビジョニングし、設定する必要があります。Adobe Campaign Standard、Microsoft Dynamics 365 for Sales、Unifi。 設定の記事は以下にリンクされています。

>[!CAUTION]
>
>各システムに対して、これらの手順は管理者が実行する必要があります。
>
>次の記事の手順に従って、権限の割り当てや管理者アクセスを含む統合/登録を作成します。  これらの手順を実行する前に、確実に会社ポリシーに従い、慎重に実行する必要があります。

ADOBE CAMPAIGNでは、APIアクセスを設定し、Unifi用の新しい統合を設定する必要があります。 これを達成するには、この記事を参 [照してください](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

MICROSOFT DYNAMICS 365では、新しいアプリの登録を作成し、アプリのユーザーが統合を使用できるようにする必要があります。  この統合用にMicrosoft Dynamics 365を設定するには、この記事を参照し [てください](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

UNIFIでは、統合を設定し、マッピングを設定するか、カスタム属性を追加する必要があります。 この統合用のUnifiを設定するには、この記事を参照 [してください](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)。

## サポートの要請

問題が発生した場合は、Unifiカスタマーサポートにお問い合わせください。 [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net)。

Unifiの予想応答時間：米国の通常の営業時間（月曜～金曜の午前9時～午後5時、祝日を除く）中に4時間。

>[!CAUTION]
>
>サポートの要請に関連して、Adobe Campaignのインスタンス情報をUnifiと共有する必要がある場合があります。