---
title: プライバシーと推奨事項についてAdobe Campaign標準
description: この節では、プライバシー管理についてAdobe Campaign標準で説明します。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0d7dc73afb2e3b69f461d0e389451c9deabc1f23

---


# Privacy and Consent{#privacy-and-consent}

## 一般的な推奨事項 {#general-recommendations}

Adobe Campaignは、個人情報や機密データを含む、非常に大量のデータを収集し、処理するための強力なツールです。 プライバシーを慎重に管理する必要があるのはこのためです。

* 個人情報を常に責任を持ち倫理的に利用しなさい。

* 迷惑メール、プッシュ通知、SMSメッセージ（「スパム」）の送信は控えます。 アドビは、顧客の全期間の価値と忠誠度を高めるための許可型マーケティングの原則を強く信じており、そのため、非要請メッセージの送信にAdobe Campaignを使用することを厳しく禁じています。

### プライバシー規制 {#privacy-regulations}

プライバシーを正しく処理し、個人データを管理するには、お客様が運営する地域に適した立法制度の範囲内で作業します。 以下の規則が適用されます。
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) （欧州総合データ保護規制）
* [DPA](https://www.gov.uk/data-protection) （英国でのGDPRの実装）
* [欧州プライバシー・電子通信に関する指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM法](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) （商用電子メールのルールと要件を設定する米国の法律）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4&amp;chapter=&amp;article=) （カリフォルニア消費者プライバシー法）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) （タイ個人データ保護法）

