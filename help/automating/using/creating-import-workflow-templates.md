---
title: データをインポートするワークフローテンプレートの作成
description: ワークフローテンプレートを作成してデータを読み込む方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 37%

---

# データをインポートするワークフローテンプレートの作成 {#import-workflow-template}

同じ構造のファイルを頻繁にインポートする必要がある場合、インポートテンプレートを使用することをお勧めします。

この例では、Adobe Campaign データベースの CRM からのプロファイルのインポートに再利用できるワークフローを事前設定する方法を示します。

1. **[!UICONTROL Resources > Templates > Workflow templates]** から新しいワークフローテンプレートを作成します。
1. 次のアクティビティを追加します。

   * **[!UICONTROL Load file]**：読み込むデータを含むファイルの期待される構造を定義します。

     >[!NOTE]
     >
     >単一のファイルからのみデータをインポートできます。 ワークフローに複数の **[!UICONTROL Load file]** アクティビティがある場合は、毎回同じファイルが使用されます。

   * **[!UICONTROL Reconciliation]**：読み込んだデータをデータベースデータと紐付けます。
   * **[!UICONTROL Segmentation]**：レコードを紐付けできるかどうかに応じてレコードの処理が異なるフィルターを作成します。
   * **[!UICONTROL Deduplication]**: データをデータベースに挿入する前に、受信ファイルからデータの重複を排除します。
   * **[!UICONTROL Update data]**: インポートされたプロファイルでデータベースを更新します。

   ![](assets/import_template_example0.png)

1. **[!UICONTROL Load file]** アクティビティを設定します。

   * サンプルファイルをアップロードすることで、求められる構造を定義します。サンプルファイルには、インポートに必要なすべての列と、いくつかの行のみが含まれている必要があります。ファイルフォーマットをチェックおよび編集して、各列のタイプが正しく設定されていることを確認します（テキスト、日付、整数など）。次に例を示します。

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * 「**[!UICONTROL File to load]**」セクションで「**[!UICONTROL Upload a new file from the local machine]**」を選択し、フィールドは空白のままにします。 このテンプレートから新しいワークフローを作成するたびに、ここで、定義された構造に対応するファイルを指定できます。

     任意のオプションを使用できますが、それに応じてテンプレートを修正する必要があります。例えば、「**[!UICONTROL Use the file specified in the inbound transition]**」を選択した場合は、の前に **[!UICONTROL Transfer file]** アクティビティを追加して、インポートするファイルを FTP/SFTP サーバーから取得できます。

     読み込み時に発生したエラーを含むファイルをユーザーがダウンロードできるようにする場合は、「**[!UICONTROL Keep the rejects in a file]**」オプションをオンにして、**[!UICONTROL File name]** を指定します。

     ![](assets/import_template_example1.png)

