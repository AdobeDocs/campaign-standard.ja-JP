---
solution: Campaign Standard
product: campaign
title: ターゲットプロファイルを使用した E メールメッセージのテスト
description: 対象を絞ったプロファイルと置換アドレスを使用してメッセージをテストする方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: コントロール母集団
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 5%

---


# ターゲットプロファイルを使用した E メールメッセージのテスト {#testing-message-profiles}

## 概要 {#overview}

[テストプロファイル](../../audiences/using/managing-test-profiles.md)に加えて、自分をターゲットプロファイルの1つの位置に置くことで、電子メールメッセージをテストできます。 これにより、プロファイルが受け取るメッセージ(カスタムフィールド、動的な情報、パーソナライズされた情報、ワークフローからの追加データなど)を正確に表示できます。

>[!NOTE]
>
> この機能は、電子メールメッセージでのみ使用できます。

主な手順は次のとおりです。

1. メッセージを設定し、**準備**&#x200B;フェーズを起動します。
1. **メッセージの対象となるプロファイルの中から1つまたは複数の** profileを選択します。
1. 各プロファイルに、配達確認の送信先の&#x200B;**置換アドレス**&#x200B;を関連付けます。
1. （オプション）各プロファイルに対して、配達確認の件名行に追加する&#x200B;**プレフィックス**&#x200B;を定義します。
1. **電子メールデザイナで、プロファイルに対してメッセージがどのように表示されるかを** プレビューします。
1. 配達確認を送信します。

>[!IMPORTANT]
>
>この機能を使用すると、プロファイルの個人情報を外部の E メールアドレスに送信できます。Campaign Standard でプライバシーリクエスト（GDPR および CCPA）を実行しても、リクエストは外部で実行されないことに注意してください。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

## プロファイルと置換アドレスの選択{#selecting-profiles}

ターゲットプロファイルをテストに使用するには、まず選択してから、配達確認を受け取る置換アドレスを定義する必要があります。 これを行うには、[ターゲットプロファイルの中から特定のプロファイル](#selecting-individual-profiles)を選択するか、[既存のオーディエンス](#importing-from-audience)からプロファイルを読み込みます。

>[!NOTE]
>
>テストするプロファイルは最大100個まで選択できます。

### 個々のプロファイルの選択{#selecting-individual-profiles}

1. メッセージダッシュボードで、メッセージの準備が成功したことを確認し、**[!UICONTROL Audience]**&#x200B;ブロックをクリックします。

   ![](assets/substitution_preparation.png)

1. 「**[!UICONTROL Profile substitutions]**」タブで、「**[!UICONTROL Create element]**」ボタンをクリックして、テストに使用するプロファイルを選択します。

   ![](assets/substitution_tab.png)

1. プロファイル選択ボタンをクリックして、メッセージの対象となるプロファイルのリストを表示します。

   ![](assets/substitution_recipient_selection.png)

1. テストに使用するプロファイルを選択し、**[!UICONTROL Address]**&#x200B;フィールドに目的の置換アドレスを入力して、**[!UICONTROL Confirm]**&#x200B;をクリックします。 プロファイルをターゲットにするすべての配達確認が、このプロファイルのデータベースで定義されているアドレスではなく、この電子メールアドレスに送信されます。

   配達確認の件名行に特定のプレフィックスを追加する場合は、**[!UICONTROL Subject line prefix]**&#x200B;フィールドに入力します。

   >[!NOTE]
   >
   >件名行のプレフィックスは500文字まで含めることができます。

   ![](assets/substitution_address.png)

   プレフィックスは次のように表示されます。

   ![](assets/substitution_prefixsample.png)

1. プロファイルは、関連する置換アドレスとプレフィックスと共にリストに追加されます。 テストに使用するすべてのプロファイルに対して上記の手順を繰り返し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/substitution_recipients_confirm.png)

   同じプロファイルに対して複数の置換アドレスに配達確認を送信する場合は、このプロファイルを必要な回数だけ追加する必要があります。

   次の例では、プロファイルJohn Smithに基づく配達確認が、2つの異なる代替アドレスに送信されます。

   ![](assets/substitution_multiple_addresses.png)

1. すべてのプロファイルと置換アドレスが定義されたら、配達確認を送信してメッセージをテストできます。 これを行うには、**[!UICONTROL Test]**&#x200B;ボタンをクリックし、実行するテストのタイプを選択します。

   メッセージターゲットにテストプロファイルが追加されていない場合、**[!UICONTROL Email rendering]**&#x200B;と&#x200B;**[!UICONTROL Proof + Email rendering]**&#x200B;は使用できないことに注意してください。  送信する配達確認の詳細については、[この](../../sending/using/sending-proofs.md)を参照してください。

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>メッセージに変更を加えた場合は、必ずメッセージの準備を再度起動してください。 そうしないと、変更は配達確認に反映されません。