>[!NOTE]
>
>GDPR、CCPA、およびPDPAのAdobe Campaignへの適用方法について詳しくは、このページを参照し [てください](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaignは、Adobe Experience Cloudソリューションの一部です。 Adobe Experience Cloudの一般原則(以下に示すキャンペーン)に従ってプライバシーを処理する方法。

* **Adobe Experience Cloudを使用する際に収集される情報**

   Adobe Experience Cloudソリューションを使用する会社として、収集してAdobe Experience Cloudアカウントに送信する情報を選択します。 収集される情報のタイプの例としては、Web閲覧アクティビティ、IPアドレス、モバイルデバイスからの場所情報、キャンペーンの成功率、購入した品目、買い物かごに入れた品目などがあります。

   >[!NOTE]
   >
   >すべてのアドビ製品に関して、キャンペーンはアプリとWebサイトのユーザーに関する情報を収集します。 詳しくは、アドビのプライバシーポリシーを [参照してください](https://www.adobe.com/privacy/policy.html)。

* **Adobe Experience Cloudを使用した情報の収集方法**

   * Adobe Experience Cloudソリューションは、Webビーコン（タグやピクセルとも呼ばれる）などのcookieや類似のテクノロジーを使用して、情報を収集します。 CookieとAdobe Campaignの追跡機能について詳しくは、この節を参照し [てください](#tracking-capabilities)。
   * また、モバイルアプリ内でAdobe Experience Cloudテクノロジーを使用することもできます。 モバイル配信とキャンペーンの送信について詳しくは、このページを [参照してくださ](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)い。

* **Adobe Experience Cloudの使用に関するプライバシーの選択**

   アドビから、次の内容を説明するプライバシーポリシーを顧客に提供するように求められます。

   * Adobe Experience Cloudに関するプライバシープラクティス
   * Adobe Experience Cloudに関連して、ユーザーが情報の収集や使用に関する環境設定を行う方法
   >[!NOTE]
   >
   >すべてのアドビ製品について、キャンペーンユーザーは、アプリやWebサイトで収集した情報の共有をオプトアウトできます。 詳しくは、 [Adobe Experience Cloudの使用状況に関するFAQを参照してください](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)。

Adobe Experience Cloudのプライバシーについて詳しくは、このページを参照 [してください](https://www.adobe.com/privacy/marketing-cloud.html)。

## 個人データと個人 {#personal-data}

プライバシーを管理する際は、どのデータをどのような人が注意深く扱うかを定義することが重要です。
* **個人データは** 、生きている個人を直接または間接的に識別できる情報です。
* **「個人の機密データ** 」とは、個人の人種、政治表示、宗教的信念、犯罪的背景、遺伝情報、健康データ、性嗜好、生体認証情報、および貿易和集合の会員に関する情報です。

主要な [立法は](#privacy-regulations) 、次のようにデータを管理する様々なエンティティを指します。
* デー **タコントローラ** (Data Controller)は、個人データの収集、使用、共有の手段と目的を決定する権限です。
* データ **プロセッサ** (Data Processor)とは、データコントローラーの指示に従って個人データを収集、使用、または共有する個人または関係者のことです。
* デー **タの対象** ：個人データが収集、使用、共有され、その個人データを参照して直接または間接的に識別できる、生きている個人です。

したがって、個人データを収集し共有する会社として、お客様はData Controllerであり、お客様のクライアントはData Subjectsであり、Adobe Campaignは、お客様の指示に従って個人データを処理する際に、データ・プロセッサとして機能します。 プライバシーリクエストを管理する場合など、データサブジェクトとの関係を処理するのは、データコントローラーとしてのお客様の責 [任であることに注意](#privacy-requests)。

オーディエンスをキャンペーンから別のオーディエンスに転送できる他のExperience Cloudソリューション( [Adobe Analytics](../../audiences/using/aep-about-audience-destinations-service.md)、オーディエンスマネージャー、Peopleコアサービスなど)と、または [](../../integrating/using/about-campaign-analytics-integration.md)[](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)[](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)Microsoft Dynamics 355などの他のソリューション（データ保護に追加費用をかける）との統合時に、

## データ取得 {#data-acquisition}

Adobe Campaignを使用すると、個人情報や機密情報などのデータを収集できます。 したがって、ユーザーの同意を受け取り、監視することが重要な受信者です。

* 常に受信者が通信を受け取ることに同意します。 これを行うには、できる限り迅速にオプトアウト要求を遵守し、重複のオプトインプロセスを通じて同意を検証します。 詳しくは、キャンペーンでのオプトイ [ンとオプトアウトの管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) および [重複オプトインプロセスの設定を参照してください](../../channels/using/setting-up-a-double-opt-in-process.md)。
* 不正なリストを読み込んだり、トラップを使用して、クライアントファイルが不正に使用されていないことを確認したりしないでください。 詳しくは、トラップの使用を参照し [てください](../../sending/using/using-traps.md)。
* 同意と権利管理を通じて、受信者の好みを追跡し、組織内の誰がどのデータにアクセスできるかを管理できます。 詳しくは、[この節](#consent)を参照してください。
* プライバシーリクエストを容易にし、受信者から管理 詳しくは、[この節](#privacy-requests)を参照してください。

## プライバシーの管理 {#privacy-management}

プライバシー管理とは、プライバシー規制（GDPR、CCPAなど）の遵守に役立つすべてのプロセスとツールを指します。 このページのプライバシー管理の概要を確 [認します](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy-overview.html)。

Adobe Campaignには、プライバシー管理に特化した様々な機能が用意されています。
* 同意の管理、データ保持、ユーザの役割。 [この節](#consent)を参照してください。
* プライバシーの要請（アクセス権及び忘却権） [この節](#privacy-requests)を参照してください。
* 個人情報の販売のオプトアウト（CCPA固有）を参照してください。 [この節](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)を参照してください。

この節では、キャンペーンの主なプライバシー機能と関与する個人の例を示 [します](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)。


### 同意、リテンション、役割 {#consent}

元々、Adobe Campaignオファーはプライバシーに不可欠な重要な機能です。

* **同意管理**:購読管理プロセスを通じて、受信者の好みを管理し、どの受信者がどのタイプの購読にオプトインしたかを追跡できます。 詳しくは、「 [購読](../../audiences/using/about-subscriptions.md) と [ランディングページ](../../channels/using/getting-started-with-landing-pages.md)」
* **データ保持**:すべての組み込みの標準ログ・テーブルには、事前に設定された保存期間があり、通常、データのストレージは6か月以下に制限されます。 保持期間を設定する場合は、ワークフロー。 詳しくは、アドビコンサルタントまたは技術管理者にお問い合わせください。
* **Rights management**:Adobe Campaignでは、様々な事前ビルドロールまたはカスタムロールを介して、様々なキャンペーンオペレーターに割り当てられた権限を管理できます。 これにより、様々なタイプのデータにアクセス、変更、またはエクスポートできる会社内のユーザーを管理できます。 For more on this, see [About access management](../../administration/using/about-access-management.md).

これらの機能およびAdobe Campaignでの管理方法について詳しくは、このページを参 [照してくださ](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent)い。

### Privacy requests {#privacy-requests}

Adobe Campaignは、特定のプライバシー要求に対するデータコントローラーとしての準備を容易にするための追加機能を提供します。

* The **Right to Access** is the right for the Data Subject to obtain from the Data Controller confirmation as to whether or not personal data concerning them is being processed, where and why.

* 「 **Right to be Fogtn** (delete request)」は、Data Subjectに対して、個人データを消去する権限を与えます。

>[!NOTE]
>
>このツールセットは、GDPR、CCPA、PDPAのプライバシーコンプライアンスに役立ちます。 これらの異なる規制について詳しくは、このページを参 [照してくださ](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)い。

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

このペ **ージには** 、 **Access** リクエストと [Deleteリクエストが](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)表示されます。 これらのリクエストを作成するための実装手順については、このページ [で詳しく説明しま](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)す。 チュートリアルは、こちらからもご利 [用いただ](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html)けます。

## 追跡機能 {#tracking-capabilities}

Adobe Campaignでは、その追跡機能のおかげで、セッションcookieと永久的なcookieを使用して、配信受信者の動作を追跡できます。 追跡について詳しくは、このページを参 [照してくださ](../../sending/using/tracking-messages.md)い。

>[!NOTE]
>
>GDPR(General Data Protection Regulation)などの規制では、Cookieをインストールする前に、会社はWebサイトのユーザーの同意を必要とすると規定されています。 認証リクエストを通じて、サイトにWebトラッキングツールが装備されていることをユーザーに通知する必要があります。

追跡リンクをメッセ [ージに追加し](../../designing/using/links.md#about-tracked-urls) 、追跡インジケーターの組み込みレポートでの配信や受信者の動作の影響を測定したり、独自の専用レポートを作成したりすることも [できます](../../reporting/using/tracking-indicators.md)[](../../reporting/using/about-dynamic-reports.md)。
