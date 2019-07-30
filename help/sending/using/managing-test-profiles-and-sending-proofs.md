---
title: テストプロファイルの管理と配達確認の送信
seo-title: テストプロファイルの管理と配達確認の送信
description: テストプロファイルの管理と配達確認の送信
seo-description: テストプロファイルと校正刷りを管理する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 準備とテストのメッセージ
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember，概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 663ce734a79d7895e1e5cbd6d5756447d42299fd

---


# Managing test profiles and sending proofs{#managing-test-profiles-and-sending-proofs}

## About test profiles {#about-test-profiles}

テストプロファイルを使用すると、定義されたターゲット条件に一致しない追加の受信者をターゲットにすることができます。これらは、受信者データベースの不正な使用を検出したり、電子メールがインボックスに届くことを確認するために、メッセージのオーディエンスに追加されます。

You can manage your test profiles from the advanced menu **[!UICONTROL Profiles & audiences > Test profiles]**.

テストプロファイルには、送信者によって制御される架空の連絡先情報または連絡先情報が含まれ、次のコンテキストのメッセージで使用できます。

* For sending **Proofs**: the Proof is a specific message used to check the message before sending the finalized delivery to recipients. コンテンツと形式に関して、配達確認テストプロファイルが配信をチェックします。See [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* **電子メールレンダリングの場合**:電子メールレンダリングテストプロファイルは、受信するメッセージインボックスに従ってメッセージが表示される方法をチェックするために使用します。例えば、Webメール、メッセージサービス、モバイルなど。[電子メールのレンダリングを参照](../../sending/using/email-rendering.md)してください。

   **電子メールレンダリング** は読み取り専用です。この使用によるテストプロファイルは、Adobe Campaignでのみ使用できます。

* **トラップ**&#x200B;として:メッセージは、クライアントファイルが不正に使用されているかどうかを識別する手段として、メインターゲットに送信されるというテストプロファイルに送信されます。
* **メッセージをプレビュー** するには:パーソナライゼーションエレメントをテストするメッセージをプレビューするときに、テストプロファイルを選択できます。

![](assets/test_profile.png)

## Managing test profiles {#managing-test-profiles}

### Creating test profiles {#creating-test-profiles}

1. From the advanced menu, via the Adobe Campaign logo, select **Profiles &amp; audiences &gt; Test profiles** to access the list of test profiles.

   ![](assets/test_profile_creation_1.png)

1. From the **[!UICONTROL Test profiles]** dashboard, click **Create**.

   ![](assets/test_profile_creation_2.png)

1. このプロファイルのデータを入力します。

   ![](assets/test_profile_creation_3.png)

1. テストプロファイルの用途を選択します。

   ![](assets/test_profile_creation_4.png)

1. Enter the contact channels **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, as well as the test profile address if necessary.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. トランザクションメッセージのパーソナライゼーションをテストするためにこのテストプロファイルを使用する場合は、イベントタイプとこのイベントのデータを指定します。
1. Click **[!UICONTROL Create]** to save the test profile.

その後、テストプロファイルがプロファイルのリストに追加されます。

**関連トピック:**

[テストプロファイル](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) ビデオの作成

### Editing test profiles {#editing-test-profiles}

テストプロファイルを編集し、そのデータにリンクされているデータを確認するか、またはそれを変更するには:

1. 編集するテストプロファイルを選択し、その画像をクリックします。
1. フィールドを確認または変更します。

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.

## Sending proofs {#sending-proofs}

配達確認は、メインターゲットに送信する前にメッセージをテストするための特定のメッセージです。

配達確認の受信者は、メッセージ（そのコンテンツとフォーム）を承認します。They are defined in the **Test profiles**. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

配達確認を送信するには、テストプロファイルをメッセージのオーディエンスに含める必要があります。

メッセージ内:

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. 使用する配達確認の種類を選択します。

   * **[!UICONTROL Email rendering]**:ターゲット設定されたボックスに従ってメッセージの受信方法をテストするには、このオプションを選択します。For more information, refer to [Email rendering](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**:このオプションを選択すると、メインターゲットに送信する前にメッセージがテストされます。配達確認受信者は、コンテンツとその形式の両方をチェックすることで、配信の承認を担当します。
   * **[!UICONTROL Proof + Email rendering]**:このオプションは、前の2つのオプションを組み合わせます。
   ![](assets/bat_select1.png)

1. 選択を確認します。

   テストプロファイルに配達確認が送信されます。

   ![](assets/bat_select2.png)

1. **[!UICONTROL Proofs]** ドロップダウンリストを使用して、配達確認を表示できます。

   ![](assets/bat_view.png)

1. 配達確認を選択して概要にアクセスします。For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. [電子メールのレンダリングを参照](../../sending/using/email-rendering.md)してください。

   ![](assets/bat_view2.png)

配達確認を受信した人のコメントに応じて、配信のコンテンツを変更するように求められます。変更が実行されたら、電子メールの準備を再開して配達確認を再送信する必要があります。Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

配信のコンテンツを最終的に確定するまで、必要な数だけ配達証拠を送信する必要があります。これが完了すると、メインターゲットに配信を送信して承認サイクルを閉じることができます。

**関連トピック:**

[テストの送信、電子メール](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) ビデオの準備と送信

## Sending proofs using additional data {#sending-proofs-using-additional-data}

この節では、疑似テストプロファイルデータを使用するとは対照的に、ワークフローでアクセスできる実際の顧客データを使用して、配達確認を送信する方法について説明します。これにより、ワークフローで使用される変数が正確で、受信者が受信するメッセージのビューを取得できます。

1. Create a test profile and enable **[!UICONTROL Proof]** and **[!UICONTROL Trap]** as the intended usage. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   このテストプロファイルはターゲットオーディエンスの一部になります。

   >[!NOTE]
   >
   >メッセージ内の任意のリッチフィールドに対してテストプロファイルをトラップとして使用する場合、対応する追加のデータは、実際のターゲットプロファイルからランダムに選択され、トラップテストプロファイルに割り当てられます。

1. マーケティングアクティビティリストにアクセスし、テストワークフローを作成します。

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. リンクされたテーブルからデータを追加します。For more on this, see [Enriching data](../../automating/using/query.md#enriching-data).

1. **電子メール配信** アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.

1. 電子メールメッセージダッシュボードから、作成したトラップの使用状況を示すテストプロファイルを選択します。

1. クエリアクティビティで定義した追加データを使用して、電子メールコンテンツのパーソナライゼーションフィールドに追加します。

1. 電子メールを保存してワークフローを開始します。

メッセージの準備中に、ターゲットカウントには選択したテストプロファイルが含まれます。
メッセージが送信されると、追加のデータが実際のプロファイルのデータに置き換えられます。

>[!NOTE]
>
>追加のデータのみが置き換えられます。テストプロファイルには、名前や姓などの実際のプロファイルデータは使用されません。
