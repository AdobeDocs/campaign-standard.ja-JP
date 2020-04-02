---
title: Campaign StandardとMicrosoft Dynamics 365の操作
description: Campaign StandardとMicrosoft Dynamics 365の使い方
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
source-git-commit: 03009c47a66aa1a62c05f632e2a60141a98639d8

---


# Campaign StandardとMicrosoft Dynamics 365の操作

クロスチャネル通信でのCRMデータのアクティブ化：microsoft Dynamics 365の連絡先をAdobe Campaignに渡し、キャンペーンパフォーマンスデータ（送信、開く、クリックおよびバウンス）をAdobe CampaignからMicrosoft Dynamics 365に共有する方法を説明します。

>[!NOTE]
>
>Microsoft Dynamics 365/Adobe Campaign Standard統合は、 **Microsoft Dynamics 365 Salesアプリのみをサポートします** 。

## メリットと使用例

### 原則

Adobe CampaignとMicrosoft Dynamics 365の統合により、CRMシステムで使用可能なすべての連絡先データを同期し、関連するすべての連絡先データをキャンペーンアクティビティで使用できるようになります。

逆に、Adobe Campaign内のプロファイルがメッセージとやり取りする際に、これらのデータ(例：の送信、開く、クリック、バウンス)が自動的にMicrosoft Dynamics 365に流れ込み、連絡先レコードがマーケティングアクティビティと共に完全に保たれます。

統合の最新リリースでは、カスタムエンティティのサポートも追加され、Dynamics 365のカスタムエンティティをキャンペーン内の対応するカスタムエンティティと同期できます。

この統合は、次の3つの主な使用例をサポートするように設計されています。

1. マーケティングキャンペーンでターゲットを設定できるように、Dynamics 365の連絡先をキャンペーンに同期する
1. 電子メールマーケティングイベント（送信、開く、クリック、バウンス）をキャンペーンからDynamics 365に送信し、Dynamics 365インターフェイスの販売リポジトリに表示する
1. セグメント化とパーソナライゼーションに使用できるように、Dynamics 365からキャンペーンにカスタムエンティティを同期する

Dynamics 365Campaign Standard統合機能のビデオをご覧く [ださい](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)。

### 主なメリット

* 販売とマーケティングの間で一貫性のあるメッセージ

Adobe CampaignとMicrosoft Dynamics 365の統合により、両方のシステムから顧客インサイトと電子メールマーケティング履歴にアクセスでき、顧客に対するすべてのメッセージで同じ一貫性のあるメッセージを共有できます。

* 全表示と顧客データの見込み客全体

Adobe CampaignをDynamics 365と統合すると、CRMシステム内から各連絡先の電子メールマーケティング履歴を共有し、アクセスできます。

* 任意のチャネルでDynamics 365データをアクティブ化

連絡先データをAdobe Campaignに同期すると、任意のオンラインチャネルまたはオフラインキャンペーンで、モバイルプッシュ、アプリ内、電子メール、ダイレクトメールなどの通信を送信できます。 各連絡先の優先チャネルに関係なく、キャンペーンが対象です。

>[!CAUTION]
>
>連絡先の同期の場合、この統合ではDynamics 365を真の原因と見なします。  同期された連絡先属性に対する変更は、Dynamics 365で行う必要があります。キャンペーンでは行いません。  変更がキャンペーンで行われると、同期中に上書きされる可能性があります。
