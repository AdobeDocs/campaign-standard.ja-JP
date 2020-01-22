---
title: テストプロファイルの管理と校正の送信
description: テストのプロファイルと校正を管理する方法について説明します。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# テストプロファイルの管理と校正の送信{#managing-test-profiles-and-sending-proofs}

## テストプロファイルについて {#about-test-profiles}

テストプロファイルを使用すると、定義したターゲット条件に一致しない追加の受信者をターゲットに設定できます。 受信者データベースの不正使用を検出したり、電子メールが受信トレイに確実に届くように、メッセージのオーディエンスに追加されます。

テストプロファイルは、アドバンスメニューから管理できま **[!UICONTROL Profiles & audiences > Test profiles]**す。

テストプロファイルには架空の連絡先情報、または送信者によって制御される連絡先情報が含まれ、次のコンテキストでメッセージで使用できます。

* 校正を送 **信する**:配達確認は、受信者に確定された配信を送信する前にメッセージを確認するために使用される特定のメッセージです。 配信の内容と形式に関して、校正テストプロファイルが配信を確認します。 詳しくは、 [校正の送信を参照してくださ](#sending-proofs)い。
* 電子メー **ルレンダリング**:電子メールレンダリングテストプロファイルは、メッセージを受信したメッセージインボックスに従ってメッセージが表示される方法を確認するために使用されます。 例えば、Webメール、メッセージサービス、モバイルなど。 電子メール [レンダリングを参照](../../sending/using/email-rendering.md)。

   電子メ **ールレンダリング** (Email rendering use)は読み取り専用です。 この使用を使用したテストプロファイルは、Adobe Campaignの標準でのみ使用できます。

* トラッ **プ**:メッセージは、メインターゲットに送信されるのと同じように、テストプロファイルに送信されます。 トラップの [使用を参照してください](#using-traps)。
* メッセージ **をプレビューするには** 、次の手順に従います。メッセージをプレビューする際にテストプロファイルを選択して、パーソナライゼーション要素をテストできます。 詳しくは、メッ [セージのプレビューを参照してくださ](/help/sending/using/previewing-messages.md)い。

![](assets/test_profile.png)

## テストプロファイルの管理 {#managing-test-profiles}

### テストプロファイルの作成 {#creating-test-profiles}

1. アドバンスメニューのAdobe Campaignロゴから、 **Profiles &amp; audiences/Test profilesを選択して、テストプロファイルのリストにア** クセスします。

   ![](assets/test_profile_creation_1.png)

1. ダッシュボード **[!UICONTROL Test profiles]**で「作成」をクリ**&#x200B;ックしま&#x200B;**す。

   ![](assets/test_profile_creation_2.png)

1. このプロファイルのデータを入力します。

   ![](assets/test_profile_creation_3.png)

1. テストプロファイルに使用する用途を選択します。

   ![](assets/test_profile_creation_4.png)

1. 必要に応じて、連絡先チ **[!UICONTROL Email, Telephone, Mobile, Mobile app]**ャネルとテストプロファイルのアドレスを入力します。

   >[!NOTE]
   >
   >好みの電子メール形式を定義できます。ま **[!UICONTROL Text]**た**[!UICONTROL HTML]**&#x200B;は

1. このテストプロファイルをトランザクションメッセージのパーソナライゼーションのテストに使用する場合は、イベントタイプとこのイベントのデータを指定します。
1. をクリック **[!UICONTROL Create]**して、テストプロファイルを保存します。

次に、テストプロファイルがプロファイルのリストに追加されます。

**関連トピック：**

[テストプロファイルビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) （英語のみ）

### テストプロファイルの編集 {#editing-test-profiles}

テストプロファイルを編集し、そのプロファイルにリンクされているデータを参照する、または変更するには：

1. 画像をクリックして、編集するテストプロファイルを選択します。
1. フィールドを参照または変更します。

   ![](assets/test_profile_edit.png)

1. 変更を **[!UICONTROL Save]**入力した場合は、をクリックします。または、画面上部のセクションでテストプロファイルの名前を選択し、テストプロ**[!UICONTROL Test profiles]** ファイルダッシュボードに戻ります。

## 配達確認の送信 {#sending-proofs}

配達確認は、メインターゲットにメッセージを送信する前に、メッセージをテストできる特定のメッセージです。

証明の受信者は、メッセージ（内容とフォーム）の承認を担当します。 これらはテストプロファイルで **定義されます**。 詳しくは、テストプロファイルの管 [理を参照してください](#managing-test-profiles)。

証明を送信するには、テストプロファイルをメッセージのオーディエンスに含める必要があります。

メッセージ内：

1. ボタンをクリッ **[!UICONTROL Send a test]**クします。

   ![](assets/bat_select.png)

1. 使用する校正の種類を選択します。

   * **[!UICONTROL Email rendering]**:対象となるインボックスに従ってメッセージを受信する方法をテストする場合は、このオプションを選択します。 詳しくは、電子メールのレンダリングを参[照してください](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**:メインターゲットにメッセージを送信する前にメッセージをテストする場合は、このオプションを選択します。 配達確認の受信者は、コンテンツと形式の両方を確認して、配信を承認する責任を負います。
   * **[!UICONTROL Proof + Email rendering]**:このオプションは、前の2つのオプションを組み合わせます。
   ![](assets/bat_select1.png)

1. 選択を確認します。

   校正がテストプロファイルに送信されます。

   ![](assets/bat_select2.png)

1. ドロップダウンリストを使用して、校正 **[!UICONTROL Proofs]**を表示することができます。

   ![](assets/bat_view.png)

1. 概要にアクセスする校正を選択します。 電子メールの場合、校正タイプとして「電子メー **ルレンダリング** 」オプションを選択した場合は **[!UICONTROL Access email rendering]**、校正ラベルの右側にアイコンが表示されます。 電子メール[レンダリングを参照](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

配達確認を受け取った人からのコメントに応じて、配信のコンテンツを変更するように求められる場合があります。 変更が行われたら、電子メールの準備を再開し、証明を再送信する必要があります。 各新しい校正には、ボタンを使用してアクセスで **[!UICONTROL Show proofs]**きます。

配信内容が完成するまで、必要な数の証明書を送信する必要があります。 この処理が完了したら、配信をメインターゲットに送信し、承認サイクルを閉じることができます。

**関連トピック：**

[テストの送信、電子メールビデオの準備と送信](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html) 。

## トラップの使用 {#using-traps}

トラップを使用する場合、メッセージは、クライアントファイルが不正に使用されているかどうかを識別する手段として、メインターゲットに送信されるのと同じように、テストプロファイルに送信されます。

トラップは、元々ダイレクトメール配信用に設計されていました。 これらの機能により、次のことが可能になります。
* ダイレクトメールプロバイダーが本当に通信を送信していることを確認します。
* 顧客と同じ条件で同時にメールを受け取ります。
* 送信されたメールの正確なコピーを保管します。
* クライアントリストがダイレクトメールプロバイダーによって誤って使用されていないことを確認します。 実際、テストプロファイルのアドレスに他の通信が送られた場合は、知らない間にクライアントファイルが使われていた可能性があります。 これが、テストプロファイルのアドレスをこの目的にのみ使用する理由です。

ダイレクトメールのオーディエンスにトラップを追加する方法について詳しくは、「テストとトラッ [プのプロファイルの追加」を参照してくださ](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)い。

他の通信チャネルの場合は、次の目的でメインターゲットにトラップテストプロファイルを追加できます。
* メッセージが正常に送信されたことを確認します。
* メッセージの正確なコピーを取得し、保持します。
* 送信および受信日時を追跡します。

テストプロファイルをトラップとして使用するには、メッセージのオーディエンスに含める必要があります。

>[!NOTE]
>
>校正や電子メールのレンダリングに使用される [プロフ](#sending-proofs) ァイルのテストとは異なり [](../../sending/using/email-rendering.md)、メッセージはメインターゲットとトラップとして使用されるテストプロファイルに同時に送信されます。

メッセージのオーディエンスを定義する場合：

1. タブから、テ **[!UICONTROL Test profiles]**ストプロファイルを選択します。 これが意図した用途であるこ**[!UICONTROL Trap]** とを確認してください。

   ![](assets/trap_select.png)

1. メッセージの内容の準備が整ったら、ボタンをクリック **[!UICONTROL Prepare]**します。 See[Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >メインターゲットが選択されていることを確認します。 そうしないと、メッセージを送信できません。

1. ボタンをクリッ **[!UICONTROL Confirm]**クします。 See[Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

メッセージがメインターゲットとテストプロファイルに送信されます。

>[!NOTE]
>
>テスト・プロファイルをトラップとして使用する場合、メッセージ内の任意のリッチ・フィールドに対して、対応する追加データが実際のターゲット・プロファイルからランダムに選択され、トラップ・テスト・プロファイルに割り当てられる。 エンリッチメントの詳細については、この例を [参照してくださ](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file)い。
