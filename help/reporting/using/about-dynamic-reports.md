---
title: 動的レポートの基本を学ぶ
description: 動的レポートでは、変数とディメンションをフリーフォーム環境にドラッグ&ドロップし、キャンペーンの成功を分析します。
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

動的レポートは、完全にカスタマイズ可能なリアルタイムレポートを提供します。 プロファイルデータへのアクセスを追加し、開封数やクリック数などの機能的なEメールキャンペーンデータに加えて、性別、市区町村、年齢などのプロファイルディメンションによる人口統計分析を有効にします。 ドラッグ＆ドロップインターフェイスを使用してデータを分析し、最も重要な顧客セグメントに対する E メールキャンペーンの効果や受信者への影響を測定できます。

>[!NOTE]
>
>管理権限を持つユーザー、または組織単位が&#x200B;**すべて**&#x200B;に設定されているユーザーのみ、新しいレポートを作成または保存できます。 詳しくは、[この節](../../administration/using/users-management.md)を参照してください。

## 動的レポートへのアクセス {#accessing-dynamic-reports}

レポートには次の場所からアクセスできます。

* ホームページから、上部のバーの「**[!UICONTROL Reports]**」タブまたは&#x200B;**[!UICONTROL Reports]**&#x200B;カードを選択して、すべての配信のレポートにアクセスします。

   ![](assets/campaign_reports_access.png)

* 各プログラム、キャンペーンおよびメッセージで、「**レポート**」ボタンをクリックし、「**動的レポート**」をクリックして、配信に固有のレポートのみを表示します。

   ![](assets/campaign_reports_description.png)

配信後は、情報の収集と処理に要する時間によっては、一部のレポートをすぐに使用できない場合があります。

動的レポートは、次の2つのカテゴリに分類されます。

* **テンプレート**&#x200B;を編集するには、「名前を付けて保存」オプション( **プ** ロジェク&#x200B;**ト/名前を付けて保存。.**)をテンプレート内でクリックします。
* **カスタムレポート** （青で識別）：レポートショームページの「新規プロジェクトを作 **成」ボタンをクリ** ックして、直接作 **** 成できます。

>[!NOTE]
>
>データは組織単位に応じてフィルタリングされます。

![](assets/dynamic_report_overview.png)

## 動的レポートの使用契約 {#dynamic-reporting-usage-agreement}

動的レポートの使用契約の目的は、データ処理に対するポップアップの同意として機能することです。 デフォルトでは、契約は表示のみされ、管理権限を持つユーザーのみが同意または拒否できます。

次の 3 つのオプションを選択できます。

* **[!UICONTROL Ask me later]**:「後で確認 **する**」をクリックすると、ウィンドウが24時間表示されなくなります。契約に同意するか拒否するまで、プロファイルディメンションはレポートに表示されず、顧客の個人情報は収集または送信されません。
* **[!UICONTROL Accept]**:この契約に同意すると、Adobe Campaignがお客様の個人識別情報を収集し、レポートまたはデータセンターに転送することを許可します。
* **[!UICONTROL Decline]**:契約を却下すると、プロファイルのディメンションはレポートに表示されず、顧客の個人情報は収集も送信もされません。この場合、 externalIDは引き続き収集され、エンドユーザーの識別に使用されます。

以下の表に、お客様の地域に応じて、本契約に同意した後の動作を示します。

|  | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **使用可能な機能**。<br>すべての標準（市区町村、国/地域、州、性別、年齢ベースのセグメント）と、米国のレポートセンターにプッシュされたカスタムプロファイル情報。プロファイルディメンションについて詳しくは、この[ページ](../../reporting/using/list-of-components-.md)を参照してください。 | **使用可能な機能**。<br>すべての既製プロファイルフィールドおよびカスタムプロファイルフィールドとAdobe Campaign Standardイベントフィールドは、米国のデータセンターで処理されます。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **使用可能な機能**。<br>EMEAレポートセンターにプッシュされるすべての標準（市区町村、国/地域、州、性別、セグメントなど、年齢単位）とカスタムプロファイル情報。プロファイルディメンションについて詳しくは、この[ページ](../../reporting/using/list-of-components-.md)を参照してください。 | **機能を使用できます。** <br>EMEAデータセンターで処理される、すべての標準およびカスタムプロファイルフィールドとAdobe Campaign Standardイベントフィールド。<br>**[!UICONTROL Control data]**:Adobe I/O登録データと、米国のデータセンターに送信および保存される顧客エンドユーザーイベントのIDが含まれます。 |

下の表は、お住まいの地域に応じて、本契約を却下した後の結果を示しています。 この契約に同意しない場合でも、配信とMicrosoft Dynamics 365統合に関するレポートは引き続き使用できます。

| 地域 | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **使用可能な機能**。<br> ExternalIDを除き、標準のおよびカスタムプロファイル情報が米国のレポートセンターにプッシュされることはありません。 | **使用可能な機能**。<br>外部IDと受信者IDを除き、標準のまたはカスタムプロファイルフィールドが米国データセンターに送信されない。<br>ミラーページIDを除く、米国のデータセンターで処理されるすべてのAdobe Campaign Standardイベントフィールド。<br>Microsoft Dynamics 365統合の詳細については、このページを参照して [ください](../../integrating/using/d365-acs-get-started.md)。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **使用可能な機能**。<br>ExternalIDを除き、EMEAレポートセンターに既製のプロファイルおよびカスタムプロファイル情報をプッシュすることはありません。 | **機能を使用できます。** <br>外部IDと受信者IDを除き、EMEAデータセンターにデフォルトまたはカスタムプロファイルフィールドは送信されません。<br>ミラーページIDを除く、EMEAデータセンターで処理されるすべてのAdobe Campaign Standardイベントフィールド。<br>**[!UICONTROL Control data]**:Adobe I/O登録データと、米国のデータセンターに送信および保存される顧客エンドユーザーイベントのIDが含まれます。<br>Microsoft Dynamics 365統合の詳細については、このページを参照して [ください](../../integrating/using/d365-acs-get-started.md)。 |

この選択は最終的なものではありません。 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;で「**[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]**」を選択すれば、いつでも変更できます。

値はいつでも変更できます。 値1は、**[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]**&#x200B;および3 **[!UICONTROL Accept]**&#x200B;に対応します。

![](assets/pii_window_2.png)
