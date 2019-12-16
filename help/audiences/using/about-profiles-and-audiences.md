---
title: プロファイルとオーディエンスについて
description: 「Adobe Campaign内のプロファイルとオーディエンスの管理について説明します。ターゲット設定された訪問者の定義、オーディエンスの選択、受信者のフィルター、データの収集、プロファイルの更新を行います。」
page-status-flag: never-activated
uuid: f4cb6c38-c8d1-44ec-93f0-d0f5f30a3d9a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
discoiquuid: fb436b17-1fc3-4fc3-94b9-f09f8aaf9699
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# プロファイルとオーディエンスについて{#about-profiles-and-audiences}

キャンペーンまたはメッセージを作成する場合、Campaignデータベース内の連絡先から選択するか、単純条件または高度な条件を使用して選択するか、オーディエンスを選択することで、配信のターゲットを指定できます。

Adobe Campaignは、リッチな顧客プロファイルをリアルタイムで作成し、顧客の好みが変化した場合に、より関連性の高いパーソナライズされたオファーを提供できます。 さらに、Adobe Campaignは、高度な分析、データ管理およびターゲット設定機能を統合してオーディエンスを構築します。

* プロファイルは、データベースに保存される個々の連絡先です。

   各プロファイルは、データベース内の1つのエントリに対応し、ターゲット設定、修飾、個々の追跡を行うために必要な情報が格納されます。Adobe Campaignでは、オンラインチャネルとオフラインチャネルの両方からすべてのインタラクションを追跡し、それを単一のプロファイルに結合できます。

* オーディエンスは、特定の条件または条件のセットに基づいて作成されたプロファイルのリストです。

   ワークフローとクエリエディターを使用すると、マーケティングキャンペーンの情報、アクティビティ、およびマーケティング履歴に基づいて、マーケティングキャンペーンのターゲットを定めるオーディエンスを作成できます。 これにより、登録済みのプロファイル、サンプルまたはターゲットオーディエンスの作成を、無制限の数の条件でフィルターできます。

連絡先へのメッセージの送信を開始する前に、その連絡先の権限を持っていることを確認する必要があります。 そうでない場合は、電子メールがスパムとしてマークされ、プラットフォームの配信品質に影響を与える可能性があります。 正常なプロファイルデータベースを確実に構築するには、最初の手順としてこの権限を保護します。 Campaignを使用する場合は、サービスやランディングページを通じた簡単なオプトインおよびオプトアウトメカニズムを使用して [](../../audiences/using/creating-a-service.md)[](../../channels/using/getting-started-with-landing-pages.md) 、連絡先情報を更新し、データベースを拡張することをお勧めします。

メッセージに購読解除リンクを指定すると、必要に応じてプロファイルをブラックリストに記載できるので、プラットフォームの配信品質を向上できます。 ブラックリストの詳細については、「Campaignでのオ [プトインとオプトアウトについて」を参照してください](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

統合された顧客プロファイルとカスタマイズされたセグメントを使用して、すべてのチャネルにわたって顧客をより効果的に識別します。 顧客、興味、人口統計およびチャネルの環境設定を知っている場合は、気付かれるようにパーソナライズされたエクスペリエンスをより簡単に作成できます。

>[!CAUTION]
>
>Adobe Campaignの許容される使用ポリシ [ーを常に尊重する必要があります](https://www.adobe.com/legal/terms/aup.html)。

GDPR は欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。アドビは、Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、追加の機能を含め、特定のGDPRリクエストに対するData Controllerとしての準備を促進するため、この機会をデータプロセッサーとして取り上げます。

GDPRに準拠するた [めに](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) Adobe Campaignが提供するツールと機能の詳細については、このガイドを参照してください。

**関連トピック：**

* [オーディエンスの作成](../../audiences/using/creating-audiences.md)
* [プロファイルの作成](../../audiences/using/creating-profiles.md)
* [統合された顧客プロファイル](../../audiences/using/integrated-customer-profile.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

