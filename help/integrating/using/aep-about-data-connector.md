---
title: Adobe Experience Platform Data Connector について
description: XDM スキーマを管理して、Campaign Standard データをAdobe Experience Platformで使用できるようにします。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform コネクタは非推奨（廃止予定）になりました。 廃止される機能は引き続き使用できますが、それ以上の機能強化やサポートは行われません。 詳しくは [&#x200B; このページを参照してください &#x200B;](../../rn/using/deprecated-features.md)

Adobe Experience Platform Data Connector は、XTK データ（Campaign に取り込まれたデータ）をAdobe Experience Platformの Experience Data Model （XDM）データにマッピングすることで、既存のお客様がAdobe Experience Platformでデータを使用できるようにします。

コネクタは **一方向性** で、Adobe Campaign StandardからAdobe Experience Platformにデータを送信します。 データはAdobe Experience PlatformからAdobe Campaign Standardには送信されません。

Adobe Experience Platform Data Connector は、Adobe Campaign Standardのカスタムリソースを理解し、顧客の全体的なデータスキーマがAdobe Experience Platform内でどのように配置されるべきかを理解している **データエンジニア** を対象としています。

次の節では、Campaign StandardとAdobe Experience Platform間でデータマッピングを実行するための主な手順を説明します。 これは、XDM スキーマとデータセットの作成から始まります。

![](assets/do-not-localize/how-to-video.png) [この機能について詳しくは、ビデオを参照してください。](#video)

>[!NOTE]
>Adobe Experience Platform Data Connector を設定し、データがAdobe Experience Platformに正常に取り込まれたら、データセットを有効にして、データがリアルタイム顧客プロファイルに含まれるようにする必要があります。
>
>これは、API またはAdobe Experience Platform インターフェイスを使用して実行できます。 詳しくは、該当するドキュメントを参照してください。
>
>* [&#x200B; リアルタイム顧客プロファイルのデータセットを有効にする &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [API を使用したリアルタイム顧客プロファイルおよび ID サービスのデータセットの設定 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## 主な概念 {#key-concepts}

* 標準マッピングは、Campaign Standardでデフォルトで提供されるフィールドでのみ使用できます。 すべてのカスタムフィールドとリソースを取り込む場合、各顧客は独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connector は、一定の間隔でプラットフォームを介してプロファイルデータをプッシュします&#x200B; 間隔の期間は 15 分です。 この値は、[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) を使用して変更できます。

* データエンジニアは、Campaign からAdobe Experience Platformへのマッピングを公開、変更および一時停止できます。

* 任意のターゲティングディメンションをマッピングできます。 単一のターゲティングディメンション内のすべてのフィールドに対して 1 つのマッピングを使用することをお勧めします。

* チャネルのオプトイン/オプトアウトを含むすべてのプロファイル更新は、バッチ更新の一部です。

* Adobe Campaign Standardまたは XDM スキーマの変更は、手動で再マッピングする必要があります&#x200B;

* トラッキングログおよび Broadlog データは、エクスペリエンスイベントとしてAdobe Experience Platformに自動的に取り込まれます。 この取り込みは、リアルタイムでAdobe Experience Platformにストリーミングされます。

* Experience Cloud ID サービス（ECID）は、エクスペリエンスイベントでデフォルトで送信されるデバイス識別子です。

  これは、訪問者に割り当てられた一意の永続的な ID で、Platform ID サービスで異なるExperience Cloud ソリューションで同じ訪問者とそのデータを識別するために使用できます。 詳しくは、[Experience Cloud ID サービスのヘルプ &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja) を参照してください。

  >[!NOTE]
  >
  >2 つ以上のプロファイルが同じデバイスを共有する場合、ECID は、統合 ID サービスのこれらの 2 つのプロファイルで同じになることにご注意ください。

## 制限事項 {#limitations}

* 初期状態のサブスクリプションイベントの転送はサポートされていません。 購読イベントを転送するには、対応する XDM とデータセットをAdobe Experience Platformで作成してから、これらのデータのカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスアクションと削除アクションの両方）については、お客様は [Privacy Core Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests) を介して、Campaign 用とAdobe Experience Platform用に 1 つの個別のリクエストを配置する必要があります。 詳しくは、Campaign の [&#x200B; プライバシーリクエストについて &#x200B;](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#righttoaccess) および [&#x200B; プライバシーリクエストの管理 &#x200B;](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) を参照してください。

* XDM フィールドごとに、Adobe Experience Platformで DULE のラベル付けを行う必要があります。 これは、DULE ラベルを適用するお客様の責任です。

* マーケティングアクションに関する制限は、Adobe Experience Platformで DULE ラベルが適用された後にのみ適用されます。 それ以前は、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* 15 分ごとに、バッチジョブが実行中で、最新のバッチ以降に変更されたレコードを特定します。 すべてのレコードが同じタイムスタンプで変更された場合、すべてのプロファイルの取り込みを管理するように見えるパフォーマンスボトルネックが発生する可能性があります

## チュートリアルビデオ {#video}

このビデオでは、Adobe Experience Platform Data Connector の概要を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Adobe Experience Platform コネクタに関するその他のビデオは [&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html) で参照できます。
