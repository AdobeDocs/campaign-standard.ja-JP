---
title: データをインポートするワークフローテンプレートの作成
description: データを読み込むワークフローテンプレートの作成方法について説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
TQID: https://experienceleague.adobe.com/u3VuLGtTmsM-4wztLfsNhGIX2F-aVI1HTtaCqXinBPw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1177
ht-degree: 38%

---

# データをインポートするワークフローテンプレートの作成 {#import-workflow-template}

同じ構造のファイルを頻繁にインポートする必要がある場合、インポートテンプレートを使用することをお勧めします。

この例では、Adobe Campaign データベースの CRM からのプロファイルのインポートに再利用できるワークフローを事前設定する方法を示します。

1. **[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;から新しいワークフローテンプレートを作成します。
1. 次のアクティビティを追加します。

   * **[!UICONTROL Load file]**：読み込むデータを含むファイルの想定される構造を定義します。

     >[!NOTE]
     >
     >1つのファイルからのみデータを読み込むことができます。 ワークフローに複数の&#x200B;**[!UICONTROL Load file]** アクティビティがある場合、同じファイルが毎回使用されます。

   * **[!UICONTROL Reconciliation]**: インポートしたデータをデータベース データと紐付けます。
   * **[!UICONTROL Segmentation]**：レコードを紐付けできるかどうかに応じて、レコードを異なる方法で処理するフィルターを作成します。
   * **[!UICONTROL Deduplication]**：受信ファイルのデータがデータベースに挿入される前に、そのデータの重複を削除します。
   * **[!UICONTROL Update data]**: インポートしたプロファイルでデータベースを更新します。

   ![](assets/import_template_example0.png)

1. **[!UICONTROL Load file]** アクティビティを設定します。

   * サンプルファイルをアップロードすることで、求められる構造を定義します。 サンプルファイルには、インポートに必要なすべての列と、いくつかの行のみが含まれている必要があります。 ファイルフォーマットをチェックおよび編集して、各列のタイプが正しく設定されていることを確認します（テキスト、日付、整数など）。次に例を示します。

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * **[!UICONTROL File to load]** セクションで、**[!UICONTROL Upload a new file from the local machine]**&#x200B;を選択し、フィールドを空白のままにします。 このテンプレートから新しいワークフローを作成するたびに、ここで、定義された構造に対応するファイルを指定できます。

     任意のオプションを使用できますが、それに応じてテンプレートを修正する必要があります。 例えば、**[!UICONTROL Use the file specified in the inbound transition]**&#x200B;を選択した場合、FTP/SFTP サーバーから読み込むファイルを取得する前に&#x200B;**[!UICONTROL Transfer file]** アクティビティを追加できます。

     読み込み中に発生したエラーを含むファイルをユーザーがダウンロードできるようにするには、**[!UICONTROL Keep the rejects in a file]** オプションを確認し、**[!UICONTROL File name]**&#x200B;を指定します。

     ![](assets/import_template_example1.png)

1. **[!UICONTROL Reconciliation]** アクティビティを設定します。 ここでのこのアクティビティの目的は、受信データを識別することです。

   * 「**[!UICONTROL Relations]**」タブで、**[!UICONTROL Create element]**&#x200B;を選択し、読み込まれたデータと受信者ターゲティングディメンションとの間のリンクを定義します（[&#x200B; ターゲティングディメンションとリソース &#x200B;](../../automating/using/query.md#targeting-dimensions-and-resources)を参照）。 この例では、結合条件の作成に **CRM ID** カスタムフィールドが使用されています。 一意のレコードを識別できる限り、必要なフィールドまたはフィールドの組み合わせを使用します。
   * 「**[!UICONTROL Identification]**」タブで、「**[!UICONTROL Identify the document from the working data]**」オプションをオフのままにします。

   ![](assets/import_template_example2.png)

1. **[!UICONTROL Segmentation]** アクティビティを設定して、1つの移行で調整済みの受信者を取得し、調整できなかったものの、2番目の移行で十分なデータを持つ受信者を取得します。

   紐付けされた受信者を含むトランジションは、データベースを更新するために使用できます。 不明な受信者を含むトランジションは、ファイルで最小限の情報が利用できる場合、データベースに新しい受信者エントリを作成するために使用できます。

   紐付けできず、十分なデータを持たない受信者は、補集合アウトバウンドトランジションで選択され、別のファイルにエクスポートしたり、単純に無視したりできます。

   * アクティビティの「**[!UICONTROL General]**」タブで、**[!UICONTROL Resource type]**&#x200B;を&#x200B;**[!UICONTROL Temporary resource]**&#x200B;に設定し、ターゲットセットとして「**[!UICONTROL Reconciliation]**」を選択します。
   * 「**[!UICONTROL Advanced options]**」タブで、「**[!UICONTROL Generate complement]**」オプションをチェックして、データベースにレコードを挿入できないかどうかを確認します。 必要に応じて、補完データのさらなる処理（ファイルエクスポート、リスト更新など）を適用できます。
   * **[!UICONTROL Segments]** タブの最初のセグメントで、インバウンド母集団にフィルター条件を追加して、プロファイルのCRM IDが0と等しくないレコードのみを選択します。 これにより、データベースのプロファイルと紐付けられたファイルのデータが、そのサブセットで選択されます。

     ![](assets/import_template_example3.png)

   * データベースに挿入するのに十分なデータを持つ未調整レコードを選択する2番目のセグメントを追加します。 （例：メールアドレス、姓名）。 紐付けされていないレコードのプロファイルのCRM ID値は0になります。

     ![](assets/import_template_example3_2.png)

   * 最初の2つのサブセットで選択されていないレコードはすべて、**[!UICONTROL Complement]**&#x200B;で選択されます。

1. 以前に設定した&#x200B;**[!UICONTROL Segmentation]** アクティビティの最初のアウトバウンドトランジションの後にある&#x200B;**[!UICONTROL Update data]** アクティビティを設定します。

   * インバウンドトランジションには、既にデータベースに存在する受信者のみが含まれているため、**[!UICONTROL Update]**&#x200B;を&#x200B;**[!UICONTROL Operation type]**&#x200B;として選択します。
   * 「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Using reconciliation criteria]**」を選択し、「**[!UICONTROL Dimension to update]** - プロファイル （この場合）」と「**[!UICONTROL Reconciliation]**」アクティビティで作成されたリンクの間のキーを定義します。 この例では、**CRM ID** カスタムフィールドが使用されています。

     ![](assets/import_template_example6.png)

   * 「**[!UICONTROL Fields to update]**」タブで、ファイルの対応する列の値で更新するプロファイルディメンションのフィールドを指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >これらのプロファイルにダイレクトメールを送信する場合は、この情報がダイレクトメールプロバイダーに不可欠であるため、必ず郵送先住所を含めてください。 また、プロファイルの情報にある「**[!UICONTROL Address specified]**」ボックスがオンになっていることを確認します。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、**1**&#x200B;を&#x200B;**[!UICONTROL Source]**&#x200B;として指定し、`postalAddress/@addrDefined` フィールドを&#x200B;**[!UICONTROL Destination]**&#x200B;として選択します。 ダイレクトメールと&#x200B;**[!UICONTROL Address specified]** オプションの使用について詳しくは、[このドキュメント &#x200B;](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

