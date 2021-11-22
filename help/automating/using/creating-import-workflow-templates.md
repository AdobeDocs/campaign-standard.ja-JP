---
title: データをインポートするワークフローテンプレートの作成
description: データをインポートするためのワークフローテンプレートを作成する方法を説明します。
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

1. 新しいワークフローテンプレートの作成元 **[!UICONTROL Resources > Templates > Workflow templates]**.
1. 次のアクティビティを追加します。

   * **[!UICONTROL Load file]**:インポートするデータを含むファイルに求められる構造を定義します。

      >[!NOTE]
      >
      >1 つのファイルからのみデータをインポートできます。 ワークフローに複数の **[!UICONTROL Load file]** アクティビティの場合は、毎回同じファイルが使用されます。

   * **[!UICONTROL Reconciliation]**:インポートしたデータをデータベースのデータに紐付けします。
   * **[!UICONTROL Segmentation]**:フィルターを作成して、紐付けできたかどうかに応じて別々にレコードを処理します。
   * **[!UICONTROL Deduplication]**:データベースに挿入される前に、受信ファイルのデータを重複排除します。
   * **[!UICONTROL Update data]**:データベースをインポートされたプロファイルで更新します。

   ![](assets/import_template_example0.png)

1. の設定 **[!UICONTROL Load file]** アクティビティ：

   * サンプルファイルをアップロードすることで、求められる構造を定義します。サンプルファイルには、インポートに必要なすべての列と、いくつかの行のみが含まれている必要があります。ファイルフォーマットをチェックおよび編集して、各列のタイプが正しく設定されていることを確認します（テキスト、日付、整数など）。次に例を示します。

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 内 **[!UICONTROL File to load]** セクション、選択 **[!UICONTROL Upload a new file from the local machine]** 「 」フィールドは空白のままにします。 このテンプレートから新しいワークフローを作成するたびに、ここで、定義された構造に対応するファイルを指定できます。

      任意のオプションを使用できますが、それに応じてテンプレートを修正する必要があります。例えば、 **[!UICONTROL Use the file specified in the inbound transition]**&#x200B;に値を入力する場合、 **[!UICONTROL Transfer file]** アクティビティを確認してください。

      インポート中に発生したエラーを含むファイルをユーザーがダウンロードできるようにするには、 **[!UICONTROL Keep the rejects in a file]** オプションを選択し、 **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. の設定 **[!UICONTROL Reconciliation]** アクティビティ。 ここでのこのアクティビティの目的は、受信データを識別することです。

   * 内 **[!UICONTROL Relations]** タブ、選択 **[!UICONTROL Create element]** およびは、インポートされたデータと受信者ターゲティングディメンションの間のリンクを定義します ( [ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)) をクリックします。 この例では、結合条件の作成に **CRM ID** カスタムフィールドが使用されています。一意のレコードを識別できる限り、必要なフィールドまたはフィールドの組み合わせを使用します。
   * 内 **[!UICONTROL Identification]** タブを閉じ、 **[!UICONTROL Identify the document from the working data]** オプションがオフになっている。

   ![](assets/import_template_example2.png)

1. の設定 **[!UICONTROL Segmentation]** 「 」アクティビティ：あるトランジションで紐付けされた受信者を取得し、2 番目のトランジションで紐付けされていないが十分なデータを持っている受信者を取得します。

   紐付けされた受信者を含むトランジションは、データベースを更新するために使用できます。不明な受信者を含むトランジションは、ファイルで最小限の情報が利用できる場合、データベースに新しい受信者エントリを作成するために使用できます。

   紐付けできず、十分なデータを持たない受信者は、補集合アウトバウンドトランジションで選択され、別のファイルにエクスポートしたり、単純に無視したりできます。

   * 内 **[!UICONTROL General]** アクティビティの「 」タブで、 **[!UICONTROL Resource type]** から **[!UICONTROL Temporary resource]** を選択し、 **[!UICONTROL Reconciliation]** をターゲットセットとして設定します。
   * 内 **[!UICONTROL Advanced options]** タブで、 **[!UICONTROL Generate complement]** データベースにレコードを挿入できないかどうかを確認できるオプションです。 必要に応じて、補完データのさらなる処理（ファイルエクスポート、リスト更新など）を適用できます。
   * の最初のセグメント **[!UICONTROL Segments]** 「 」タブで、インバウンド母集団に対するフィルター条件を追加して、プロファイルの CRM ID が 0 に等しくないレコードのみを選択します。 この方法では、データベースのプロファイルと紐付けされたファイルのデータがそのサブセットで選択されます。

      ![](assets/import_template_example3.png)

   * データベースに挿入される十分なデータを持つ紐付けられていないレコードを選択する 2 番目のセグメントを追加します。 （例：E メールアドレス、姓名）。紐付けされていないレコードのプロファイルの CRM ID の値が 0 に等しい。

      ![](assets/import_template_example3_2.png)

   * 最初の 2 つのサブセットで選択されていないすべてのレコードは、 **[!UICONTROL Complement]**.

