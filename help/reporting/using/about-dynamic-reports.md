---
solution: Campaign Standard
product: campaign
title: 動的レポートの概要
description: 動的レポートでは、変数やディメンションをフリーフォーム環境にドラッグ&ドロップし、キャンペーンの成功を分析します。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: レポート
role: リーダー
level: 初心者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 6%

---


# 動的レポートの概要 {#about-dynamic-reports}

動的レポートは、完全にカスタマイズ可能なリアルタイムレポートを提供します。 プロファイルデータへのアクセスを追加し、性別、市区町村、年齢などのプロファイルディメンション別の人口統計的な分析を可能にするほか、オープン数やクリック数などの機能的な電子メールキャンペーンデータも利用できます。 ドラッグ＆ドロップインターフェイスを使用してデータを分析し、最も重要な顧客セグメントに対する E メールキャンペーンの効果や受信者への影響を測定できます。

>[!NOTE]
>
>管理権限を持つユーザー、または組織単位（**すべて**）が設定されているユーザーのみが、新しいレポートを作成または保存できます。 詳しくは、[この節](../../administration/using/users-management.md)を参照してください。

## 動的レポートへのアクセス{#accessing-dynamic-reports}

レポートには次のアクセスができます。

* ホームページで上部のバーの&#x200B;**[!UICONTROL Reports]**&#x200B;タブを選択するか、**[!UICONTROL Reports]**&#x200B;カードを選択してすべての配信のレポートにアクセスします。

   ![](assets/campaign_reports_access.png)

* 各プログラム、キャンペーンおよびメッセージで、**「レポート**」ボタンから&#x200B;**動的レポート**&#x200B;をクリックして、配信に固有のレポートのみを表示します。

   ![](assets/campaign_reports_description.png)

配信の収集と処理に要する時間によっては、情報の収集後すぐにレポートを利用できない場合があります。

動的レポートは2つのカテゴリに分かれています。

* **テンプレート**。テンプレートは **、「** 名前を付けて保存」オプション(**プロジェクト/名前を付けて保存…)を使用してコピーすることで変更できます。**)をテンプレートに追加します。
* **カスタムレポート** （青色で識別）。レポートホームページの「新しい **プロジェクトを** 作成」ボタンをクリックして、直接作成でき **** ます。

>[!NOTE]
>
>組織単位に応じてデータがフィルタされます。

![](assets/dynamic_report_overview.png)

## 動的なレポート使用許諾{#dynamic-reporting-usage-agreement}

動的レポート使用許諾契約の目的は、データ処理に関するポップアップ同意として機能することです。 デフォルトでは、契約は表示されるだけで、管理者権限を持つユーザーのみが同意または拒否できます。

次の 3 つのオプションを選択できます。

* **[!UICONTROL Ask me later]**:[ **後で確認する**]をクリックすると、24時間ウィンドウの表示が停止します。契約に同意するか却下するまで、プロファイルディメンションはレポートに表示されず、顧客の個人ID情報は収集または送信されません。
* **[!UICONTROL Accept]**:本契約に同意すると、Adobe Campaignが顧客の個人識別情報を収集し、レポートまたはデータセンターに転送することを許可します。
* **[!UICONTROL Decline]**:契約を拒否すると、プロファイルディメンションはレポートに表示されず、顧客の個人ID情報は収集または送信されません。この場合、externalIDは引き続き収集され、エンドユーザーの識別に使用されます。

次の表に、お客様の地域に応じて、本契約に同意した後の動作を示します。

|  | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **機能を利用可能**。<br>既製の情報（市区町村、国/地域、州、性別、セグメントなど、年齢別）とカスタムプロファイル情報はすべて、米国のレポートセンターに送り込まれます。プロファイルディメンションの詳細については、[ページ](../../reporting/using/list-of-components-.md)を参照してください。 | **機能を利用可能**。<br>すべての既製のプロファイルフィールドおよびカスタムイベントフィールドは、米国のデータセンターで処理されます。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **機能を利用可能**。<br>設定なし（市区町村、国/地域、州、性別、セグメントなど、年齢別）、カスタムプロファイル情報は、EMEAレポートセンターに送り込まれます。プロファイルディメンションの詳細については、[ページ](../../reporting/using/list-of-components-.md)を参照してください。 | **機能を使用できます。** <br>すべての既製およびカスタムプロファイルフィールドと、EMEAデータセンターで処理されるAdobe Campaign Standardイベントフィールド。<br>**[!UICONTROL Control data]**このIDには、Adobe I/O登録データと、米国のデータセンターに送信および保存される顧客エンドユーザイベントのIDが含まれます。 |

下の表に、お住まいの地域に応じてこの契約を却下した場合の状況を示します。 この契約に同意しない場合でも、配信とMicrosoft Dynamics 365の統合に関するレポートは引き続き使用できます。

| 地域 | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **機能を利用可能**。<br> ExternalID以外の、標準搭載されたプロファイルやカスタム情報が米国のレポートセンターに送り込まれることはありません。 | **機能を利用可能**。<br>外部IDと受信者IDを除き、標準搭載されたフィールドやカスタムプロファイルフィールドは米国のデータセンターに送信されません。<br>ミラーページID以外の、米国のデータセンターで処理されたすべてのAdobe Campaign Standardイベントフィールド。<br>Microsoft Dynamics 365の統合の詳細については、この [ページを参照してください](../../integrating/using/d365-acs-get-started.md)。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **機能を利用可能**。<br>ExternalID以外の既製の情報やカスタムプロファイル情報は、EMEAレポートセンターに送り込まれません。 | **機能を使用できます。** <br>追加設定なしでEMEAデータセンターに送信されるプロファイルフィールドやカスタムフィールドはありません。ただし、外部IDと受信者IDは例外です。<br>ミラーページIDを除き、EMEAデータセンターで処理されたすべてのAdobe Campaign Standardイベントフィールド。<br>**[!UICONTROL Control data]**このIDには、Adobe I/O登録データと、米国のデータセンターに送信および保存される顧客エンドユーザイベントのIDが含まれます。<br>Microsoft Dynamics 365の統合の詳細については、この [ページを参照してください](../../integrating/using/d365-acs-get-started.md)。 |

この選択は最終的なものではありません。**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;で&#x200B;**[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]**&#x200B;を選択すると、いつでも変更できます。

値はいつでも変更できます。 値1は、**[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]**&#x200B;および3 **[!UICONTROL Accept]**&#x200B;に対応します。

![](assets/pii_window_2.png)
