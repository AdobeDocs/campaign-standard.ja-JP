---
title: Microsoft Dynamics 365 統合の概要
description: Microsoft Dynamics 365統合の使用を開始する方法を説明します
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 5%

---


# Microsoft Dynamics 365 統合の概要

チャネル間の通信に関するCRMデータをアクティブにします。Microsoft Dynamics 365の連絡先をAdobe Campaignに渡し、キャンペーンパフォーマンスデータ（送信、開く、クリック、およびバウンス）をAdobe CampaignからMicrosoft Dynamics 365に共有する方法を説明します。

この統合には、次のソフトウェアバージョンが必要です。

* Microsoft Dynamics 365 for Sales Onlineのみ、最新バージョン

* Adobe Campaign Standard最新版

>[!CAUTION]
>
>この機能は、製品の一部として初期状態では使用できません。実装するには、アドビのコンサルティングサービス部門に依頼する必要があります。詳しくは、アドビ担当者にお問い合わせください。


## 原則

Microsoft Dynamics 365とのAdobe Campaign Standardの統合により、CRMシステム内の使用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティで使用できるようになりました。

逆に、Adobe Campaign Standardのプロファイルがメッセージとやり取りすると、そのデータ(例：送信、開く、クリック、バウンス)が自動的にMicrosoft Dynamics 365に流れ込み、マーケティングアクティビティとの連絡記録も完全に保ちます。

また、Dynamics 365の[カスタムエンティティ](../../integrating/using/d365-acs-self-service-app-settings.md)を、キャンペーン内の対応する&#x200B;**カスタムリソース**&#x200B;に同期できるようにすることもサポートします。

この統合は、主に次の4つの使用例をサポートするように設計されています。

1. Dynamics 365からキャンペーンに連絡先を同期して、マーケティングキャンペーンでターゲット設定できるようにします
1. Dynamics 365のカスタムエンティティをキャンペーンに同期して、セグメント化とパーソナライゼーションに使用できるようにします
1. キャンペーンからDynamics 365に電子メールマーケティングイベント（送信、開く、クリック、バウンス）を送信し、Dynamics 365インターフェイスの販売リポジトリに表示します
1. Dynamics 365とキャンペーンの間でオプトアウト（電子メール送信しないなど）ステータスを同期して、ユーザーのプライバシー設定を維持します。

主なメリットは次のとおりです。

* 販売とマーケティングの間で一貫したメッセージが届く：Adobe Campaign StandardとDynamics 365の統合により、両方のシステムで顧客インサイトと電子メールマーケティング履歴にアクセスでき、顧客に対するすべてのメッセージで同じ一貫性のあるメッセージを共有できます。

* すべての見込み客および顧客データの全体的な表示:Adobe Campaign StandardとDynamics 365を統合することで、CRMシステム内から各連絡先の電子メールマーケティング履歴を共有し、アクセスすることができます。

* 任意のチャネルのDynamics 365データをアクティブにする：連絡先データがAdobe Campaignに同期されている場合、通信は、任意のオンラインまたはオフラインチャネルで、モバイルプッシュ、アプリ内、電子メール、ダイレクトメールなどのキャンペーンと共に送信できます。 キャンペーンは、各連絡先の好みのチャネルに関係なく「対象になっています。」

>[!CAUTION]
>
>この統合では、Dynamics 365を接触およびカスタムエンティティ同期の真のソースと見なします。  同期された属性に対する変更は、Adobe Campaign StandardではなくDynamics 365で行う必要があります。  キャンペーンで変更を行うと、同期中に上書きされる場合があります。


## Microsoft Dynamics 365統合を実装するための主な手順{#request-and-implement-this-integration}

この統合をプロビジョニングするには、次の手順に従う必要があります。

以下のフローチャートとフローチャートの詳細に従って、統合をリクエストおよび設定してください。

![](assets/provisioning-wf.png)

フローチャートの詳細（上記の手順に対応）:

* **手順1** - Microsoft Dynamics 365 for Salesおよびfor Servaceのライセンスを既にお持ちか、または購入中であることを前提としています。
* **ステップ2**  — 標準的な統合機能は、すべてのお客様が無料で利用できます。ただし、要件に応じて追加費用がかかる場合があります。[ベストプラクティスと制限](../../integrating/using/d365-acs-notices-and-recommendations.md)の詳細を参照してください。 統合が元のSOに含まれていない場合、統合を利用するには、新しい販売注文(SO)に署名する必要があります。
* **手順3**  - Dynamics 365とキャンペーンの統合前の手順を完了します。「[この統合の設定](#configure-this-integration)」を参照してください。
* **手順4** -Adobeオンボーディングチームが、統合アプリケーションユーザーインターフェイス(UI)へのアクセスを提供します。
* **手順5**  — データのマッピング、置き換え、フィルターなどを設定できます。統合アプリケーションのUI内で統合をテストします。

   >[!IMPORTANT]
   >
   > 双方向またはDynamics 365オプトアウト構成へのキャンペーンが必要な場合は、Adobeのテクニカルコンタクトに、オプトアウトワークフローをキャンペーンインスタンスにセットアップするように依頼する必要があります。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### この統合を構成{#configure-this-integration}

この統合には、次の3つのシステムをプロビジョニングして設定する必要があります。

* **Adobe Campaign Standard**:apiアクセスを設定し、統合ツールの新しい統合を設定する必要があります。これを達成するには、[この記事](../../integrating/using/d365-acs-configure-adobe-io.md)を参照してください。
* **Microsoft Dynamics 365**:新しいアプリの登録を作成し、アプリのユーザーが統合を使用できるようにする必要があります。この統合用にMicrosoft Dynamics 365を構成するには、[この記事](../../integrating/using/d365-acs-configure-d365.md)を参照してください。
* **Microsoft Dynamics 365 Self-Service AppとのAdobe Campaign Standard統合**:この記事の手順に従う必要があ [ります](../../integrating/using/d365-acs-self-service-app-control-access.md)。

>[!IMPORTANT]
>
>各システムに対して、これらの手順は&#x200B;**管理者**&#x200B;が実行する必要があります。
>
>このドキュメントの手順に従って、権限の割り当てや管理者アクセスを含む統合/登録を作成します。  これらの手順を実行する前に会社ポリシーに従い、慎重に実行する必要があります。


### サポートの要請

サポートチケットは、Adobeカスタマーケアによって記録できます。

統合データフローに関する問題の場合は、問題の説明の一部にレポートスイートを含め、次の情報を必ず含めてください。

* **Process Owner**:エンジニアリングアーキテクト
* **ES Process ID**:オンボーディングプロセス中に提供されます。
* **プロセスタイトル**:Microsoft Dynamics 365 /Adobe Campaign Standard統合
* **問題の説明**:問題の説明

現在、統合サポートは24時間365日体制です(月～金、Adobeの休日および休憩時間を除く)。