1. の設定 **[!UICONTROL Update data]** アクティビティ **[!UICONTROL Segmentation]** アクティビティが以前に設定されました。

   * 選択 **[!UICONTROL Update]** as **[!UICONTROL Operation type]** インバウンドトランジションのみに、データベースに既に存在する受信者が含まれるので、
   * 内 **[!UICONTROL Identification]** タブ、選択 **[!UICONTROL Using reconciliation criteria]** と、 **[!UICONTROL Dimension to update]**  — この例のプロファイル — および **[!UICONTROL Reconciliation]** アクティビティ。 この例では、**CRM ID** カスタムフィールドが使用されています。

      ![](assets/import_template_example6.png)

   * 内 **[!UICONTROL Fields to update]** 「 」タブに移動し、ファイルの対応する列の値で更新する Profiles ディメンションのフィールドを指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >これらのプロファイルにダイレクトメールを送信する予定がある場合は、郵送先住所を必ず含めてください。この情報は、ダイレクトメールプロバイダーにとって重要です。 また、 **[!UICONTROL Address specified]** 」ボックスがオンになっている。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、 **1** as **[!UICONTROL Source]** をクリックし、 `postalAddress/@addrDefined` ～としてのフィールド **[!UICONTROL Destination]**. ダイレクトメールの詳細と **[!UICONTROL Address specified]** オプション： [このドキュメント](../../channels/using/about-direct-mail.md#recommendations).

1. の設定 **[!UICONTROL Deduplication]** 紐付けされていないプロファイルを含むトランジションの後にある「 」アクティビティ：

   * 内 **[!UICONTROL Properties]** タブ、 **[!UICONTROL Resource type]** から生成された一時的なリソースに **[!UICONTROL Reconciliation]** ワークフローの「 」アクティビティ。

      ![](assets/import_template_example4.png)

   * この例では、一意のプロファイルを見つけるために、E メールフィールドが使用されています。入力されていることがわかっており、一意の組み合わせを構成する任意のフィールドを使用できます。
   * を選択します。 **[!UICONTROL Deduplication method]**. この場合、重複が発生した場合にどのレコードを保持するかは、アプリケーションによって自動的に決定されます。

   ![](assets/import_template_example7.png)

1. の設定 **[!UICONTROL Update data]** 次の場所にあるアクティビティ **[!UICONTROL Deduplication]** アクティビティが以前に設定されました。

   * 選択 **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** インバウンドトランジションには、データベースに存在しないプロファイルのみが含まれるので、
   * 内 **[!UICONTROL Identification]** タブ、選択 **[!UICONTROL Using reconciliation criteria]** と、 **[!UICONTROL Dimension to update]**  — この例のプロファイル — および **[!UICONTROL Reconciliation]** アクティビティ。 この例では、**CRM ID** カスタムフィールドが使用されています。

      ![](assets/import_template_example6.png)

   * 内 **[!UICONTROL Fields to update]** 「 」タブに移動し、ファイルの対応する列の値で更新する Profiles ディメンションのフィールドを指定します。 ファイル列の名前が受信者ディメンションフィールドの名前と同一またはほとんど同じ場合、自動選択ボタンを使用して、異なるフィールドを自動的に一致させることができます。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >これらのプロファイルにダイレクトメールを送信する予定がある場合は、郵送先住所を必ず含めてください。この情報は、ダイレクトメールプロバイダーにとって重要です。 また、 **[!UICONTROL Address specified]** 」ボックスがオンになっている。 ワークフローからこのオプションを更新するには、更新するフィールドに要素を追加し、 **1** as **[!UICONTROL Source]** をクリックし、 **[postalAddress/@addrDefined]** ～としてのフィールド **[!UICONTROL Destination]**. ダイレクトメールの詳細と **[!UICONTROL Address specified]** オプション： [このドキュメント](../../channels/using/about-direct-mail.md#recommendations).

1. 3 番目の **[!UICONTROL Segmentation]** アクティビティを追加する **[!UICONTROL Extract file]** アクティビティと **[!UICONTROL Transfer file]** データベースに挿入されていないデータを追跡する場合は、「 」アクティビティを選択します。 これらのアクティビティを設定して、必要な列をエクスポートし、ファイルを取得可能な FTP または SFTP サーバーにファイルを転送します。
1. を追加します。 **[!UICONTROL End]** 「 」アクティビティを開き、ワークフローテンプレートを保存します。

これで、テンプレートが使用できるようになり、すべての新規ワークフローに利用できます。必要な操作は、次に、 **[!UICONTROL Load file]** アクティビティ。

![](assets/import_template_example9.png)
