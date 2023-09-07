---
title: Adobe Campaign Standard でのプライバシーと同意
description: この節では、Adobe Campaign Standard のプライバシー、個人データ、同意管理、およびこれらを扱うために利用できるツールの概要について説明します。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: User
level: Intermediate
exl-id: 0fc71c2f-f294-43f7-825c-73ab4d43fcf7
source-git-commit: 9533654ac4476b359da8cf00f9ef2015d9f8ccdf
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 96%

---

# プライバシーと同意{#privacy-and-consent}

## 一般的な推奨事項 {#general-recommendations}

Adobe Campaign は、個人情報や機密データを含む膨大な量のデータを収集および処理するための強力なツールです。そのため、プライバシー管理は慎重におこなう必要があります。

* 常に、個人情報を責任を持って倫理的に使用してください。

* 迷惑メール／プッシュ通知／SMS メッセージ（「スパム」）を送信しないでください。アドビでは、顧客の生涯価値およびロイヤルティを促進するうえで許可型マーケティングの原則を重視しています。したがって、未承諾メッセージの送信に Adobe Campaign を使用することを固く禁止しています。


### プライバシー規制 {#privacy-regulations}

プライバシーを正しく取り扱い、個人データを管理するには、事業をおこなう地域に適用される法律の範囲内で作業してください。次の規則が含まれます。
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)（ヨーロッパの一般データ保護規則）
* [DPA](https://www.gov.uk/data-protection)（英国での GDPR）
* [プライバシーと電子通信に関する欧州指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM 法](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)（商用メールのルールと要件を設定する米国の法律）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)（カリフォルニア州消費者プライバシー法）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)（タイ個人データ保護法）