1. **[!UICONTROL Reconciliation]** アクティビティを設定します。 ここでのこのアクティビティの目的は、受信データを識別することです。

   * 「**[!UICONTROL Relations]**」タブで「**[!UICONTROL Create element]**」を選択し、読み込んだデータと受信者ターゲティングディメンションの間のリンクを定義します（[ ターゲティングディメンションとリソース ](../../automating/using/query.md#targeting-dimensions-and-resources) を参照）。 この例では、結合条件の作成に **CRM ID** カスタムフィールドが使用されています。一意のレコードを識別できる限り、必要なフィールドまたはフィールドの組み合わせを使用します。
   * 「**[!UICONTROL Identification]**」タブで、「**[!UICONTROL Identify the document from the working data]**」オプションをオフのままにします。

   ![](assets/import_template_example2.png)

1. **[!UICONTROL Segmentation]** アクティビティを設定して、1 つのトランジションで紐付けされた受信者と、紐付けはできなかったが、2 つ目のトランジションで十分なデータがある受信者を取得します。

   紐付けされた受信者を含むトランジションは、データベースを更新するために使用できます。不明な受信者を含むトランジションは、ファイルで最小限の情報が利用できる場合、データベースに新しい受信者エントリを作成するために使用できます。

   紐付けできず、十分なデータを持たない受信者は、補集合アウトバウンドトランジションで選択され、別のファイルにエクスポートしたり、単純に無視したりできます。

   * アクティビティの「**[!UICONTROL General]**」タブで、**[!UICONTROL Resource type]** を **[!UICONTROL Temporary resource]** に設定し、ターゲットセットとして **[!UICONTROL Reconciliation]** を選択します。
   * 「**[!UICONTROL Advanced options]**」タブで「**[!UICONTROL Generate complement]**」オプションをチェックすると、データベースに挿入できないレコードがあるかどうかを確認できます。 必要に応じて、補完データのさらなる処理（ファイルエクスポート、リスト更新など）を適用できます。
   * 「**[!UICONTROL Segments]**」タブの最初のセグメントで、インバウンド母集団にフィルター条件を追加して、プロファイルの CRM ID が 0 に等しくないレコードのみを選択します。 この方法で、データベースのプロファイルと紐付けされたファイルのデータが、そのサブセットで選択されます。

     ![](assets/import_template_example3.png)

   * データベースに挿入するのに十分なデータがある紐付けられていないレコードを選択する 2 つ目のセグメントを追加します。 例：メールアドレス、名、姓。 紐付けされていないレコードのプロファイルの CRM ID 値は 0 になります。

     ![](assets/import_template_example3_2.png)

   * 最初の 2 つのサブセットで選択されていないすべてのレコードが **[!UICONTROL Complement]** で選択されます。

1. 前に設定した **[!UICONTROL Update data]** アクティビティの最初のアウトバウンドトランジションの後にある **[!UICONTROL Segmentation]** アクティビティを設定します。

   * インバウンドトランジションにはデータベースに既に存在する受信者のみが含まれるので、**[!UICONTROL Update]** として **[!UICONTROL Operation type]** を選択します。
   * 「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Using reconciliation criteria]**」を選択し、**[!UICONTROL Dimension to update]** （この場合はプロファイル）と **[!UICONTROL Reconciliation]** アクティビティで作成されたリンクの間のキーを定義します。 この例では、**CRM ID** カスタムフィールドが使用されています。

     ![](assets/import_template_example6.png)

   * 「**[!UICONTROL Fields to update]**」タブで、更新するプロファイル ディメンションのフィールドを、ファイルの対応する列の値で指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >これらのプロファイルにダイレクトメールを送信する予定がある場合は、住所を必ず含めてください。この情報は、ダイレクトメールプロバイダーにとって不可欠です。 また、プロファイルの情報の「**[!UICONTROL Address specified]**」チェックボックスがオンになっていることも確認します。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、**として** 1 **[!UICONTROL Source]** を指定し、`postalAddress/@addrDefined` として **[!UICONTROL Destination]** フィールドを選択します。 ダイレクトメールと **[!UICONTROL Address specified]** オプションの使用について詳しくは、[ このドキュメント ](../../channels/using/about-direct-mail.md#recommendations) を参照してください。

1. 紐付けられていないプロファイルを含むトランジションの後の **[!UICONTROL Deduplication]** アクティビティを設定します。

   * 「**[!UICONTROL Properties]**」タブで、**[!UICONTROL Resource type]** を、ワークフローの **[!UICONTROL Reconciliation]** アクティビティから生成された一時リソースに設定します。

     ![](assets/import_template_example4.png)

   * この例では、一意のプロファイルを見つけるために、メールフィールドが使用されています。入力されていることがわかっており、一意の組み合わせを構成する任意のフィールドを使用できます。
   * **[!UICONTROL Deduplication method]** を選択してください。 この場合、重複が発生した場合に保持するレコードはアプリケーションによって自動的に決定されます。

   ![](assets/import_template_example7.png)

1. 前に設定した **[!UICONTROL Update data]** アクティビティの後にある **[!UICONTROL Deduplication]** アクティビティを設定します。

   * インバウンドトランジションにはデータベースに存在しないプロファイルのみが含まれるので、**[!UICONTROL Insert only]** として **[!UICONTROL Operation type]** を選択します。
   * 「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Using reconciliation criteria]**」を選択し、**[!UICONTROL Dimension to update]** （この場合はプロファイル）と **[!UICONTROL Reconciliation]** アクティビティで作成されたリンクの間のキーを定義します。 この例では、**CRM ID** カスタムフィールドが使用されています。

     ![](assets/import_template_example6.png)

   * 「**[!UICONTROL Fields to update]**」タブで、更新するプロファイル ディメンションのフィールドを、ファイルの対応する列の値で指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >これらのプロファイルにダイレクトメールを送信する予定がある場合は、住所を必ず含めてください。この情報は、ダイレクトメールプロバイダーにとって不可欠です。 また、プロファイルの情報の「**[!UICONTROL Address specified]**」チェックボックスがオンになっていることも確認します。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、**として** 1 **[!UICONTROL Source]** を指定し、**[として]** postalAddress/@addrDefined **[!UICONTROL Destination]** フィールドを選択します。 ダイレクトメールと **[!UICONTROL Address specified]** オプションの使用について詳しくは、[ このドキュメント ](../../channels/using/about-direct-mail.md#recommendations) を参照してください。

1. **[!UICONTROL Segmentation]** アクティビティの 3 番目のトランジションの後、データベースに挿入されていないデータを追跡する場合は、**[!UICONTROL Extract file]** アクティビティと **[!UICONTROL Transfer file]** アクティビティを追加します。 これらのアクティビティを設定して、必要な列をエクスポートし、ファイルを取得可能な FTP または SFTP サーバーにファイルを転送します。
1. **[!UICONTROL End]** アクティビティを追加し、ワークフローテンプレートを保存します。

これで、テンプレートが使用できるようになり、すべての新規ワークフローに利用できます。その後、**[!UICONTROL Load file]** アクティビティに読み込むデータを含んだファイルを指定するだけで済みます。

![](assets/import_template_example9.png)
