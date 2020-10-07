---
title: Microsoft Dynamics 365 統合の概要
description: Microsoft Dynamics 365統合の使用を開始する方法を説明します
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 10%

---


# Microsoft Dynamics 365 統合の概要

チャネル間の通信に関するCRMデータをアクティブにします。Microsoft Dynamics 365の連絡先をAdobe Campaignに渡し、キャンペーンパフォーマンスデータ（送信、開く、クリック、およびバウンス）をAdobe CampaignからMicrosoft Dynamics 365に共有する方法を説明します。

この節では、サポートされ [るバージョンを示します](#support-software-versions)。

>[!CAUTION]
>
>この機能は、製品の一部として初期状態では使用できません。実装するには、アドビのコンサルティングサービス部門に依頼する必要があります。詳しくは、アドビ担当者にお問い合わせください。

## 原則

Adobe CampaignとMicrosoft Dynamics 365の統合により、CRMシステム内の使用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティで使用できるようになります。

逆に、Adobe Campaign内のプロファイルがメッセージとやり取りする場合、そのデータ(例：送信、開く、クリック、バウンス)が自動的にMicrosoft Dynamics 365に流れ込み、マーケティングアクティビティとの連絡記録も完全に保ちます。

この統合は、カスタムエンティティもサポートし、Dynamics 365の [カスタムエンティティ](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) をキャンペーン内の対応するカスタムエンティティと同期できます。

この統合は、主に次の4つの使用例をサポートするように設計されています。

1. Dynamics 365からキャンペーンに連絡先を同期して、マーケティングキャンペーンでターゲット設定できるようにします
1. Dynamics 365のカスタムエンティティをキャンペーンに同期して、セグメント化とパーソナライゼーションに使用できるようにします
1. キャンペーンからDynamics 365に電子メールマーケティングイベント（送信、開く、クリック、バウンス）を送信し、Dynamics 365インターフェイスの販売リポジトリに表示します
1. Dynamics 365とACS間でオプトアウト（電子メール送信しないなど）ステータスを同期して、顧客のプライバシー設定を維持します。

## 主なメリット

* 販売とマーケティングの間で一貫したメッセージが行われる

Adobe CampaignとMicrosoft Dynamics 365の統合により、顧客のインサイトと電子メールのマーケティング履歴に両方のシステムからアクセスでき、顧客に対するすべてのメッセージで同じ一貫性のあるメッセージを共有できます。

* すべての見込み客と顧客データの全体的な表示

Adobe CampaignをDynamics 365と統合することで、CRMシステム内から各連絡先の電子メールマーケティング履歴を共有し、アクセスすることができます。

* 任意のチャネル上のDynamics 365データをアクティブにする

連絡先データがAdobe Campaignに同期されている場合、通信は、任意のオンラインまたはオフラインチャネルで、モバイルプッシュ、アプリ内、電子メール、ダイレクトメールなどのキャンペーンと共に送信できます。 各連絡先の好みのチャネルに関係なく、キャンペーンが対象とします。

>[!CAUTION]
>
>連絡先エンティティとカスタムエンティティの同期の場合、この統合ではDynamics 365を真の原因と見なします。  同期された属性に対する変更は、キャンペーンではなくDynamics 365で行う必要があります。  キャンペーンで変更を行うと、同期中に上書きされる場合があります。

## サポートソフトウェアバージョン {#support-software-versions}

この統合には、次のソフトウェアバージョンが必要です。

* Microsoft Dynamics 365 for Sales Onlineのみ、最新バージョン

* Adobe Campaign Standard最新版
