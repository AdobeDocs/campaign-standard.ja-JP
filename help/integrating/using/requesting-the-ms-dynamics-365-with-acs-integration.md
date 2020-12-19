---
solution: Campaign Standard
product: campaign
title: Microsoft Dynamics 365 統合のリクエストと設定
description: Microsoft Dynamics 365とCampaign Standard統合を要求し、構成する方法を説明します
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# Microsoft Dynamics 365 統合のリクエストと設定

この統合をプロビジョニングするには、次の手順に従う必要があります。

以下のフローチャートとフローチャートの詳細に従って、統合をリクエストおよび設定してください。

![](assets/provisioning-wf.png)

フローチャートの詳細（上記の手順に対応）:

* **手順1** - Microsoft Dynamics 365 for SalesおよびforAdobe Campaign Standardのライセンスを既にお持ちか、または購入中であることを前提としています。

* **ステップ2**  — 標準的な統合機能は、すべてのお客様が無料で利用できます。ただし、要件に応じて追加費用がかかる場合があります( [統合ガードレールと境界を参照](../../integrating/using/ms-dynamics-365-integration-guardrails.md))。統合を活用するには、新しい販売注文に署名する必要があります。

* **手順3**  - Dynamics 365とキャンペーンの統合前の手順を完了します。「[この統合の設定](#configure-this-integration)」を参照してください。

* **手順4 ～ 7**  -Adobeのオンボーディングチームは、オンボーディングプロセスを通じてお客様と連携します。

## この統合を構成{#configure-this-integration}

この統合には、次の3つのシステムをプロビジョニングして設定する必要があります。Adobe Campaign Standard、Microsoft Dynamics 365 for Salesおよび統合ツール。 設定の記事は以下にリンクされています。

>[!CAUTION]
>
>各システムに対して、これらの手順は管理者が実行する必要があります。
>
>次の記事の手順に従って、権限の割り当てや管理者アクセスを含む統合/登録を作成します。  これらの手順を実行する前に会社ポリシーに従い、慎重に実行する必要があります。

Adobe Campaignでは、APIアクセスを設定し、統合ツールの新しい統合を設定する必要があります。 これを達成するには、[この記事](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)を参照してください。

MICROSOFT DYNAMICS 365では、新しいアプリ登録を作成し、アプリケーションユーザーが統合を使用できるようにする必要があります。  この統合用にMicrosoft Dynamics 365を構成するには、[この記事](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)を参照してください。

入力、出力、オプトアウトの各データフローの設定を行うには、Adobeのオンボーディングチームと協力する必要があります。


## サポートの要請

サポートチケットは、通常どおり、Adobeカスタムケアで記録できます。カスタマーケアは、必要に応じてサポート担当者を派遣します。

統合データフローに関する問題の場合は、問題の説明の一部にレポートスイートを含め、次の情報を必ず含めてください。

* **Process Owner**:エンジニアリングアーキテクト

* **ES Process ID**:オンボーディングプロセス中に提供されます。

* **プロセスタイトル**:Dynamics 365 /Adobe Campaign Standard統合

* **問題の説明**:問題の説明

現在、統合サポートは24時間365日体制です(月～金、Adobeの休日および休憩時間を除く)。