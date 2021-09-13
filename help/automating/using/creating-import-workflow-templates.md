---
title: データをインポートするワークフローテンプレートの作成
description: データをインポートするためのワークフローテンプレートの作成方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 38%

---

# データをインポートするワークフローテンプレートの作成 {#import-workflow-template}

同じ構造のファイルを頻繁にインポートする必要がある場合、インポートテンプレートを使用することをお勧めします。

この例では、Adobe Campaign データベースの CRM からのプロファイルのインポートに再利用できるワークフローを事前設定する方法を示します。

1. **[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;から新しいワークフローテンプレートを作成します。
1. 次のアクティビティを追加します。

   * **[!UICONTROL Load file]**:インポートするデータを含むファイルに求められる構造を定義します。

      >[!NOTE]
      >
      >1つのファイルからのみデータをインポートできます。 ワークフローに複数の&#x200B;**[!UICONTROL Load file]**&#x200B;アクティビティがある場合は、毎回同じファイルが使用されます。

   * **[!UICONTROL Reconciliation]**:インポートしたデータをデータベースデータに紐付けします。
   * **[!UICONTROL Segmentation]**:フィルターを作成して、紐付けできたかどうかに応じて別々にレコードを処理します。
   * **[!UICONTROL Deduplication]**:データベースに挿入される前に、受信ファイルのデータを重複排除します。
   * **[!UICONTROL Update data]**:インポートしたプロファイルでデータベースを更新します。

   ![](assets/import_template_example0.png)

1. **[!UICONTROL Load file]**&#x200B;アクティビティを設定します。

   * サンプルファイルをアップロードすることで、求められる構造を定義します。サンプルファイルには、インポートに必要なすべての列と、いくつかの行のみが含まれている必要があります。ファイルフォーマットをチェックおよび編集して、各列のタイプが正しく設定されていることを確認します（テキスト、日付、整数など）。次に例を示します。

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 「**[!UICONTROL File to load]**」セクションで「**[!UICONTROL Upload a new file from the local machine]**」を選択し、フィールドを空白のままにします。 このテンプレートから新しいワークフローを作成するたびに、ここで、定義された構造に対応するファイルを指定できます。

      任意のオプションを使用できますが、それに応じてテンプレートを修正する必要があります。例えば、「**[!UICONTROL Use the file specified in the inbound transition]**」を選択した場合、FTP/SFTPサーバーからインポートするファイルを取得する前に、**[!UICONTROL Transfer file]**&#x200B;アクティビティを追加できます。

      インポート中に発生したエラーを含むファイルをユーザーがダウンロードできるようにするには、「**[!UICONTROL Keep the rejects in a file]**」オプションをオンにして、「**[!UICONTROL File name]**」を指定します。

      ![](assets/import_template_example1.png)

1. **[!UICONTROL Reconciliation]**&#x200B;アクティビティを設定します。 ここでのこのアクティビティの目的は、受信データを識別することです。

   * 「**[!UICONTROL Relations]**」タブで「**[!UICONTROL Create element]**」を選択し、インポートされたデータと受信者ターゲティングディメンションの間のリンクを定義します（[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照）。 この例では、結合条件の作成に **CRM ID** カスタムフィールドが使用されています。一意のレコードを識別できる限り、必要なフィールドまたはフィールドの組み合わせを使用します。
   * 「**[!UICONTROL Identification]**」タブで、「**[!UICONTROL Identify the document from the working data]**」オプションをオフのままにします。

   ![](assets/import_template_example2.png)

1. **[!UICONTROL Segmentation]**&#x200B;アクティビティを設定して、あるトランジションで紐付けされた受信者を取得し、2番目のトランジションで紐付けされていないが十分なデータを持っている受信者を取得します。

   紐付けされた受信者を含むトランジションは、データベースを更新するために使用できます。不明な受信者を含むトランジションは、ファイルで最小限の情報が利用できる場合、データベースに新しい受信者エントリを作成するために使用できます。

   紐付けできず、十分なデータを持たない受信者は、補集合アウトバウンドトランジションで選択され、別のファイルにエクスポートしたり、単純に無視したりできます。

   * アクティビティの「**[!UICONTROL General]**」タブで、「**[!UICONTROL Resource type]**」を「**[!UICONTROL Temporary resource]**」に設定し、ターゲットセットとして「**[!UICONTROL Reconciliation]**」を選択します。
   * 「**[!UICONTROL Advanced options]**」タブで、「**[!UICONTROL Generate complement]**」オプションをオンにして、データベースにレコードが挿入できないかどうかを確認できます。 必要に応じて、補完データのさらなる処理（ファイルエクスポート、リスト更新など）を適用できます。
   * 「 **[!UICONTROL Segments]** 」タブの最初のセグメントで、インバウンド母集団に対するフィルター条件を追加し、プロファイルのCRM IDが0に等しくないレコードのみを選択します。 この方法では、データベースのプロファイルと紐付けされたファイルのデータがそのサブセットで選択されます。

      ![](assets/import_template_example3.png)

   * データベースに挿入される十分なデータを持つ紐付けされていないレコードを選択する2番目のセグメントを追加します。 （例：E メールアドレス、姓名）。紐付けされていないレコードのプロファイルのCRM ID値が0に等しい。

      ![](assets/import_template_example3_2.png)

   * 最初の2つのサブセットで選択されていないすべてのレコードは、**[!UICONTROL Complement]**&#x200B;で選択されます。

1. 前に設定した&#x200B;**[!UICONTROL Segmentation]**&#x200B;アクティビティの最初のアウトバウンドトランジションの後にある&#x200B;**[!UICONTROL Update data]**&#x200B;アクティビティを設定します。

   * インバウンドトランジションには既にデータベースに存在する受信者のみが含まれるので、「**[!UICONTROL Update]**」を「**[!UICONTROL Operation type]**」と選択します。
   * 「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Using reconciliation criteria]**」を選択し、「**[!UICONTROL Dimension to update]** - Profiles （この例では）」と「**[!UICONTROL Reconciliation]**」アクティビティで作成したリンクの間のキーを定義します。 この例では、**CRM ID** カスタムフィールドが使用されています。

      ![](assets/import_template_example6.png)

   * 「**[!UICONTROL Fields to update]**」タブで、ファイルの対応する列の値で更新するプロファイルディメンションのフィールドを指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >これらのプロファイルにダイレクトメールを送信する場合は、ダイレクトメールプロバイダーにとって郵送先住所を必ず含めてください。 また、プロファイル情報の「**[!UICONTROL Address specified]**」ボックスがオンになっていることを確認します。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、**1**&#x200B;を&#x200B;**[!UICONTROL Source]**&#x200B;と指定して、`postalAddress/@addrDefined`フィールドを&#x200B;**[!UICONTROL Destination]**&#x200B;として選択します。 ダイレクトメールと&#x200B;**[!UICONTROL Address specified]**&#x200B;オプションの使用について詳しくは、[このドキュメント](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

1. 紐付けられていないプロファイルを含むトランジションの後にある「**[!UICONTROL Deduplication]**」アクティビティを設定します。

   * 「**[!UICONTROL Properties]**」タブで、**[!UICONTROL Resource type]**&#x200B;をワークフローの「**[!UICONTROL Reconciliation]**」アクティビティから生成された一時リソースに設定します。

      ![](assets/import_template_example4.png)

   * この例では、一意のプロファイルを見つけるために、E メールフィールドが使用されています。入力されていることがわかっており、一意の組み合わせを構成する任意のフィールドを使用できます。
   * **[!UICONTROL Deduplication method]**&#x200B;を選択します。 この場合、重複が発生した場合にどのレコードを保持するかは、アプリケーションによって自動的に決定されます。

   ![](assets/import_template_example7.png)

1. 前に設定した&#x200B;**[!UICONTROL Deduplication]**&#x200B;アクティビティの後にある&#x200B;**[!UICONTROL Update data]**&#x200B;アクティビティを設定します。

   * インバウンドトランジションにはデータベースに存在しないプロファイルのみが含まれるので、「 **[!UICONTROL Insert only]** 」を「 **[!UICONTROL Operation type]** 」と選択します。
   * 「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Using reconciliation criteria]**」を選択し、「**[!UICONTROL Dimension to update]** - Profiles （この例では）」と「**[!UICONTROL Reconciliation]**」アクティビティで作成したリンクの間のキーを定義します。 この例では、**CRM ID** カスタムフィールドが使用されています。

      ![](assets/import_template_example6.png)

   * 「**[!UICONTROL Fields to update]**」タブで、ファイルの対応する列の値で更新するプロファイルディメンションのフィールドを指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >これらのプロファイルにダイレクトメールを送信する場合は、ダイレクトメールプロバイダーにとって郵送先住所を必ず含めてください。 また、プロファイル情報の「**[!UICONTROL Address specified]**」ボックスがオンになっていることを確認します。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、**1**&#x200B;を&#x200B;**[!UICONTROL Source]**&#x200B;と指定して、**[postalAddress/@addrDefined]**&#x200B;フィールドを&#x200B;**[!UICONTROL Destination]**&#x200B;として選択します。 ダイレクトメールと&#x200B;**[!UICONTROL Address specified]**&#x200B;オプションの使用について詳しくは、[このドキュメント](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

1. **[!UICONTROL Segmentation]**&#x200B;アクティビティの3番目のトランジションの後に、データベースに挿入されないデータを追跡する場合は、**[!UICONTROL Extract file]**&#x200B;アクティビティと&#x200B;**[!UICONTROL Transfer file]**&#x200B;アクティビティを追加します。 これらのアクティビティを設定して、必要な列をエクスポートし、ファイルを取得可能な FTP または SFTP サーバーにファイルを転送します。
1. **[!UICONTROL End]**&#x200B;アクティビティを追加し、ワークフローテンプレートを保存します。

これで、テンプレートが使用できるようになり、すべての新規ワークフローに利用できます。必要な操作は、**[!UICONTROL Load file]**&#x200B;アクティビティにインポートするデータを含むファイルを指定することです。

![](assets/import_template_example9.png)
