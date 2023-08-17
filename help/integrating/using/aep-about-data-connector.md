---
title: Adobe Experience Platform Data Connector について
description: XDM スキーマを管理して、Campaign StandardデータをAdobe Experience Platformで使用できるようにします。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 5%

---

# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector は現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

Adobe Experience Platform Data Connector を使用すると、既存のお客様は、XTK データ（Campaign で取り込んだデータ）をAdobe Experience Platformの Experience Data Model(XDM) データにマッピングすることで、Adobe Experience Platformでデータを利用できるようになります。

コネクタは **単方向の** では、データをAdobe Campaign StandardからAdobe Experience Platformに送信します。 データはAdobe Experience PlatformからAdobe Campaign Standardに送信されません。

Adobe Experience Platform Data Connector は、 **データエンジニア** Adobe Campaign Standardのカスタムリソースを理解し、顧客の全体的なデータスキーマをAdobe Experience Platform内でどのように配置するかを理解できるユーザー。

次の節では、Campaign StandardとAdobe Experience Platformの間でデータマッピングを実行するための主な手順について説明します。 まず、XDM スキーマとデータセットの作成を行います。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

>[!NOTE]
>Adobe Experience Platform Data Connector を設定し、データがAdobe Experience Platformに正常に取り込まれたら、データがリアルタイム顧客プロファイルに含まれるようにデータセットを有効にする必要があります。
>
>これは、API またはAdobe Experience Platformインターフェイスを通じて実行できます。 詳しくは、該当するドキュメントを参照してください。
>
>* [リアルタイム顧客プロファイルのデータセットの有効化](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [API を使用したリアルタイム顧客プロファイルおよび ID サービスのデータセットの設定](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## 主要概念 {#key-concepts}

* 初期設定のマッピングは、デフォルトで「Campaign Standard」で指定されているフィールドでのみ使用できます。 すべてのカスタムフィールドとリソースを取り込む場合、各顧客は独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connector は、一定の間隔でプラットフォームを通じてプロファイルデータをプッシュしま&#x200B;す。 期間は 15 分です。 この値は [Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* データエンジニアは、Campaign からAdobe Experience Platformへのマッピングをパブリッシュ、変更および一時停止できます。

* 任意のターゲティングディメンションをマッピングできます。 単一のターゲティングディメンションでは、すべてのフィールドに対して 1 つのマッピングを使用することをお勧めします。

* チャネルのオプトイン/オプトアウトを含むすべてのプロファイル更新は、一括更新の一部です。

* Adobe Campaign Standardまたは XDM スキーマの変更は、手動で再マッピングする必要がありま&#x200B;す。

* トラッキングログおよび Broadlog データは、Experience Events としてAdobe Experience Platformに自動的に取り込まれます。 この取り込みは、Adobe Experience Platformにリアルタイムでストリーミングされます。

* Experience CloudID サービス (ECID) はデバイス識別子で、デフォルトで Experience Events と共に送信されます。

  これは訪問者に割り当てられる一意の永続的 ID で、Platform ID サービスで、異なるExperience Cloudソリューションで同じ訪問者とそのデータを識別するために使用できます。 詳しくは、 [Experience CloudID サービスヘルプ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja).

  >[!NOTE]
  >
  >2 つ以上のプロファイルが同じデバイスを共有している場合、ECID は統合 ID サービスのこれら 2 つのプロファイルで同じになることに注意してください。

## 制限事項 {#limitations}

* 既製のサブスクリプションイベントの転送はサポートされていません。 サブスクリプションイベントを転送するには、Adobe Experience Platformで対応する XDM とデータセットを作成し、それらのデータのカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスアクションと削除アクションの両方）に関して、顧客は [Privacy Core Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests):1 つはキャンペーン用、もう 1 つはAdobe Experience Platform用です。 詳しくは、 [プライバシーリクエストについて](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#righttoaccess) および [プライバシーリクエストの管理](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) Campaign 内。

* XDM フィールドごとに、DULE のラベル付けをAdobe Experience Platformでおこなう必要があります。 これは、DULE ラベルを適用するお客様の責任です。

* マーケティングアクションの制限は、Adobe Experience Platformでデータラベルが適用された後にのみ適用されます。 それ以前は、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* 15 分ごとにバッチジョブが実行され、最新のバッチ以降に変更されたレコードが識別されます。 すべてのレコードが同じタイムスタンプで変更される場合、すべてのプロファイルの取り込みを管理するパフォーマンスのボトルネックが表示される可能性があります

## チュートリアルビデオ {#video}

このビデオでは、Adobe Experience Platform Data Connector の概要を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Adobe Experience Platform Data Connector に関するその他のビデオを利用できます [ここ](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
