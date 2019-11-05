---
title: パッケージの管理
description: 管理者は、構造化XMLファイルを使用して、様々なAdobe Campaignインスタンス間でリソースを交換するパッケージを定義できます。
page-status-flag: 非活性化の
uuid: d041f549-bfc5-4e6b-87bf-a63c7c224bca
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データのインポート/エクスポート
discoiquuid: c3015cdc-8432-4e57-8ac0-43ae7827e3b0
context-tags: packageDef,overview;packageInstall,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# パッケージの管理{#managing-packages}

管理者は、構造化XMLファイルを使用して、様々なAdobe Campaignインスタンス間でリソースを交換するパッケージを定義できます。 設定パラメーターやデータを指定できます。

これは、あるサーバから別のサーバにデータを転送したり、インスタンスの設定を複製する場合に役立ちます。

パッケージは、//メニュ **[!UICONTROL Administration]** ーか **[!UICONTROL Deployment]** ら入手 **[!UICONTROL Package exports]** でき **[!UICONTROL Package imports]** ます。 2つのメニューも同様に機能します。

各リストの要素は、変更日やインストール日に従って、デフォルトで最新から最新の順に表示されます。

![](assets/packages_1.png)

要素のコンテンツを表示および変更するには、そのラベルをクリックします。 「パッケージの書き出し [」および「パッケージの読み込み](#exporting-a-package) 」の [項を参照してください](#importing-a-package) 。

## パッケージのエクスポート {#package-exports}

### 標準パッケージ {#standard-packages}

**[!UICONTROL Platform]** とは2つ **[!UICONTROL Administration]** の組み込みパッケージで、それぞれに、書き出すリソースの事前定義済みのリストが含まれています。 読み取り専用モードで開くことができ、書き出しにのみ適しています。

![](assets/packages_14.png)

>[!CAUTION]
>
>書き出したリソースにデフォルトのIDが含まれている場合、パッケージの書き出しは許可されません。 したがって、書き出し可能なリソースのIDは、Adobe Campaign Standardで標準として提供されているテンプレートとは異なる名前を使用して変更する必要があります。 例えば、テストプロファイルをエクスポートする場合、値「SDM」または「sdm」を含むIDは使用できません。 デフォルトのIDを含むパッケージを書き出そうとすると、次のようなエラーが表示されます。"'ブランド（ブランド）'エンティティタイプは、パッケージのインポート時に競合が発生する可能性のあるデフォルトのID ('BRD1')を使用します。 この名前を変更し、操作を繰り返します。」

パッケージの書き出し手順は、「パッケージの書き出し [」の節で説明します](#exporting-a-package) 。

* パッケージ **[!UICONTROL Platform]** は、技術的な設定時に追加されたすべてのリソースを再グループ化します。カスタムリソース、カスタムリソースセット、トリガー、およびアプリケーションオプションを、タイプと共に使 **[!UICONTROL System]** 用できます。
* パッケー **[!UICONTROL Administration]** ジは、ビジネス設定時に追加された以下のオブジェクトをすべて再グループ化します。キャンペーンテンプレート、コンテンツテンプレート、配信テンプレート、ランディングページテンプレート、プログラムテンプレートおよびワークフローテンプレート。

   また、次のオブジェクトも含まれます。コンテンツブロック、ターゲットマッピング、外部アカウント、組織単位、タイプ、役割、タイポロジ、タ **[!UICONTROL User]** イポロジルールおよびユーザーを含むアプリケーションオプション。

>[!NOTE]
>
>この2つのパッケージの内容は変更できません。 これに対し、これらのパッケージには常に最新のデータが含まれています。 独自のパッケ [ージを作成して、特定の要素を書き出す](#creating-a-package) ことができます。

### パッケージの作成 {#creating-a-package}

特定のデータセットを書き出す必要がある場合は、パッケージを作成する必要があります。

パッケージを作成するには、管理権限が必要です。

1. //か **[!UICONTROL Administration]** ら、パッケ **[!UICONTROL Deployment]** ージのコンテン **[!UICONTROL Package exports]****[!UICONTROL Create]** ツのリストにあるボタンをクリックします。

   要素が直ちに作成されます。 作成をキャンセルするには、リストに戻り、削除する対応するボックスをオンにします。

1. パッケージコンテンツ画面で、名前とIDを指定します。
1. 説明を追加 **[!UICONTROL Edit properties]** し、特定のユーザーにアクセスを制限する場合は、このボタンをクリックします。

   ![](assets/packages_18.png)

1. タブのボ **[!UICONTROL Create element]** タンを使用し **[!UICONTROL Export content]** て、書き出すリソースを選択します。

   ![](assets/packages_2.png)

1. リソースはアルファベット順に表示され、名前でフィルタリングできます。 技術名は角括弧で囲まれて表示されます。 リストから要素を選択し、確認します。

   ![](assets/packages_3.png)

1. リソース名がタブに表示され **[!UICONTROL Export content]** ます。 リソースを変更するには、対応するボックスを選択し、ボタンを使用 **[!UICONTROL Show detail of the element selected]** します。

   ![](assets/packages_4.png)

1. クエリーエディターを使用すると、エクスポートする要素をフィルタリングできます。 For more on this, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >リソースあたり最大5,000個のオブジェクトを書き出すことができます。

1. 書き出すすべてのリソースを指定したら、選択内容を保存します。

パッケージが作成され、書き出しの準備が整いました。

### パッケージの書き出し {#exporting-a-package}

パッケージを書き出すと、リソースの特定の状態を保存し、同じインスタンス上の別のインスタンスまたは後で再読み込みできるようになります。

>[!CAUTION]
>
>書き出したリソースにあらかじめ用意されているIDが含まれている場合、パッケージの書き出しは許可されません。 したがって、書き出し可能なリソースのIDは、Adobe Campaign Standardで標準として提供されているテンプレートとは異なる名前を使用して変更する必要があります。 例えば、テストプロファイルをエクスポートする場合、値「SDM」または「sdm」を含むIDは使用できません。

1. /から **[!UICONTROL Administration]** 詳細にア **[!UICONTROL Deployment]** クセス **[!UICONTROL Package exports]**&#x200B;するパッケージを選択します。
1. 必要なデータがパッケージに含まれていることを確認します。
1. Click the **[!UICONTROL Start export]** button.

書き出したファイルは、使用中のブラウザのダウンロードフォルダに保存されます。 この名前は自動的に「package_xxx.xml」という名前になり、「xxx」はパッケージIDに対応します。

操作が完了すると、次のセクションが表示されます。

* **[!UICONTROL Export status]**:この節では、操作が正しく実行されたかどうかを示します。

   ![](assets/packages_6.png)

* タブを使用して、エクスポートの異なる手順を確認で **[!UICONTROL Log]** きます。 以前のすべてのエクスポートのステータスが含まれます。

   ![](assets/packages_7.png)

>[!NOTE]
>
>既に書き出されているパッケージコンテンツリストから要素を選択する場合、タブとタブ **[!UICONTROL Log]** は引き **[!UICONTROL Last export]** 続き使用できます。

## パッケージインポート {#package-imports}

### システムの更新 {#system-updates}

上記のパッケージの読み込みリストには、アドビが実行したアップデートにリンクされた自動読み込みが含まれています。

![](assets/packages_15.png)

このタ **[!UICONTROL Execution logs]** ブには、すべての読み込み手順が格納されます。 サイドパネルには、一般情報が表示されます。

![](assets/packages_11.png)

>[!NOTE]
>
>これらの要素は読み取り専用モードでアクセスできます。

### パッケージの読み込み {#importing-a-package}

管理者は、Adobe Campaignインスタンスの以前に実行したエクスポートから作成されたパッケージを手動でインポートできます。 For more on this, refer to the [Package exports](#package-exports) section.

手動パッケージのインポートは、次の2つの手順で構成されます。まず、ファイルをアップロードし、その内容を読み込む必要があります。

1. //か **[!UICONTROL Administration]** ら、パッケ **[!UICONTROL Deployment]** ージの **[!UICONTROL Package imports]**&#x200B;読み込みリス **[!UICONTROL Create]** トのボタンをクリックします。

   要素が直ちに作成されます。 作成をキャンセルするには、リストに戻り、削除する対応するボックスをオンにします。

1. 新しいインポートの名前とIDを指定します。
1. アップロードするファイルをドラッグ&amp;ドロップするか、リンクをクリックして選択 **[!UICONTROL Select from folder]** します。

   読み込むファイルは、XMLまたはZIP（XMLファイルを含む）形式である必要があります。

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >アップロードしたドキュメントを置き換えるには、まず名前の右側にあるXアイコンを使用してファイルを削除し、操作を繰り返します。

1. ファイルがアップロードされたら、ボタンを使用してその内容をデータベースに読み込 **[!UICONTROL Start import]** みます。

   ![](assets/packages_19.png)

操作が完了すると、次のセクションが表示されます。

* **[!UICONTROL Import status]**:この節では、操作が正しく実行されたかどうかを示します。
* タブを使用して、読み込みの異なる手順を確認でき **[!UICONTROL Execution logs]** ます。 これは、エラーを表示する際に特に重要です。

   ![](assets/packages_20.png)

パッケージを読み込むと、同じ要素から再読み込みすることはできません。 変更できるのは、そのラベルとIDのみです。

同じパッケージを再度読み込むには、パッケージの読み込みリストに戻り、要素を作成してから、選択したファイルを再度アップロードする必要があります。
