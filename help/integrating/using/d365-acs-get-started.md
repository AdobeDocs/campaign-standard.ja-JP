---
title: Microsoft Dynamics 365 統合の概要
description: Microsoft Dynamics 365 統合の概要
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 6%

---

# Microsoft Dynamics 365 統合の概要

クロスチャネル通信で CRM データをアクティブ化します。Microsoft Dynamics 365 からAdobe Campaignに連絡先を渡し、キャンペーンパフォーマンスデータ（送信、開封、クリックおよびバウンス）をAdobe Campaignに戻りMicrosoft Dynamics 365 に共有する方法を学びます。

この統合には、次のソフトウェアバージョンが必要です。

* Microsoft Dynamics 365 for Sales Online 最新バージョン

* Adobe Campaign Standard、最新版

>[!CAUTION]
>
>この機能は、製品の一部として初期状態では使用できません。実装するには、アドビのコンサルティングサービス部門に依頼する必要があります。詳しくは、アドビ担当者にお問い合わせください。
>

## 原則

Adobe Campaign StandardとMicrosoft Dynamics 365 の統合により、CRM システムで使用可能なすべての連絡先データの同期が可能になり、関連するすべての連絡先データをキャンペーンアクティビティで使用できるようになります。

逆に、Adobe Campaign Standard内のプロファイルがメッセージとやり取りする際、これらのデータ（送信、開封、クリック、バウンスなど）はMicrosoft Dynamics 365 に自動的に送られ、連絡先レコードがマーケティングアクティビティでも完全に保持されます。

この統合では、Dynamics 365 の [&#x200B; カスタムエンティティ &#x200B;](../../integrating/using/d365-acs-self-service-app-settings.md) を、Campaign の対応する **カスタムリソース** に同期することもサポートされています。

この統合は、次の 4 つの主なユースケースをサポートするように設計されています。

1. マーケティングキャンペーンでターゲット設定ができるように、Dynamics 365 から Campaign に連絡先を同期
1. セグメント化やパーソナライゼーションに使用できるように、Dynamics 365 から Campaign にカスタムエンティティを同期
1. Dynamics 365 インターフェイスの営業リポジトリに表示するためのメールマーケティングイベント（送信、開封、クリック、バウンス）を Campaign から Dynamics 365 に送信する
1. 顧客のプライバシー設定を維持するために、Dynamics 365 と Campaign の間でオプトアウト （メール拒否など）状態を同期しています。

主なメリットは次のとおりです。

* 営業とマーケティング間で一貫したメッセージを表示：Adobe Campaign Standardと Dynamics 365 の統合により、両方のシステムから顧客インサイトと電子メールマーケティング履歴にアクセスできるようになりました。また、お客様に対するすべてのメッセージで同じ一貫性のあるメッセージの共有もできます。

* すべての見込み客と顧客データの総合的なビュー：Adobe Campaign Standardを Dynamics 365 と統合すると、CRM システム内から各連絡先の電子メールマーケティング履歴を共有し、アクセスできます。

* 任意のチャネルで Dynamics 365 データをアクティブ化：連絡先データをAdobe Campaignに同期すると、モバイルプッシュ、アプリ内、メール、ダイレクトメールなど、Campaign を使用した任意のオンラインまたはオフラインチャネルでやり取りできます。 Campaign では、各連絡先の優先チャネルに関係なく、「対応しました」

>[!CAUTION]
>
>この統合では、Dynamics 365 を連絡先およびカスタムエンティティ同期の信頼できる情報源と見なします。  同期された属性に対する変更は、Adobe Campaign Standardではなく Dynamics 365 で行う必要があります。  Campaign で変更を加えると、同期中に最終的に上書きされる可能性があります。
>

## Microsoft Dynamics 365 統合を実装するための主な手順{#request-and-implement-this-integration}

この統合をプロビジョニングするには、次の手順に従う必要があります。

以下のフローチャートおよびフローチャートの詳細に従って、統合をリクエストし設定してください。

![](assets/provisioning-wf.png)

フローチャートの詳細（上記の手順に対応）:

* **手順 1** – 販売用およびAdobe Campaign Standard用のMicrosoft Dynamics 365 のライセンスを既に保有しているか、または調達中であることを前提としています。
* **手順 2** – 標準統合機能は、すべてのお客様に無料で提供されますが、要件に応じて追加コストが発生する可能性があります。 詳細情報 [&#x200B; ベストプラクティスと制限事項 &#x200B;](../../integrating/using/d365-acs-notices-and-recommendations.md)。 元の SO に含まれていない場合は、統合を活用するために新しい SO に署名する必要があります。
* **手順 3** - Dynamics 365 と Campaign の統合前手順を完了します。 [&#x200B; この統合の設定 &#x200B;](#configure-this-integration) を参照してください。
* **手順 4** – 統合のオンボーディングチームから、Adobeアプリケーションのユーザーインターフェイス（UI）にアクセスできるようになります。
* **手順 5** - データマッピング、置き換え、フィルターなどを設定できるようになります。 さらに、統合アプリケーションの UI 内から統合をテストします。

  >[!IMPORTANT]
  >
  > Dynamics 365 への双方向またはキャンペーンのオプトアウト設定が必要な場合、Campaign インスタンスにオプトアウトワークフローを設定するには、Adobeの技術担当者にリクエストを送信する必要があります。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### この統合の設定 {#configure-this-integration}

この統合用に 3 つのシステムをプロビジョニングし設定する必要があります。

* **Adobe Campaign Standard**: API アクセスを設定して、統合ツールの新しい統合を構成する必要があります。 これを行うには、[&#x200B; この記事 &#x200B;](../../integrating/using/d365-acs-configure-adobe-io.md) を参照してください。
* **Microsoft Dynamics 365**：新しいアプリ登録を作成し、アプリ ユーザーが統合を使用できるようにする必要があります。  この統合用にMicrosoft Dynamics 365 を設定するには、[&#x200B; この記事 &#x200B;](../../integrating/using/d365-acs-configure-d365.md) を参照してください。
* **Adobe Campaign StandardとMicrosoft Dynamics 365 セルフサービスアプリとの統合**: [&#x200B; この記事 &#x200B;](../../integrating/using/d365-acs-self-service-app-control-access.md) の手順に従う必要があります。

>[!IMPORTANT]
>
>システムごとに、**管理者** がこれらの手順を実行する必要があります。
>
>このドキュメントの手順では、権限の割り当てや管理者アクセスに関連する統合/登録の作成手順を説明します。  お客様の責任として、事前に会社のポリシーに従って手順を確認し、慎重に実行する必要があります。
>

### サポートをリクエスト

サポートチケットは、Adobeカスタマーケアに記録することができます。

統合データフローの問題については、必ず次の情報を含めてください。

* **プロセスオーナー**：エンジニアリングアーキテクト
* **ES プロセス ID**：オンボーディングプロセス中に提供されます
* **プロセスのタイトル**:Microsoft Dynamics 365/Adobe Campaign Standardの統合
* **問題の説明**：問題の説明

現在、統合サポートは 24 時間 365 日（月曜日から金曜日で利用可能。Adobeの休日と休憩時間は除く）です。
