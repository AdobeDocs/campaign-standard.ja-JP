---
solution: Campaign Standard
product: campaign
title: ターゲットプロファイルを使用した E メールメッセージのテスト
description: ターゲットプロファイルと代用アドレスを使用してメッセージをテストする方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: コントロール母集団
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 4%

---

# ターゲットプロファイルを使用した E メールメッセージのテスト {#testing-message-profiles}

## 概要 {#overview}

[テストプロファイル](../../audiences/using/managing-test-profiles.md)に加えて、ターゲットプロファイルの1つの位置に自分を配置して、Eメールメッセージをテストできます。 これにより、プロファイルが受け取るメッセージ(カスタムフィールド、動的情報、パーソナライズされた情報（ワークフローからの追加データを含む）の正確な内容を取得できます。

>[!NOTE]
>
> この機能は、Eメールメッセージでのみ使用できます。

主な手順は次のとおりです。

1. メッセージを設定し、**準備**&#x200B;フェーズを開始します。
1. **メッセージの対象となるプ** ロファイルの中から1つまたは複数のプロファイルを選択します。
1. 配達確認の送信先となる&#x200B;**代用アドレス**&#x200B;を各プロファイルに関連付けます。
1. （オプション）各プロファイルに対して、配達確認の件名行に追加する&#x200B;**プレフィックス**&#x200B;を定義します。
1. **** Eメールデザイナーで、プロファイルに対するメッセージの表示方法をプレビューします。
1. 配達確認を送信します。

>[!IMPORTANT]
>
>この機能を使用すると、プロファイルの個人情報を外部の E メールアドレスに送信できます。Campaign Standard でプライバシーリクエスト（GDPR および CCPA）を実行しても、リクエストは外部で実行されないことに注意してください。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

## プロファイルと代用アドレスの選択 {#selecting-profiles}

ターゲットプロファイルをテストに使用するには、まずターゲットプロファイルを選択してから、配達確認を受け取る代用アドレスを定義する必要があります。 これをおこなうには、ターゲットプロファイルの中から特定のプロファイル](#selecting-individual-profiles)を[選択するか、既存のオーディエンスから[プロファイルをインポート](#importing-from-audience)します。

>[!NOTE]
>
>テスト用のプロファイルは最大100個選択できます。

### 個々のプロファイルの選択 {#selecting-individual-profiles}

1. メッセージダッシュボードで、メッセージの準備が成功したことを確認し、**[!UICONTROL Audience]**&#x200B;ブロックをクリックします。

   ![](assets/substitution_preparation.png)

1. 「**[!UICONTROL Profile substitutions]**」タブで、「**[!UICONTROL Create element]**」ボタンをクリックして、テストに使用するプロファイルを選択します。

   ![](assets/substitution_tab.png)

1. 「プロファイルの選択」ボタンをクリックして、メッセージのターゲットとなるプロファイルのリストを表示します。

   ![](assets/substitution_recipient_selection.png)

1. テストに使用するプロファイルを選択し、**[!UICONTROL Address]**&#x200B;フィールドに目的の代用アドレスを入力して、「**[!UICONTROL Confirm]**」をクリックします。 プロファイルをターゲティングするすべての配達確認は、このプロファイルのデータベースで定義された配達確認ではなく、このEメールアドレスに送信されます。

   配達確認の件名行に特定のプレフィックスを追加する場合は、「**[!UICONTROL Subject line prefix]**」フィールドに入力します。

   >[!NOTE]
   >
   >件名行のプレフィックスは、500文字まで含めることができます。

   ![](assets/substitution_address.png)

   プレフィックスは次のように表示されます。

   ![](assets/substitution_prefixsample.png)

1. プロファイルが、関連する代用アドレスおよびプレフィックスと共にリストに追加されます。 テストに使用するすべてのプロファイルに対して上記の手順を繰り返し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/substitution_recipients_confirm.png)

   同じプロファイルの複数の代用アドレスに配達確認を送信する場合は、このプロファイルを必要な回数だけ追加する必要があります。

   次の例では、John Smithというプロファイルに基づく配達確認が、2つの異なる代用アドレスに送信されます。

   ![](assets/substitution_multiple_addresses.png)

1. すべてのプロファイルと代用アドレスを定義したら、配達確認を送信してメッセージをテストできます。 それには、「**[!UICONTROL Test]**」ボタンをクリックし、実行するテストのタイプを選択します。

   メッセージターゲットにテストプロファイルが追加されていない場合、 **[!UICONTROL Email rendering]**&#x200B;と&#x200B;**[!UICONTROL Proof + Email rendering]**&#x200B;のオプションは使用できません。  配達確認の送信について詳しくは、[この節](../../sending/using/sending-proofs.md)を参照してください。

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>メッセージに変更を加えた場合は、必ずメッセージの準備を再度開始してください。 そうしないと、変更は配達確認に反映されません。