>[!NOTE]
>
>GDPR、CCPA、PDPA が Adobe Campaign にどのように適用されるかについては、[このページ](../../start/using/privacy-management.md#privacy-management-regulations)を参照してください。

### Adobe Experience Cloud プライバシー {#experience-cloud-privacy}

Adobe Campaign は、Adobe Experience Cloud ソリューションの一部です。Campaign でのプライバシーの扱い方は、次のような Adobe Experience Cloud の一般原則に従います。

* **Adobe Experience Cloud を使用する際に収集される情報**

  Adobe Experience Cloud ソリューションを使用する会社は、収集して Adobe Experience Cloud アカウントに送信する情報を選択します。収集される情報のタイプの例としては、web 閲覧アクティビティ、IP アドレス、モバイルデバイスからの位置情報、キャンペーン成功率、購入品目、買い物かごに入れた品目などがあります。

  >[!NOTE]
  >
  >すべてのアドビ製品について、Campaign はアプリと web サイトのユーザーに関する情報を収集します。詳しくは、[アドビのプライバシーポリシー](https://www.adobe.com/jp/privacy/policy.html)を参照してください。

* **Adobe Experience Cloud を使用した情報収集の仕組み**

   * Adobe Experience Cloud ソリューションでは、情報を収集できるように、web ビーコン（タグやピクセルとも呼ばれます）などの Cookie および同様のテクノロジーを使用します。Cookie および Adobe Campaign を使用した追跡機能について詳しくは、[この節](#tracking-capabilities)を参照してください。
   * モバイルアプリで Adobe Experience Cloud テクノロジーを使用することもできます。Campaign を使用してモバイル配信を行う方法について詳しくは、[このページ](../../channels/using/mobile-guide.md)を参照してください。

* **Adobe Experience Cloud の使用に関するユーザーのプライバシー選択**

  アドビから、次の内容を説明するプライバシーポリシーをお客様に提供するように求められます。

   * Adobe Experience Cloud に関連するプライバシー方針
   * Adobe Experience Cloud に関連して、ユーザーが情報の収集や使用に関する環境設定をおこなう方法

  >[!NOTE]
  >
  >すべてのアドビ製品と同様に、Campaign のユーザーは、アプリや Web サイトを通じて収集した情報の共有をオプトアウトできます。詳しくは、[Adobe Experience Cloud の使用に関する FAQ](https://www.adobe.com/jp/privacy/experience-cloud-usage-info-faq.html) を参照してください。

Adobe Experience Cloud のプライバシーについて詳しくは、[このページ](https://www.adobe.com/jp/privacy/marketing-cloud.html)を参照してください。

## 個人データとペルソナ {#personal-data}

プライバシーを管理する場合、どのデータを誰がどのように扱うかを定義することが重要です。
* **個人データ**&#x200B;は、生存する個人を直接または間接的に識別できる情報です。
* **個人の機密データ**&#x200B;は、個人の人種、政治観、宗教的信念、犯罪歴、遺伝情報、健康データ、性的嗜好、生体認証情報、および労働組合の組合員に関する情報です。

[主な法律](#privacy-regulations)では、データを管理する様々なエンティティを以下のように定義しています。
* **データ管理者**&#x200B;は、個人データの収集、使用、共有の方法と目的を決定する権限を有する関係者です。
* **データ処理者**&#x200B;は、データ管理者の指示に従って個人データを収集、使用、または共有する個人または関係者です。
* **データ主体**&#x200B;は、個人データが収集、使用、共有され、その個人データを参照して直接または間接的に識別できる、生存する個人のことです。

したがって、個人データを収集し共有する会社はデータ管理者で、そのクライアントはデータ主体です。Adobe Campaign は、お客様の指示に従って個人データを処理する際に、データ処理者として機能します。[プライバシーリクエスト](#privacy-requests)を管理する場合など、データ主体との関係を処理するのはデータ管理者側の責任となるため注意が必要です。

オーディエンスを別のExperience Cloudに転送できる他のシステムソリューションと Campaign を統合する場合、 [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Managerまたは People コアサービス](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)、または他のソリューション ( [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)の場合は、個人データ保護に対して特別なケアを払う必要があります。

## データの取得 {#data-acquisition}

Adobe Campaign を使用すると、個人情報や機密情報などのデータを収集できます。したがって、受信者の同意を得てこれを監視することが重要になります。

* 受信者は常に通信の受信に同意するようにします。これをおこなうには、できるだけ早くオプトアウトリクエストを守り、二重のオプトインプロセスを通じて同意を確認します。詳しくは、[Campaign でのオプトインおよびオプトアウトの管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)および[ダブルオプトインプロセスの設定](../../channels/using/setting-up-a-double-opt-in-process.md)を参照してください。
* 不正なリストを読み込まず、トラップを使用して、クライアントファイルが不正に使用されていないことを確認してください。詳しくは、[トラップの使用](../../sending/using/using-traps.md)を参照してください。
* 同意と権限の管理を通じて、受信者の好みを追跡し、組織内の誰がどのデータにアクセスできるかを管理できます。詳しくは、[この節](#consent)を参照してください。
* 受信者からのプライバシーリクエストを円滑に処理して管理します。詳しくは、[この節](#privacy-requests)を参照してください。

## プライバシー管理 {#privacy-management}

プライバシー管理とは、プライバシー規制（GDPR、CCPA など）の遵守に役立つすべてのプロセスとツールを指します。プライバシー管理の概要については、[このページ](../../start/using/privacy-management.md#privacy-management-regulations)で確認してください。

Adobe Campaign では、プライバシー管理に関する様々な機能を提供しています。
* 同意の管理、データ保持、ユーザーの役割：[この節](#consent)を参照してください。
* プライバシーリクエスト（アクセスする権利と忘れられる権利）：[この節](#privacy-requests)を参照してください。
* 個人情報の販売のオプトアウト（CCPA 固有）：[この節](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)を参照してください。

Campaign の主なプライバシー機能と関与するペルソナの例を[この節](#personal-data)に示します。


### 同意、保持、役割 {#consent}

Adobe Campaign には、プライバシーに不可欠な重要な機能が最初から用意されています。

* **同意の管理**：購読管理プロセスを通じて、受信者の環境設定を管理し、どの受信者がどの購読タイプにオプトインしたかを追跡できます。詳しくは、[購読](../../audiences/using/about-subscriptions.md)と[ランディングページ](../../channels/using/getting-started-with-landing-pages.md)を参照してください。
* **データ保持**：すべてのビルトインの標準ログテーブルには事前に設定された保存期間があり、通常、データのストレージは 6 か月以下に制限されます。その他の保存期間は、ワークフローで設定できます。詳しくは、アドビのコンサルタントまたは技術管理者にお問い合わせください。
* **権限管理**：Adobe Campaign では、事前作成された役割またはカスタムの役割を使用して、様々な Campaign オペレーターに割り当てられている権限を管理できます。これにより、会社内で様々なタイプのデータにアクセス、変更、書き出しできるユーザーを管理できます。詳しくは、[アクセス管理について](../../administration/using/about-access-management.md)を参照してください。

これらの機能および Adobe Campaign での管理方法について詳しくは、[このページ](../../start/using/privacy-management.md#consent-retention-roles)を参照してください。

### プライバシーリクエスト {#privacy-requests}

Adobe Campaign には、特定のプライバシーリクエストに対するデータ管理者としての準備を容易にするためのその他の機能が用意されています。

* **アクセスする権利**&#x200B;とは、データ主体がデータ管理者に、自分に関する個人データが処理されているかどうか、また処理されている場合はその場所と目的について確認できることを指します。

* 「**忘れられる権利**」（削除要求）により、データ主体はデータコントローラーに個人データを消去させることができます。

>[!NOTE]
>
>このツールセットは、GDPR、CCPA および PDPA のプライバシーコンプライアンスを支援するために用意されています。これらの様々な規則について詳しくは、[このページ](../../start/using/privacy-management.md#privacy-management-regulations)を参照してください。

**アクセス**&#x200B;要求と&#x200B;**削除**&#x200B;要求は、[このページ](../../start/using/privacy-management.md#right-access-forgotten)に表示されます。これらのリクエストを作成するための実装手順については、[このページ](../../start/using/privacy-requests.md#about-privacy-requests)で詳しく説明しています。チュートリアルは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=ja)からもご利用いただけます。

## トラッキング機能 {#tracking-capabilities}

Adobe Campaign のトラッキング機能により、セッション Cookie と永続 Cookie を使用して配信先の行動をトラッキングできます。トラッキングの詳細については、[このページ](../../sending/using/tracking-messages.md)を参照してください。

>[!NOTE]
>
>EU 一般データ保護規則（GDPR）などの規制では、企業は Cookie をインストールする前に Web サイトのユーザーから同意を得ることが規定されています。認証リクエストを通じて、サイトに Web トラッキングツールが装備されていることをユーザーに通知する必要があります。

また、メッセージに[トラッキング用リンク](../../designing/using/links.md#about-tracked-urls)を追加して、[トラッキング指標](../../reporting/using/tracking-indicators.md)のビルトインレポートで配信の影響と受信者の行動を測定したり、独自の[専用レポート](../../reporting/using/about-dynamic-reports.md)を作成したりすることもできます。

