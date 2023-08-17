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
source-wordcount: '842'
ht-degree: 14%

---

# Microsoft Dynamics 365 統合の概要

クロスチャネル通信で CRM データをアクティブ化します。Microsoft Dynamics 365 から Adobe Campaign に連絡先を渡し、キャンペーンパフォーマンスデータ（送信、開封、クリックおよびバウンス）を Adobe Campaign に戻り Microsoft Dynamics 365 に共有する方法を学びます。

この統合には、次のソフトウェアバージョンが必要です。

* Microsoft Dynamics 365 for Sales Online のみ、最新バージョン

* Adobe Campaign Standard、最新バージョン

>[!CAUTION]
>
>この機能は、製品の一部として初期状態では使用できません。実装するには、アドビのコンサルティングサービス部門に依頼する必要があります。詳しくは、アドビ担当者にお問い合わせください。
>

## 原則

Adobe Campaign StandardとMicrosoft Dynamics 365 の統合により、CRM システムで使用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティで使用できます。

反対に、Adobe Campaign Standard内のプロファイルがメッセージとやり取りする際に、それらのデータ（例：送信、開封、クリック、バウンス）はMicrosoft Dynamics 365 に自動的に送られ、マーケティング活動と共に連絡先記録も完全に維持されます。

この統合では、の有効化もサポートしています。 [カスタムエンティティ](../../integrating/using/d365-acs-self-service-app-settings.md) 対応するに同期される Dynamics 365 内 **カスタムリソース** Campaign 内。

この統合は、次の 4 つの主な使用例をサポートするように設計されています。

1. Dynamics 365 から Campaign への連絡先の同期で、マーケティングキャンペーンのターゲットに
1. Dynamics 365 から Campaign へのカスタムエンティティの同期（セグメント化とパーソナライゼーションに使用可能）
1. Campaign から Dynamics 365 に電子メールマーケティングイベント（送信、開封、クリック、バウンス）を送信し、Dynamics 365 インターフェイスの販売リポジトリに表示します
1. Dynamics 365 と Campaign 間でオプトアウト（E メール送信なしなど）ステータスを同期して、顧客のプライバシー設定を維持する。

主なメリットは次のとおりです。

* セールスとマーケティングの間で一貫したメッセージを送信：Adobe Campaign Standardと Dynamics 365 の統合により、顧客インサイトと電子メールマーケティング履歴に両方のシステムからアクセスでき、顧客に対するすべてのメッセージで一貫したメッセージを共有できます。

* すべての見込み客と顧客データの全体像：Adobe Campaign Standardと Dynamics 365 を統合すると、CRM システム内から各連絡先の電子メールマーケティング履歴を共有し、アクセスできます。

* 任意のチャネルで Dynamics 365 データを有効化：連絡先データをAdobe Campaignに同期すると、モバイルプッシュ、アプリ内、電子メール、ダイレクトメールなど、Campaign を使用した任意のオンラインまたはオフラインチャネルで通信できます。 各連絡先の優先チャネルに関係なく、キャンペーン「対象」になりました。

>[!CAUTION]
>
>この統合では、Dynamics 365 を連絡先とカスタムエンティティの同期の真実のソースと見なします。  同期済み属性に対する変更は、Adobe Campaign Standardではなく、Dynamics 365 で行う必要があります。  Campaign で変更を加えると、同期中に上書きされる可能性があります。
>

## Microsoft Dynamics 365 統合を実装するための主な手順{#request-and-implement-this-integration}

この統合をプロビジョニングするには、次の手順に従う必要があります。

以下のフローチャートとフローチャートの詳細に従って、統合をリクエストおよび設定してください。

![](assets/provisioning-wf.png)

フローチャートの詳細（上記のステップにマップ）:

* **手順 1** - Microsoft Dynamics 365 for Sales およびAdobe Campaign Standardのライセンスを既に取得済み、または調達中であることを前提としています。
* **手順 2**  — 標準の統合機能は、すべてのお客様が無料で利用できます。ただし、要件に応じて、追加のコストがかかる場合があります。 詳細情報： [ベストプラクティスと制限事項](../../integrating/using/d365-acs-notices-and-recommendations.md). 統合を利用するには、元の SO に統合が含まれていない場合は、新しい販売注文 (SO) にサインインする必要があります。
* **手順 3** - Dynamics 365 と Campaign の統合前の手順の完了。 詳しくは、 [この統合を設定](#configure-this-integration).
* **手順 4** -Adobeのオンボーディングチームが統合アプリケーションユーザーインターフェイス (UI) にアクセスできるようになります。
* **手順 5**  — データマッピング、置き換え、フィルターなどを設定できます。 統合アプリケーションの UI 内から統合をテストします。

  >[!IMPORTANT]
  >
  > 双方向または Campaign から Dynamics 365 へのオプトアウト設定が必要な場合は、Adobeにテクニカルコンタクトにリクエストして、オプトアウトワークフローを Campaign インスタンスに設定する必要があります。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)

### この統合を設定 {#configure-this-integration}

この統合には、次の 3 つのシステムをプロビジョニングして設定する必要があります。

* **Adobe Campaign Standard**:API アクセスを設定し、統合ツール用に新しい統合を設定する必要があります。 これを実現するには、 [この記事](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**：新しいアプリ登録を作成し、アプリケーションユーザーが統合を使用できるようにする必要があります。  この統合用にMicrosoft Dynamics 365 を設定するには、 [この記事](../../integrating/using/d365-acs-configure-d365.md).
* **Adobe Campaign StandardとMicrosoft Dynamics 365 セルフサービスアプリの統合**: [この記事](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>各システムに対して、次の手順を **administrator**.
>
>このドキュメントの手順では、権限の割り当てや管理者アクセスに関連する統合／登録の作成手順を説明します。お客様の責任として、事前に会社のポリシーに従って手順を確認し、慎重に実行する必要があります。
>

### サポートをリクエスト

サポートチケットは、カスタマーケアでAdobeでログに記録できます。

統合データフローに関する問題が発生した場合は、必ず次の情報を含めてください。

* **プロセス所有者**：エンジニアリングアーキテクト
* **ES Process ID**：オンボーディングプロセス中に提供されます。
* **プロセスタイトル**: Microsoft Dynamics 365 / Adobe Campaign Standard統合
* **問題の説明**：問題の説明

現在、統合サポートの対象は 24 時間 365 日（月～金）です。Adobeの休日と休憩期間を除きます。