### オーディエンスからのプロファイルのインポート {#importing-from-audience}

Campaign Standardを使用すると、テストに使用できるプロファイルのオーディエンスをインポートできます。 これにより、例えば、様々なプロファイルをターゲットとする一連のメッセージ全体を一意のEメールアドレスに送信できます。

さらに、オーディエンスに住所列とプレフィックス列が既に設定されている場合は、「**[!UICONTROL Profile substitutions]**」タブでこれらの情報をインポートできます。 置換アドレスを使用したオーディエンスインポートの例について詳しくは、[この節](#use-case)を参照してください。

>[!NOTE]
>
>オーディエンスをインポートする場合、メッセージのターゲットに対応するプロファイルのみが選択され、「**[!UICONTROL Profile substitutions]**」タブに追加されます。

オーディエンスからのテストに使用するプロファイルをインポートするには、次の手順に従います。

1. メッセージダッシュボードで、メッセージの準備が成功したことを確認し、**[!UICONTROL Audience]**&#x200B;ブロックをクリックします。

   ![](assets/substitution_preparation.png)

1. 「**[!UICONTROL Profile substitutions]**」タブで、「**[!UICONTROL Import from an audience]**」をクリックします。

   ![](assets/substitution_audience_import.png)

1. 使用するオーディエンスを選択し、オーディエンスに送信する配達確認に使用する代替アドレスとプレフィックスを入力します。

   >[!NOTE]
   >
   >件名行のプレフィックスは、500文字まで含めることができます。

   ![](assets/substitution_audience_define.png)

   使用する代用アドレスやプレフィックスがオーディエンスで既に定義されている場合は、**[!UICONTROL From Audience]**&#x200B;オプションを選択し、これらの情報の取得に使用する列を指定します。

   ![](assets/substitution_fromaudience.png)

1. 「**[!UICONTROL Import]**」ボタンをクリックします。メッセージターゲットに対応するオーディエンスのプロファイルが、関連する代用アドレスおよびプレフィックスと共に「**[!UICONTROL Profile substitution]**」タブに追加されます。

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>同じオーディエンスを再度インポートし、別の置換アドレスやプレフィックスを付けると、前のインポートのプロファイルに加えて、プロファイルがリストに追加されます。

## ターゲットプロファイルを使用したメッセージのプレビュー

>[!NOTE]
>
>プレビューは、Eメールデザイナーでのみ使用できます。

ターゲットプロファイルを使用してメッセージをプレビューできるようにするには、これらのプロファイルを&#x200B;**[!UICONTROL Profile substitution]**&#x200B;リストに追加している必要があります（[プロファイルと代用アドレスの定義](#selecting-profiles)を参照）。

メッセージ内にパーソナライゼーションフィールドを使用する場合は、メッセージの準備を開始する前に&#x200B;**パーソナライゼーションフィールドを追加する必要があります。**&#x200B;そうしないと、プレビューでは考慮されません。 その結果、パーソナライゼーションフィールドに変更が加えられた場合は、必ずメッセージの準備を再度開始してください。

プロファイルの置き換えを使用してメッセージをプレビューするには、次の手順に従います。

1. メッセージダッシュボードで、コンテンツのスナップショットをクリックして、Eメールデザイナーでメッセージを開きます。

   ![](assets/substitution_preview_access.png)

1. 「**[!UICONTROL Preview]**」タブを選択し、「**[!UICONTROL Change profile]**」をクリックします。

   ![](assets/substitution_preview_changeprofile.png)

1. 「 **[!UICONTROL Profile Substitution]** 」タブをクリックして、テスト用に追加された置換プロファイルを表示します。

   プレビューに使用するプロファイルを選択し、「**[!UICONTROL Select]**」をクリックします。

   ![](assets/substitution_preview_selection.png)

1. メッセージのプレビューが表示されます。 矢印を使用して、選択したプロファイル間を移動します。

   ![](assets/substitution_preview.png)

## ユースケース {#use-case}

この使用例では、パーソナライズされたEメールニュースレターを特定のプロファイルのセットに送信します。 ニュースレターを送信する前に、ターゲットプロファイルの一部を使用してプレビューし、外部ファイルで定義されている内部Eメールアドレスに配達確認を送信します。

この使用例の主な手順を次に示します。

1. テストに使用するオーディエンスを作成します。
1. プロファイルをターゲットに設定し、ニュースレターを送信するためのワークフローを作成します。
1. メッセージのプロファイルの置換を設定します。
1. ターゲットプロファイルを使用してメッセージをプレビューします。
1. 配達確認の送信.

### 手順1:テストに使用するオーディエンスの作成

1. オーディエンスを作成するために、インポートするファイルを準備します。 この場合、配達確認に使用する代替アドレスと、配達確認の件名行に追加するプレフィックスを含める必要があります。

   この例では、「oliver.vaughan@internal.com」Eメールアドレスは、「john.doe@mail.com」Eメールアドレスを持つプロファイルをターゲットとするメッセージの配達確認を受け取ります。 配達確認の件名行に、「JD」というプレフィックスが追加されます。

   ![](assets/substitution_uc1.png)

1. ファイルからオーディエンスを作成するワークフローを構築します。 これをおこなうには、以下のアクティビティを追加して設定します。

   * **[!UICONTROL Load file]** アクティビティ：CSVファイルをインポートします(このアクティビティについて詳しくは、この [節を参照](../../automating/using/load-file.md))。
   * **[!UICONTROL Reconciliation]** アクティビティ：ファイルの情報をデータベースの情報にリンクします。この例では、プロファイルのEメールアドレスを紐付けフィールドとして使用します（このアクティビティについて詳しくは、[この節](../../automating/using/reconciliation.md)を参照してください）。
   * **[!UICONTROL Save audience]** アクティビティ：インポートしたファイルに基づいてオーディエンスを作成します(このアクティビティについて詳しくは、この [節を参照](../../automating/using/save-audience.md))。

   ![](assets/substitution_uc2.png)

1. ワークフローを実行し、「 **[!UICONTROL Audiences]** 」タブに移動して、目的の情報でオーディエンスが作成されたことを確認します。

   この例では、オーディエンスは3つのプロファイルで構成されています。 各配達確認は、配達確認を受け取る代替Eメールアドレスにリンクされ、配達確認の件名行に使用するプレフィックスが付きます。

   ![](assets/substitution_uc3.png)

### 手順2:プロファイルをターゲットに設定し、ニュースレターを送信するためのワークフローの作成

1. **[!UICONTROL Query]**&#x200B;と&#x200B;**[!UICONTROL Email delivery]**&#x200B;アクティビティを追加し、必要に応じて設定します（[クエリ](../../automating/using/query.md)と[Eメール配信](../../automating/using/email-delivery.md)の節を参照）。

   ![](assets/substitution_uc4.png)

1. ワークフローを実行し、メッセージの準備が成功したことを確認します。

### 手順3:メッセージの「プロファイルの置き換え」タブの設定

1. **[!UICONTROL Email delivery]**&#x200B;アクティビティを開きます。 メッセージダッシュボードで、「**[!UICONTROL Audience]**」ブロックをクリックします。

   ![](assets/substitution_uc5.png)

1. 「**[!UICONTROL Profile substitutions]**」タブを選択し、「**[!UICONTROL Import from an audience]**」をクリックします。

   ![](assets/substitution_uc6.png)

1. **[!UICONTROL Audience]**&#x200B;フィールドで、ファイルから作成したオーディエンスを選択します。

   ![](assets/substitution_uc7.png)

1. 配達確認の送信時に使用する代替アドレスと件名行のプレフィックスを定義します。

   これをおこなうには、「**[!UICONTROL From audience]**」オプションを選択してから、情報を含むオーディエンスから列を選択します。

   ![](assets/substitution_uc8.png)

1. 「**[!UICONTROL Import]**」ボタンをクリックします。オーディエンスのプロファイルが、関連する代用アドレスおよび件名行のプレフィックスと共にリストに追加されます。

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >この例では、オーディエンスのすべてのプロファイルが&#x200B;**[!UICONTROL Query]**&#x200B;アクティビティのターゲットになります。 これらのプロファイルの1つがメッセージターゲットに含まれていない場合、リストには追加されません。

### 手順4:ターゲットプロファイルを使用したメッセージのプレビュー

1. メッセージダッシュボードで、コンテンツのスナップショットをクリックして、Eメールデザイナーでメッセージを開きます。

   ![](assets/substitution_uc10.png)

1. 「**[!UICONTROL Preview]**」タブを選択し、「**[!UICONTROL Change profile]**」をクリックします。

   ![](assets/substitution_uc_preview.png)

1. 「 **[!UICONTROL Profile Substitution]** 」タブをクリックして、以前に追加した代替プロファイルを表示します。

   プレビューに使用するプロファイルを選択し、「**[!UICONTROL Select]**」をクリックします。

   ![](assets/substitution_uc_selectpreview.png)

1. メッセージのプレビューが表示されます。 矢印を使用して、選択したプロファイル間を移動します。

   ![](assets/substitution_uc_previewprofile.png)

### 手順5:配達確認の送信

1. メッセージダッシュボードで「**[!UICONTROL Test]**」ボタンをクリックし、確認します。

   ![](assets/substitution_uc_sendproof.png)

1. 配達確認は、「**[!UICONTROL Profile substitutions]**」タブで設定した内容に従って送信されます。

   ![](assets/substitution_uc_proofs.png)

## チュートリアルビデオ {#video}

このビデオでは、プロファイルの置き換えを使用してEメールメッセージをテストする方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/32368?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)からご覧いただけます。
