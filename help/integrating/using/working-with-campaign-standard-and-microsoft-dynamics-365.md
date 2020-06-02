---
title: Microsoft Dynamics 365統合の概要
description: Microsoft Dynamics 365統合の使用を開始する方法を説明します
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21135f27fd1d8297edd3dd067446d09c39de9f4f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---


# Microsoft Dynamics 365統合の概要

>[!IMPORTANT]
>
>この統合は現在使用できません。 新しいコネクターが開発中で、今後利用できる予定です。 詳しくは、アドビのセールス担当者にお問い合わせください。

チャネル間の通信に関するCRMデータをアクティブにします。 Microsoft Dynamics 365の連絡先をAdobe Campaignに渡し、キャンペーンパフォーマンスデータ（送信、開く、クリック、およびバウンス）をAdobe CampaignからMicrosoft Dynamics 365に共有する方法を説明します。

>[!NOTE]
>
>Microsoft Dynamics 365 /Adobe Campaign標準統合は、 **Microsoft Dynamics 365 Salesアプリの** みをサポートします。

## 原則

Adobe CampaignとMicrosoft Dynamics 365の統合により、CRMシステムで使用可能なすべての連絡先データを同期でき、関連するすべての連絡先データをキャンペーンアクティビティで使用できるようになります。

逆に、Adobe Campaign内のプロファイルがメッセージとやり取りする場合、そのデータ(例： 送信、開く、クリック、バウンス)が自動的にMicrosoft Dynamics 365に流れ込み、連絡先の記録がマーケティングアクティビティと共に完全に保たれます。

また、最新リリースの統合では、カスタムエンティティのサポートも追加され、Dynamics 365のカスタムエンティティをキャンペーン内の対応するカスタムエンティティに同期できます。

この統合は、主に次の3つの使用例をサポートするように設計されています。

1. Dynamics 365の連絡先をキャンペーンに同期して、マーケティングキャンペーンでターゲット設定できるようにします
1. キャンペーンからDynamics 365に電子メールマーケティングイベント（送信、開く、クリック、バウンス）を送信し、Dynamics 365インターフェイスの販売リポジトリに表示します
1. Dynamics 365のカスタムエンティティをキャンペーンに同期して、セグメント化とパーソナライゼーションに使用できるようにします

## 主なメリット

* 販売とマーケティングの間で一貫したメッセージが行われる

Adobe CampaignとMicrosoft Dynamics 365の統合により、顧客のインサイトと電子メールのマーケティング履歴に両方のシステムからアクセスでき、顧客に対するすべてのメッセージで同じ一貫性のあるメッセージを共有できます。

* すべての見込み客と顧客データの全体的な表示

Adobe CampaignをDynamics 365と統合すると、CRMシステム内から各連絡先の電子メールマーケティング履歴を共有し、アクセスできます。

* 任意のチャネル上のDynamics 365データをアクティブにする

連絡先データがAdobe Campaignに同期されている場合、通信は、任意のオンラインまたはオフラインチャネルで、モバイルプッシュ、アプリ内、電子メール、ダイレクトメールなどのキャンペーンと共に送信できます。 各連絡先の希望チャネルに関係なく、キャンペーンが対象としています。

>[!CAUTION]
>
>連絡先の同期の場合、この統合ではDynamics 365を真のソースと見なします。  同期された連絡先属性に対する変更は、キャンペーンではなくDynamics 365で行う必要があります。  キャンペーンで変更を行うと、同期中に上書きされる場合があります。
