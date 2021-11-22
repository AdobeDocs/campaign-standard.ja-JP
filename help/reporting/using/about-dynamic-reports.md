---
title: 動的レポートの基本を学ぶ
description: 動的レポートを使用して、変数とディメンションをフリーフォーム環境にドラッグ&ドロップし、キャンペーンの成功を分析します。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---

# 動的レポートの基本を学ぶ {#about-dynamic-reports}

動的レポートは、完全にカスタマイズ可能なリアルタイムレポートを提供します。 プロファイルデータへのアクセスを追加し、性別、市区町村、年齢などのプロファイルディメンションによる人口統計分析に加えて、開封数やクリック数などの機能的な E メールキャンペーンデータを有効にします。 ドラッグ＆ドロップインターフェイスを使用してデータを分析し、最も重要な顧客セグメントに対する E メールキャンペーンの効果や受信者への影響を測定できます。

>[!NOTE]
>
>管理権限を持つユーザー、または組織単位がに設定されているユーザーのみ **すべて** 新しいレポートを作成または保存できます。 詳しくは、[この節](../../administration/using/users-management.md)を参照してください。

## 動的レポートへのアクセス {#accessing-dynamic-reports}

レポートには次の場所でアクセスできます。

* ホームページで、 **[!UICONTROL Reports]** 上部のバーのタブまたは **[!UICONTROL Reports]** カードを使用して、すべての配信のレポートにアクセスできます。

   ![](assets/campaign_reports_access.png)

* 各プログラム、キャンペーン、メッセージで、 **レポート** ボタンをクリックして **動的レポート** ：配信に関するレポートのみを表示します。

   ![](assets/campaign_reports_description.png)

配信後すぐに使用できないレポートもあります。これは、情報の収集と処理に要する時間によって異なります。

動的レポートは、次の 2 つのカテゴリに分かれています。

* **テンプレート**（を使用してコピーすることで変更可能） **名前を付けて保存** オプション (**プロジェクト/名前を付けて保存…**) をテンプレート内に追加します。
* **カスタムレポート** （青で識別）。 **新規プロジェクトを作成** ボタン **レポート** ホームページ。

>[!NOTE]
>
>データは組織単位に応じてフィルタリングされます。

![](assets/dynamic_report_overview.png)

## 動的レポートの使用契約 {#dynamic-reporting-usage-agreement}

動的レポートの使用契約の目的は、データの処理に関するポップアップの同意として機能することです。 デフォルトでは、契約は表示のみされ、管理権限を持つユーザーのみが同意または拒否できます。

次の 3 つのオプションを選択できます。

* **[!UICONTROL Ask me later]**:クリック **後で確認する**&#x200B;を指定した場合、ウィンドウは 24 時間表示されなくなります。 契約に同意するか拒否するまで、プロファイルディメンションはレポートに表示されず、顧客の個人識別情報は収集も送信もされません。
* **[!UICONTROL Accept]**:この契約に同意すると、Adobe Campaignがお客様の個人 ID 情報を収集し、それらをレポートまたはデータセンターに転送することを許可します。
* **[!UICONTROL Decline]**:契約を却下すると、プロファイルのディメンションがレポートに表示されなくなり、顧客の個人 ID 情報は収集も送信もされません。 この場合、 externalID は引き続き収集され、エンドユーザーの識別に使用されます。

以下の表は、お客様の地域に応じて、本契約に同意した後の動作を示します。

|  | 動的レポート | Microsoft Dynamics 365 コネクタ |
|---|---|---|
| アメリカおよび APAC（アジア太平洋） | **使用可能な機能**. <br>すべての標準（市区町村、国/地域、州、性別、年齢ベースのセグメント）とカスタムプロファイル情報が、米国のレポートセンターにプッシュされました。 プロファイルディメンションについて詳しくは、 [ページ](../../reporting/using/list-of-components-.md) | **使用可能な機能**. <br>すべての標準およびカスタムプロファイルフィールドとAdobe Campaign Standardイベントフィールドは、米国のデータセンターで処理されます。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **使用可能な機能**. <br>標準（市区町村、国/地域、州、性別、年齢ベースのセグメント）と、EMEA レポートセンターにプッシュされたカスタムプロファイル情報。 プロファイルディメンションについて詳しくは、 [ページ](../../reporting/using/list-of-components-.md) | **機能を使用できます。** <br>EMEA データセンターで処理される、すべての標準およびカスタムプロファイルフィールドとAdobe Campaign Standardイベントフィールド。 <br>**[!UICONTROL Control data]**Adobe I/O登録データと、米国のデータセンターで送信および保存される顧客のエンドユーザーイベントの ID が含まれる |

下の表は、お住まいの地域に応じてこの契約を却下した後の結果を示しています。 この契約に同意しない場合でも、配信とMicrosoft Dynamics 365 統合に関するレポートは引き続き使用できます。

| 地域 | 動的レポート | Microsoft Dynamics 365 コネクタ |
|---|---|---|
| アメリカおよび APAC（アジア太平洋） | **使用可能な機能**. <br> ExternalID を除き、標準のおよびカスタムプロファイル情報が米国のレポートセンターにプッシュされることはありません。 | **使用可能な機能**. <br>外部 ID と受信者 ID を除き、標準のプロファイルフィールドやカスタムプロファイルフィールドが US データセンターに送信されない。 <br>ミラーページ ID を除く、米国のデータセンターで処理されるすべてのAdobe Campaign Standardイベントフィールド。 <br>Microsoft Dynamics 365 の統合について詳しくは、こちらを参照してください。 [ページ](../../integrating/using/d365-acs-get-started.md). |
| EMEA（ヨーロッパ中東およびアフリカ） | **使用可能な機能**. <br>ExternalID を除き、EMEA レポートセンターに既製のプロファイルおよびカスタムプロファイル情報がプッシュされない。 | **機能を使用できます。** <br>外部 ID および受信者 ID を除き、EMEA データセンターに標準またはカスタムのプロファイルフィールドが送信されない。 <br>ミラーページ ID を除く、EMEA データセンターで処理されるすべてのAdobe Campaign Standardイベントフィールド。  <br>**[!UICONTROL Control data]**Adobe I/O登録データと、米国のデータセンターで送信および保存される顧客のエンドユーザーイベントの ID が含まれる<br>Microsoft Dynamics 365 の統合について詳しくは、こちらを参照してください。 [ページ](../../integrating/using/d365-acs-get-started.md). |

この選択は最終的なものではありません。いつでも、「 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

値はいつでも変更できます。 値 1 は、に対応します。 **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** および 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
