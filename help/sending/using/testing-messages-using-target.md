---
title: ターゲットプロファイルを使用したメールメッセージのテスト
description: ターゲットプロファイルと代用アドレスを使用したメッセージのテスト方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Control Groups
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 4%

---

# ターゲットプロファイルを使用したメールメッセージのテスト {#testing-message-profiles}

## 概要 {#overview}

[ テストプロファイル ](../../audiences/using/managing-test-profiles.md) に加えて、ターゲットプロファイルの 1 つの位置に自分を配置することで、メールメッセージをテストできます。 これにより、プロファイルが受け取るメッセージの正確な表現（カスタムフィールド、動的でパーソナライズされた情報、ワークフローからの追加データなど）を取得できます。

>[!IMPORTANT]
>
>この機能を使用すると、プロファイルの個人情報を外部のメールアドレスに送信できます。Campaign Standard でプライバシーリクエスト（GDPR および CCPA）を実行しても、リクエストは外部で実行されないことに注意してください。

主な手順は次のとおりです。

1. メッセージを設定し、**準備** フェーズを開始します。
1. メッセージの対象となるプロファイルから **1 つまたは複数のプロファイルを選択** します。
1. 各プロファイルに、配達確認の送信先となる **代替アドレス** を関連付けます。
1. （オプション）プロファイルごとに、配達確認の件名行に追加する **プレフィックス** を定義します。
1. プロファイルに対するメッセージの表示方法を電子メールDesignerで **プレビュー** します。
1. 配達確認を送信します。

   >[!IMPORTANT]
   >
   >配達確認は、[!DNL Campaign Standard] で標準配信として処理されます。 その結果、プロファイルの置き換えを使用して配達確認を送信すると、選択したプロファイルの配信ログとトラッキングログにレコードが追加されます。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

## プロファイルと代用アドレスの選択 {#selecting-profiles}

ターゲットプロファイルをテストに使用するには、まずプロファイルを選択してから、配達確認を受け取る代用アドレスを定義する必要があります。 これを行うには、[ ターゲットプロファイルから特定のプロファイルを選択 ](#selecting-individual-profiles) するか、[ 既存のオーディエンスからプロファイルをインポート ](#importing-from-audience) することができます。

>[!NOTE]
>
>テスト用に最大 100 個のプロファイルを選択できます。

### 個々のプロファイルの選択 {#selecting-individual-profiles}

1. メッセージダッシュボードで、メッセージの準備が正常に完了したことを確認し、「**[!UICONTROL Audience]**」ブロックをクリックします。

   ![](assets/substitution_preparation.png)

1. 「**[!UICONTROL Profile substitutions]**」タブで、「**[!UICONTROL Create element]**」ボタンをクリックして、テストに使用するプロファイルを選択します。

   ![](assets/substitution_tab.png)

1. 「プロファイル選択」ボタンをクリックして、メッセージのターゲットとなるプロファイルのリストを表示します。

   ![](assets/substitution_recipient_selection.png)

1. テストに使用するプロファイルを選択し、「**[!UICONTROL Address]**」フィールドに目的の代用アドレスを入力して、「**[!UICONTROL Confirm]**」をクリックします。 プロファイルをターゲットとするすべての配達確認は、このプロファイル用にデータベースで定義された配達確認ではなく、このメールアドレスに送信されます。

   配達確認の件名行に特定のプレフィックスを追加する場合は、「**[!UICONTROL Subject line prefix]**」フィールドに入力します。

   >[!NOTE]
   >
   >件名行のプレフィックスには、最大 500 文字を含めることができます。

   ![](assets/substitution_address.png)

   プレフィックスは次のように表示されます。

   ![](assets/substitution_prefixsample.png)

1. プロファイルが、関連する代替アドレスとプレフィックスと共にリストに追加されます。 テストに使用するすべてのプロファイルに対して上記の手順を繰り返し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/substitution_recipients_confirm.png)

   同じプロファイルの複数の代用アドレスに配達確認を送信する場合は、このプロファイルを必要な回数だけ追加する必要があります。

   次の例では、プロファイル John Smith に基づく配達確認が、2 つの異なる代用アドレスに送信されます。

   ![](assets/substitution_multiple_addresses.png)

1. すべてのプロファイルと代用アドレスを定義したら、配達確認を送信してメッセージをテストできます。 それには、「**[!UICONTROL Test]**」ボタンをクリックし、実行するテストのタイプを選択します。

   テストプロファイルがメッセージターゲットに追加されていない場合、「**[!UICONTROL Email rendering]**」オプションと「**[!UICONTROL Proof + Email rendering]**」オプションは使用できません。  配達確認の送信について詳しくは、[ この節 ](../../sending/using/sending-proofs.md) を参照してください。

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>メッセージに変更を加えた場合は、メッセージの準備を再度開始してください。 そうしないと、変更はプルーフに反映されません。