### オーディエンス{#importing-from-audience}からのプロファイルのインポート

Campaign Standardを使用すると、テストに使用できるプロファイルのオーディエンスを読み込むことができます。 これにより、例えば、異なるプロファイルをターゲットとする一連のメッセージを一意の電子メールアドレスに送信できます。

また、オーディエンスが既にアドレス列とプレフィックス列を使用して設定されている場合は、**[!UICONTROL Profile substitutions]**&#x200B;タブでこれらの情報をインポートできます。 置換アドレスを含むオーディエンスインポートの例については、[このセクション](#use-case)を参照してください。

>[!NOTE]
>
>オーディエンスを読み込むと、メッセージターゲットに対応するプロファイルのみが選択され、**[!UICONTROL Profile substitutions]**&#x200B;タブに追加されます。

オーディエンスからテストに使用するプロファイルを読み込むには、次の手順に従います。

1. メッセージダッシュボードで、メッセージの準備が成功したことを確認し、**[!UICONTROL Audience]**&#x200B;ブロックをクリックします。

   ![](assets/substitution_preparation.png)

1. 「**[!UICONTROL Profile substitutions]**」タブで、「**[!UICONTROL Import from an audience]**」をクリックします。

   ![](assets/substitution_audience_import.png)

1. 使用するオーディエンスを選択し、オーディエンスに送信する配達確認に使用する置換アドレスと接頭辞を入力します。

   >[!NOTE]
   >
   >件名行のプレフィックスは500文字まで含めることができます。

   ![](assets/substitution_audience_define.png)

   使用する置換アドレスや接頭辞が既にオーディエンスで定義されている場合は、**[!UICONTROL From Audience]**&#x200B;オプションを選択し、これらの情報の取得に使用する列を指定します。

   ![](assets/substitution_fromaudience.png)

1. 「**[!UICONTROL Import]**」ボタンをクリックします。メッセージターゲットに対応するオーディエンスのプロファイルが&#x200B;**[!UICONTROL Profile substitution]**&#x200B;タブに追加され、関連する置換アドレスと接頭辞が追加されます。

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>同じオーディエンスを再度読み込むと、別の置換アドレスや接頭辞を持つプロファイルは、以前の読み込みのに加えてリストに追加されます。

## ターゲットプロファイルを含むメッセージのプレビュー

>[!NOTE]
>
>プレビューは、電子メールデザイナでのみ使用できます。

ターゲットプロファイルを使用してプレビューを行うには、これらのプロファイルを&#x200B;**[!UICONTROL Profile substitution]**&#x200B;リストに追加しておく必要があります([プロファイルと置換アドレスの定義](#selecting-profiles)を参照)。

メッセージ内でパーソナライゼーションフィールドを使用する場合は、**メッセージの準備を開始する前に**&#x200B;追加する必要があります。 そうしないと、プレビューでは考慮されません。 その結果、パーソナライゼーションフィールドに変更が加えられた場合は、必ずメッセージの準備を再度起動してください。

プロファイルの置換を使用してプレビュー・メッセージを作成するには、次の手順に従います。

1. メッセージダッシュボードで、コンテンツのスナップショットをクリックして、電子メールデザイナーでメッセージを開きます。

   ![](assets/substitution_preview_access.png)

1. 「**[!UICONTROL Preview]**」タブを選択し、「**[!UICONTROL Change profile]**」をクリックします。

   ![](assets/substitution_preview_changeprofile.png)

1. 「**[!UICONTROL Profile Substitution]**」タブをクリックして、テスト用に追加された置換プロファイルを表示します。

   プレビューに使用するプロファイルを選択し、**[!UICONTROL Select]**&#x200B;をクリックします。

   ![](assets/substitution_preview_selection.png)

1. メッセージのプレビューが表示されます。 矢印を使用して、選択したプロファイル間を移動します。

   ![](assets/substitution_preview.png)

## 使用例 {#use-case}

この使用事例では、特定のプロファイルに対してパーソナライズされた電子メールニュースレターを送信する必要があります。 ニュースレターを送信する前に、対象プロファイルの一部を使用してプレビューを行い、外部ファイルで定義された内部電子メールアドレスに配達確認を送信します。

この使用例の主な手順は次のとおりです。

1. テストに使用するオーディエンスを作成します。
1. ターゲットプロファイルにワークフローを構築し、ニュースレターを送信します。
1. メッセージの代替プロファイルを設定します。
1. ターゲットプロファイルを使用してプレビューを行います。
1. 配達確認の送信

### 手順1:テストに使用するオーディエンスの作成

1. 読み込むファイルを準備し、オーディエンスを作成します。 この場合、配達確認に使用する置換アドレスと、配達確認の件名行に追加するプレフィックスを含める必要があります。

   この例では、「oliver.vaughan@internal.com」電子メールアドレスに、「john.doe@mail.com」電子メールアドレスを持つプロファイルを対象とした配達確認が送信されます。 「JD」プレフィックスが配達確認の件名行に追加されます。

   ![](assets/substitution_uc1.png)