1. 未調整プロファイルを含むトランジションの後にある&#x200B;**[!UICONTROL Deduplication]** アクティビティを設定します。

   * 「**[!UICONTROL Properties]**」タブで、**[!UICONTROL Resource type]**&#x200B;をワークフローの&#x200B;**[!UICONTROL Reconciliation]** アクティビティから生成された一時リソースに設定します。

     ![](assets/import_template_example4.png)

   * この例では、一意のプロファイルを見つけるために、メールフィールドが使用されています。 入力されていることがわかっており、一意の組み合わせを構成する任意のフィールドを使用できます。
   * **[!UICONTROL Deduplication method]**&#x200B;を選択してください。 この場合、アプリケーションは、重複が発生した場合に保持するレコードを自動的に決定します。

   ![](assets/import_template_example7.png)

1. 以前に設定した&#x200B;**[!UICONTROL Deduplication]** アクティビティの後にある&#x200B;**[!UICONTROL Update data]** アクティビティを設定します。

   * インバウンドトランジションには、データベースに存在しないプロファイルのみが含まれているため、**[!UICONTROL Insert only]**&#x200B;を&#x200B;**[!UICONTROL Operation type]**&#x200B;として選択します。
   * 「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Using reconciliation criteria]**」を選択し、「**[!UICONTROL Dimension to update]** - プロファイル （この場合）」と「**[!UICONTROL Reconciliation]**」アクティビティで作成されたリンクの間のキーを定義します。 この例では、**CRM ID** カスタムフィールドが使用されています。

     ![](assets/import_template_example6.png)

   * 「**[!UICONTROL Fields to update]**」タブで、ファイルの対応する列の値で更新するプロファイルディメンションのフィールドを指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >これらのプロファイルにダイレクトメールを送信する場合は、この情報がダイレクトメールプロバイダーに不可欠であるため、必ず郵送先住所を含めてください。 また、プロファイルの情報にある「**[!UICONTROL Address specified]**」ボックスがオンになっていることを確認します。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、**1**&#x200B;を&#x200B;**[!UICONTROL Source]**&#x200B;として指定し、**[postalAddress/@addrDefined]** フィールドを&#x200B;**[!UICONTROL Destination]**&#x200B;として選択します。 ダイレクトメールと&#x200B;**[!UICONTROL Address specified]** オプションの使用について詳しくは、[このドキュメント &#x200B;](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

1. **[!UICONTROL Segmentation]** アクティビティの3回目の移行の後、データベースに挿入されていないデータを追跡する場合は、**[!UICONTROL Extract file]** アクティビティと&#x200B;**[!UICONTROL Transfer file]** アクティビティを追加します。 これらのアクティビティを設定して、必要な列をエクスポートし、ファイルを取得可能な FTP または SFTP サーバーにファイルを転送します。
1. **[!UICONTROL End]** アクティビティを追加し、ワークフローテンプレートを保存します。

これで、テンプレートが使用できるようになり、すべての新規ワークフローに利用できます。 次に、**[!UICONTROL Load file]** アクティビティに読み込むデータを含むファイルを指定するために必要なのは、すべてです。

![](assets/import_template_example9.png)
