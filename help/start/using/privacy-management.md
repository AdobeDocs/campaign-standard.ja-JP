---
title: Adobe Campaign Standard のプライバシー管理
description: プライバシーを管理する Adobe Campaign Standard の機能について詳しく説明します。
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Privacy
role: User
level: Intermediate
exl-id: 84cf8f6e-9ba0-4cd5-80e2-a61cefa31e0a
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 100%

---

# プライバシー管理 {#privacy-management}

Adobe Campaign には、[プライバシー規制](#privacy-management-regulations)（GDPR、CCPA、PDPA、LGPD など）を遵守するのに役立つ各種のツールが用意されています。

GDPR などのプライバシー規制に対する対応するために Adobe Campaign で提供されている 5 つの主な機能を次に示します。

![](assets/privacy-gdpr-use-cases.png)

* **アクセスする権利**

* **削除する権利**

詳しくは、[アクセスする権利と忘れられる権利](#right-access-forgotten)を参照してください。

* **同意管理**

* **データ保持**

* **権限管理**

詳しくは、[同意、リテンション、役割](#consent-retention-roles)を参照してください。

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## プライバシー管理に関する規制 {#privacy-management-regulations}

Adobe Campaign の機能により、次の規制を遵守できるようになります。

* **GDPR**（[一般データ保護規則](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)）は欧州連合（EU）で施行されているプライバシー保護法律で、EU 諸国のデータ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR に関する一般的な情報は、次のリンクから確認してください。

   * https://www.adobe.com/jp/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/jp/marketing-cloud/campaign/general-data-protection-regulation.html

* **CCPA**（[カリフォルニア州消費者プライバシー法](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)）は、カリフォルニア州民に個人情報に関する新しい権利を提供し、カリフォルニア州でビジネスをおこなう特定の事業者に対してデータ保護の責任を課します。
* **PDPA**（[Personal Data Protection Act、個人情報保護法](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)）は、タイの新しいプライバシー法で、データ保護要件を現代の状況に合わせて整合化することを目的としています。
* **LGPD**（[Lei Geral de Proteção de Dados、一般データ保護法](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)）は、2021 年前半から適用され、ブラジルで個人データを収集および処理するすべての会社に対して有効となります。

これらすべての規則は、前述の各地域または国（EU、米国カリフォルニア州、タイ、ブラジル）に居住するデータ主体のデータを保持する Adobe Campaign のお客様が対象となります。

>[!NOTE]
>
>個人データおよびデータを管理する様々なエンティティ（データ管理者、データ処理者、データ主体）について詳しくは、[個人データとペルソナ](../../start/using/privacy.md#personal-data)を参照してください。

## アクセス権と忘れられる権利 {#right-access-forgotten}

プライバシーの準備を容易にするために、Adobe Campaign では&#x200B;**アクセス**&#x200B;要求と&#x200B;**削除**&#x200B;要求の処理が可能になりました。

* **アクセスする権利**&#x200B;とは、データ主体がデータ管理者に、自分に関する個人データが処理されているかどうか、また処理されている場合はその場所と目的について確認できることを指します。データ管理者は、個人データのコピーを電子形式で無償提供する必要があります。

* データ消去としても知られている「**忘れられる権利**」（削除要求）は、データ主体がデータコントローラーに個人データを消去させ、データのさらなる拡散を中止させ、第三者にデータ処理を停止させることができる権利です。

**アクセス**&#x200B;要求と&#x200B;**削除**&#x200B;要求の作成方法、および Adobe Campaign によるリクエストの処理方法については、[実装手順](../../start/using/privacy-requests.md#about-privacy-requests)を参照してください。

Campaign Standard のプライバシー管理に関するチュートリアルについては、[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=ja#privacy)を参照してください。

>[!NOTE]
>
>個人データおよびデータを管理する様々なエンティティ（データ管理者、データ処理者、データ主体）について詳しくは、[個人データとペルソナ](../../start/using/privacy.md#personal-data)を参照してください。

## 同意、保持、役割 {#consent-retention-roles}

新しく導入された&#x200B;**アクセスする権利**&#x200B;と&#x200B;**忘れられる権利**&#x200B;の他にも、Adobe Campaign はプライバシーに必要な重要機能を各種用意しています。

* [同意管理](#consent-management)：環境設定管理用の購読機能
* [データ保持](#data-retention)：すべての標準ログテーブルのデータ保持期間。保持期間の追加はワークフローで設定可能
* [権限管理](#rights-management)：ネームド権限により管理されるデータアクセス

### 同意管理 {#consent-management}

同意とは、データ主体に関する個人データの処理についてデータ主体からの同意を得ることを指します。処理に関して必要な同意を得ることは、データ管理者の責務です。Adobe Campaign には、サービスに関連する同意を顧客が管理するための機能はありますが、アドビは同意自体についての責任を負いません。顧客は自社内の法務部門と連携して、同意のプロセスと手続きを自ら確立する必要があります。

同意に関する側面を管理する機能は、発売当初から Adobe Campaign の中核機能でした。購読管理プロセスにより、顧客はどの受信者がどの種類の購読をオプトインしているかをトラッキングできます。購読の種類には、ニュースレター、毎日または毎週のプロモーションなどのマーケティングプログラムがあります。

![](assets/privacy-consent-management.png)

同意管理について詳しくは、[購読について](../../audiences/using/about-subscriptions.md)および[ランディングページの使用を開始する](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

Adobe Campaign が提供する同意管理ツールに加えて、消費者が個人情報の販売をオプトアウトしたかどうかをトラッキングすることもできます。[この節](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)を参照してください。

### データ保持 {#data-retention}

Campaign の組み込みログテーブルには保持期間がプリセットされており、通常はデータ保存期間が 6 か月以内に制限されています。

組み込みテーブルのデフォルトの保持期間は以下のとおりです。リテンションは実装時にアドビの技術管理者が設定します。値は顧客の要件に基づくため、実装環境によって異なる場合があります。

* **統合されたトラッキング**：6 か月
* **配信ログ**：6 か月
* **トラッキングログ**：6 か月
* **イベント**：1 ヶ月
* **イベント処理の統計**：6 か月
* **アーカイブしたイベント**：6 か月
* **臨時の事業者**：7 日間
* **無視されたパイプラインイベント**：1 ヶ月
* **配信アラート**：1 ヶ月
* **書き出しの監査**：6 か月

削除の場合と同様、標準ワークフロー機能を使用して、任意のカスタムテーブルのリテンション期間を設定することができます。

リテンションの詳細について知りたい場合、またはカスタムテーブルの設定が必要な場合は、アドビのコンサルタントまたは技術管理者にお問い合わせください。

### 権限管理 {#rights-management}

Adobe Campaign では、事前作成された役割またはカスタムの役割を使用して、様々な Campaign オペレーターに割り当てられている権限を管理できます。

その利点の 1 つとして、各種類のデータについて社内のどのユーザーがアクセスできるかを管理できることが挙げられます。例えば、様々な地域を複数のマーケッターで担当している場合に、各マーケッターが自分の担当地域からのデータのみにアクセスできるようにすることが可能です。

同様に、ユーザーごとに各種の機能を設定することができます。例えば、配信の送信者を限定することができたり、データを変更またはエクスポートできるユーザーを制限してプライバシー管理の関連性を高めたりできます。

![](assets/privacy-user-management.png)

アクセス管理について詳しくは、[この節](../../administration/using/about-access-management.md)を参照してください。