1. ワークフローを構築して、ファイルからオーディエンスを作成します。 これを行うには、次のアクティビティを追加して設定します。

   * **[!UICONTROL Load file]** アクティビティ:CSVファイルを読み込みます(このアクティビティの詳細については、 [この節を参照](../../automating/using/load-file.md))。
   * **[!UICONTROL Reconciliation]** アクティビティ:ファイルの情報をデータベースの情報にリンクします。この例では、プロファイルの電子メールアドレスを調整フィールドとして使用します(このアクティビティの詳細については、[このセクション](../../automating/using/reconciliation.md)を参照してください)。
   * **[!UICONTROL Save audience]** アクティビティ:読み込んだファイルに基づいてオーディエンスを作成します(このアクティビティの詳細については、 [この節を参照](../../automating/using/save-audience.md))。

   ![](assets/substitution_uc2.png)

1. ワークフローを実行し、**[!UICONTROL Audiences]**&#x200B;タブに移動して、オーディエンスが必要な情報と共に作成されたことを確認します。

   この例では、オーディエンスは3つのプロファイルで構成されています。 それぞれが、配達確認を受け取る置換電子メールアドレスにリンクされ、配達確認の件名行に使用するプレフィックスが付きます。

   ![](assets/substitution_uc3.png)

### 手順2:ターゲットプロファイルへのワークフローの構築とニュースレターの送信

1. **[!UICONTROL Query]**&#x200B;と追加&#x200B;**[!UICONTROL Email delivery]**&#x200B;のアクティビティを設定し、必要に応じて設定します(「[クエリ](../../automating/using/query.md)」と「[電子メール配信](../../automating/using/email-delivery.md)」の節を参照)。

   ![](assets/substitution_uc4.png)

1. ワークフローを実行し、メッセージの準備が成功したことを確認します。

### 手順3:メッセージのプロファイル置換タブの設定

1. **[!UICONTROL Email delivery]**&#x200B;アクティビティを開きます。 メッセージダッシュボードで、**[!UICONTROL Audience]**&#x200B;ブロックをクリックします。

   ![](assets/substitution_uc5.png)

1. 「**[!UICONTROL Profile substitutions]**」タブを選択し、「**[!UICONTROL Import from an audience]**」をクリックします。

   ![](assets/substitution_uc6.png)

1. **[!UICONTROL Audience]**&#x200B;フィールドで、ファイルから作成したオーディエンスを選択します。

   ![](assets/substitution_uc7.png)

1. 配達確認の送信時に使用する置換住所と件名の接頭辞を定義します。

   これを行うには、**[!UICONTROL From audience]**&#x200B;オプションを選択し、情報を含むオーディエンスから列を選択します。

   ![](assets/substitution_uc8.png)

1. 「**[!UICONTROL Import]**」ボタンをクリックします。オーディエンスのプロファイルは、関連する置換アドレスと件名行プレフィックスと共にリストに追加されます。

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >この場合、オーディエンスのすべてのプロファイルは&#x200B;**[!UICONTROL Query]**&#x200B;アクティビティによってターゲット設定されます。 これらのプロファイルの1つがメッセージターゲットに含まれていない場合、リストに追加されません。

### 手順4:ターゲットプロファイルを使用したプレビュー

1. メッセージダッシュボードで、コンテンツのスナップショットをクリックして、電子メールデザイナーでメッセージを開きます。

   ![](assets/substitution_uc10.png)

1. 「**[!UICONTROL Preview]**」タブを選択し、「**[!UICONTROL Change profile]**」をクリックします。

   ![](assets/substitution_uc_preview.png)

1. 「**[!UICONTROL Profile Substitution]**」タブをクリックし、以前に追加した置換プロファイルを表示します。

   プレビューに使用するプロファイルを選択し、**[!UICONTROL Select]**&#x200B;をクリックします。

   ![](assets/substitution_uc_selectpreview.png)

1. メッセージのプレビューが表示されます。 矢印を使用して、選択したプロファイル間を移動します。

   ![](assets/substitution_uc_previewprofile.png)

### 手順5:配達確認の送信

1. メッセージダッシュボードで&#x200B;**[!UICONTROL Test]**&#x200B;ボタンをクリックし、確認します。

   ![](assets/substitution_uc_sendproof.png)

1. 配達確認は、「**[!UICONTROL Profile substitutions]**」タブで設定された内容に従って送信されます。

   ![](assets/substitution_uc_proofs.png)

## チュートリアルビデオ {#video}

このビデオでは、プロファイルの置き換えを使用して電子メールメッセージをテストする方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/32368?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)で参照できます。