### オーディエンスからのプロファイルの読み込み {#importing-from-audience}

Campaign Standardでは、テストに使用できるプロファイルのオーディエンスをインポートできます。 これにより、例えば、異なるプロファイルをターゲットにした一連のメッセージ全体を一意のメールアドレスに送信できます。

さらに、オーディエンスが既にアドレス列とプレフィックス列で設定されている場合は、「**[!UICONTROL Profile substitutions]**」タブでこれらの情報を読み込むことができます。 代用アドレスを使用したオーディエンスのインポート例について詳しくは、[ この節 ](#use-case) を参照してください。

>[!NOTE]
>
>オーディエンスをインポートすると、メッセージターゲットに対応するプロファイルのみが選択され、「**[!UICONTROL Profile substitutions]**」タブに追加されます。

プロファイルを読み込んでオーディエンスからテストで使用するには、次の手順に従います。

1. メッセージダッシュボードで、メッセージの準備が正常に完了したことを確認し、「**[!UICONTROL Audience]**」ブロックをクリックします。

   ![](assets/substitution_preparation.png)

1. 「**[!UICONTROL Profile substitutions]**」タブで、「**[!UICONTROL Import from an audience]**」をクリックします。

   ![](assets/substitution_audience_import.png)

1. 使用するオーディエンスを選択し、代替アドレスと、オーディエンスに送信される配達確認に使用するプレフィックスを入力します。

   >[!NOTE]
   >
   >件名行のプレフィックスには、最大 500 文字を含めることができます。

   ![](assets/substitution_audience_define.png)

   使用する代替アドレスやプレフィックスがオーディエンスで既に定義されている場合は、「**[!UICONTROL From Audience]**」オプションを選択し、これらの情報の取得に使用する列を指定します。

   ![](assets/substitution_fromaudience.png)

1. 「**[!UICONTROL Import]**」ボタンをクリックします。メッセージターゲットに対応するオーディエンスからのプロファイルと、関連する代用アドレスおよびプレフィックスが「**[!UICONTROL Profile substitution]**」タブに追加されます。

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>同じオーディエンスを、異なる代替アドレスやプレフィックスで再度インポートすると、前回のインポートに加えてプロファイルがリストに追加されます。

## ターゲットプロファイルを使用したメッセージのプレビュー

>[!NOTE]
>
>プレビューは、メールDesignerでのみ使用できます。

ターゲットプロファイルを使用してメッセージをプレビューできるようにするには、これらのプロファイルを **[!UICONTROL Profile substitution]** リストに追加したことを確認します（[ プロファイルと代用アドレスの定義 ](#selecting-profiles) を参照）。

メッセージでパーソナライゼーションフィールドを使用する場合は、メッセージの準備を開始する **前** に追加する必要があります。 そうでない場合、これらはプレビューでは考慮されません。 そのため、パーソナライゼーションフィールドに変更が加えられた場合は、メッセージの準備を再度開始してください。

プロファイルの置き換えを使用してメッセージをプレビューするには、次の手順に従います。

1. メッセージダッシュボードで、コンテンツスナップショットをクリックして、メールDesignerでメッセージを開きます。

   ![](assets/substitution_preview_access.png)

1. **[!UICONTROL Preview]** タブを選択し、「**[!UICONTROL Change profile]**」をクリックします。

   ![](assets/substitution_preview_changeprofile.png)

1. 「**[!UICONTROL Profile Substitution]**」タブをクリックして、テスト用に追加された代用プロファイルを表示します。

   プレビューに使用するプロファイルを選択し、「**[!UICONTROL Select]**」をクリックします。

   ![](assets/substitution_preview_selection.png)

1. メッセージのプレビューが表示されます。 矢印を使用して、選択したプロファイル間を移動します。

   ![](assets/substitution_preview.png)

## ユースケース {#use-case}

このユースケースでは、パーソナライズされたメールニュースレターを特定のプロファイルのセットに送信します。 ニュースレターを送信する前に、ターゲットプロファイルの一部を使用してプレビューし、外部ファイルで定義された内部メールアドレスに配達確認を送信します。

このユースケースの主な手順は次のとおりです。

1. テストに使用するオーディエンスを作成します。
1. プロファイルを対象とするワークフローを作成し、ニュースレターを送信します。
1. メッセージのプロファイルの置き換えを設定します。
1. ターゲットプロファイルを使用したメッセージのプレビュー。
1. 配達確認の送信。

### 手順 1：テストに使用するオーディエンスを作成する

1. 読み込むファイルを準備して、オーディエンスを作成します。 この場合、配達確認に使用する代替アドレスと、配達確認の件名行に追加するプレフィックスを含める必要があります。

   この例では、「oliver.vaughan@internal.com」のメールアドレスが、「john.doe@mail.com」のメールアドレスを持つプロファイルをターゲットにしたメッセージの配達確認を受信します。 「JD」プレフィックスがプルーフの件名に追加されます。

   ![](assets/substitution_uc1.png)

1. ファイルからオーディエンスを作成するワークフローを作成します。 それには、以下のアクティビティを追加して設定します。

   * **[!UICONTROL Load file]** アクティビティ：CSV ファイルをインポートします（詳しくは、[ この節 ](../../automating/using/load-file.md) を参照してください）。
   * **[!UICONTROL Reconciliation]** アクティビティ：ファイルの情報をデータベースの情報にリンクします。 この例では、プロファイルのメールアドレスを紐付けフィールドとして使用します（このアクティビティについて詳しくは、[ この節 ](../../automating/using/reconciliation.md)）を参照してください）。
   * **[!UICONTROL Save audience]** アクティビティ：読み込んだファイルに基づいてオーディエンスを作成します（このアクティビティについて詳しくは、[ この節 ](../../automating/using/save-audience.md) を参照してください）。

   ![](assets/substitution_uc2.png)

1. ワークフローを実行し、「**[!UICONTROL Audiences]**」タブに移動して、目的の情報でオーディエンスが作成されたことを確認します。

   この例では、オーディエンスは 3 つのプロファイルで構成されています。 それぞれの受信者は、プルーフを受信する代替メールアドレスにリンクされ、プルーフの件名に使用するプレフィックスが付きます。

   ![](assets/substitution_uc3.png)

### 手順 2：プロファイルを対象とするワークフローを作成してニュースレターを送信する

1. **[!UICONTROL Query]** アクティビティと **[!UICONTROL Email delivery]** アクティビティを追加し、必要に応じて設定します（「[ クエリ ](../../automating/using/query.md)」および「[ メール配信 ](../../automating/using/email-delivery.md)」の節を参照）。

   ![](assets/substitution_uc4.png)

1. ワークフローを実行し、メッセージが正常に準備されたことを確認します。

### 手順 3：メッセージの「プロファイルの置き換え」タブの設定

1. **[!UICONTROL Email delivery]** アクティビティを開きます。 メッセージダッシュボードで、「**[!UICONTROL Audience]**」ブロックをクリックします。

   ![](assets/substitution_uc5.png)

1. **[!UICONTROL Profile substitutions]** タブを選択し、「**[!UICONTROL Import from an audience]**」をクリックします。

   ![](assets/substitution_uc6.png)

1. 「**[!UICONTROL Audience]**」フィールドで、ファイルから作成したオーディエンスを選択します。

   ![](assets/substitution_uc7.png)

1. 配達確認の送信時に使用する代替アドレスおよび件名行プレフィックスを定義します。

   これを行うには、「**[!UICONTROL From audience]**」オプションを選択し、情報を含むオーディエンスから列を選択します。

   ![](assets/substitution_uc8.png)

1. 「**[!UICONTROL Import]**」ボタンをクリックします。オーディエンスのプロファイルが、関連する代替アドレスと件名プレフィックスと共にリストに追加されます。

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >この場合、オーディエンスのすべてのプロファイルが **[!UICONTROL Query]** アクティビティのターゲットになります。 これらのプロファイルのいずれかがメッセージターゲットに含まれていない場合、リストには追加されません。

### 手順 4：ターゲットプロファイルを使用したメッセージのプレビュー

1. メッセージダッシュボードで、コンテンツスナップショットをクリックして、メールDesignerでメッセージを開きます。

   ![](assets/substitution_uc10.png)

1. **[!UICONTROL Preview]** タブを選択し、「**[!UICONTROL Change profile]**」をクリックします。

   ![](assets/substitution_uc_preview.png)

1. 「**[!UICONTROL Profile Substitution]**」タブをクリックすると、以前に追加した代用プロファイルが表示されます。

   プレビューに使用するプロファイルを選択し、「**[!UICONTROL Select]**」をクリックします。

   ![](assets/substitution_uc_selectpreview.png)

1. メッセージのプレビューが表示されます。 矢印を使用して、選択したプロファイル間を移動します。

   ![](assets/substitution_uc_previewprofile.png)

### 手順 5：配達確認の送信

1. メッセージダッシュボードで「**[!UICONTROL Test]**」ボタンをクリックし、確認します。

   ![](assets/substitution_uc_sendproof.png)

1. 配達確認は、「配達確認」タブで設定した内容に従って送 **[!UICONTROL Profile substitutions]** されます。

   ![](assets/substitution_uc_proofs.png)

## チュートリアルビデオ {#video}

このビデオでは、プロファイルの置き換えを使用してメールメッセージをテストする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/36510?quality=12&captions=jpn)

その他のCampaign Standardチュートリアルビデオについては、[ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。
