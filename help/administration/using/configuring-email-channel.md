---
title: Adobe Campaign Standard での E メールチャネルの設定
description: Adobe Campaign Standard で E メールチャネルを設定する方法を説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '2596'
ht-degree: 77%

---

# E メールチャネルの設定{#configuring-email-channel}

Campaign [管理者](../../administration/using/users-management.md#functional-administrators)は、E メールチャネルを設定できます。これらの詳細設定には、一般的な E メールチャネルパラメーター、E メールルーティングアカウント、E メール処理ルールおよび E メールのプロパティが含まれます。ここでは、一般的な E メールおよび送信パラメーターのデフォルト値を編集する方法について説明します。

## E メールチャネルパラメーター {#email-channel-parameters}

E メール設定画面では、E メールチャネルのパラメーターを定義できます。管理者は、**[!UICONTROL Administration]／[!UICONTROL Channels]／[!UICONTROL Email]／[!UICONTROL Configuration]**&#x200B;メニューから、これらの設定にアクセスできます。

![](assets/channels_1.png)

* **許可されたマスクフィールド**

   「**[!UICONTROL Header parameters of sent emails]**」セクションには、承認された E メールアドレスが一覧表示されます。この E メールアドレスを使用して、受信者に E メールを送信したり、非同期バウンス、不在返信など（エラーアドレス）の自動返信を送信したりできます。Adobe Campaign は、メッセージの準備段階で、入力されたアドレスが有効であるかどうかを確認します。この動作モードでは、配信品質の問題を引き起こす可能性のあるアドレスを一切使用しないようにします。
   * 送信者アドレスとエラーアドレスの両方は Adobe が設定します。これらのフィールドは空にできません。
   * これらのフィールドは編集できません。住所を更新する場合は、Adobe カスタマーケアチームにお問い合わせください。
   * 別のアドレスを追加する場合は、[Campaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=ja)を使用して新しいサブドメインを設定するか、Adobe カスタマーケアチームにお問い合わせください。複数のマスクを使用する場合は、コンマで区切ります。
   * *@yourdomain.com のような星形を使用してアドレスを設定することをお勧めします。サブドメイン名で終わる任意のアドレスを使用できます。

* **配信品質**

   **[!UICONTROL Delivery reports ID]**&#x200B;は、Adobe カスタマーケアチームによって提供されます。これは、技術的な配信品質レポートで使用される配信品質 ID で各インスタンスを識別します。
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **配信パラメーター**

   Adobe Campaign は、開始日にメッセージの送信を開始します。

   「**[!UICONTROL Message delivery duration]**」フィールドでは、一時的なエラーまたはソフトバウンスが発生した配信内のメッセージを再試行する時間枠を指定できます。

   >[!IMPORTANT]
   >
   >**Campaign のこのパラメーターは、3.5 日以下に設定した場合にのみ使用されるようになりました。** 3.5 日を超える値を定義した場合、その値は考慮されません。

   「**[!UICONTROL Online resources validity duration]**」フィールドは、アップロードされたリソース（主にミラーページと画像）に関して使用されます。ディスクスペースを節約するために、このページ上のリソースが有効な期間は限られています。

* **再試行**

   一時的に配信できなかったメッセージは、自動再試行の対象となります。詳しくは、[一時的な配信エラーの後の再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

   >[!IMPORTANT]
   >
   >実行する再試行の最大数と再試行間の最小遅延は、IP が特定のドメインでどの程度過去に実行され、現在どの程度の動作を実行しているかに基づいています。 Campaign の **[!UICONTROL Retry period]** 設定と **[!UICONTROL Number of retries]** 設定は無視されます。

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **E メール強制隔離のパラメーター**

   「**[!UICONTROL Time between two significant errors]**」フィールドに値を入力して、ソフトバウンスのエラーが発生した場合にエラーカウンターを増やすまでのアプリケーションの待機時間を定義します。デフォルト値は「**1d**」（1 日）です。

   **[!UICONTROL Maximum number of errors before quarantine]**&#x200B;値に達すると、E メールアドレスが隔離されます。デフォルト値は「**5**」：アドレスは 5 番目のエラーで隔離されます。これは、連絡先が後続の配信から自動的に除外されることを意味します。
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   強制隔離について詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## E メールルーティングアカウント {#email-routing-accounts}

デフォルトでは、**[!UICONTROL Integrated email routing]**&#x200B;外部アカウントが提供されます。アプリケーションから E メールを送信するための技術的なパラメーターが含まれます。

![](assets/channels_2.png)

アカウントタイプは常に&#x200B;**[!UICONTROL Routing]**&#x200B;に、チャネルは&#x200B;**[!UICONTROL Email]**&#x200B;に、配信モードは&#x200B;**[!UICONTROL Bulk delivery]**&#x200B;に設定されている必要があります。

**関連トピック**：

[外部アカウント](../../administration/using/external-accounts.md)

## E メール処理ルール {#email-processing-rules}

管理者は、**[!UICONTROL Administration > Channels > Email]**&#x200B;メニューから&#x200B;**[!UICONTROL Email processing rules]**&#x200B;にアクセスできます。

>[!IMPORTANT]
>
>E メールドメインと MX ルールは、自動的に管理されるようになり、<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> 変更できなくなりました。

* **DKIM(DomainKeys Identified Mail)**  E メール認証の署名は、すべてのドメインのすべてのメッセージに対しておこなわれます。**Sender ID**、**DomainKeys**、**S/MIME** は使用しません。
* MX ルールは、独自の履歴 E メールの評判と、E メールを送信するドメインからのリアルタイムフィードバックに基づいて、ドメインごとにスループットを自動的にカスタマイズします。

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### バウンスメール {#bounce-mails}

非同期バウンスは、引き続き、**[!UICONTROL Bounce mails]**&#x200B;ルールを通じて Campaign inMail プロセスで選定されます。

これらのルールには、リモートサーバーが返すことができ、エラー（**ハード**、**ソフト**&#x200B;または&#x200B;**無視**）を検証できる文字列のリストが含まれます。

>[!IMPORTANT]
>
>同期配信の失敗エラーメッセージは、Adobe Campaign Enhanced MTA で評価されるようになりました。この MTA はバウンスのタイプと選定を決定し、その情報を Campaign に返します。

バウンスメールの選定について詳しくは、[この節](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)を参照してください。

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## E メールプロパティのリスト {#list-of-email-properties}

このセクションでは、E メールまたは E メールテンプレートのプロパティ画面で使用できるパラメーターのリストについて詳しく説明します。

>[!NOTE]
>
>一部のパラメーターは、テンプレートでのみ使用できます。アクセスできるパラメーターは、[権限によって異なります](../../administration/using/users-management.md)。

E メールまたは E メールテンプレートのプロパティを編集するには、「**[!UICONTROL Edit properties]**」ボタンを使用します。

![](assets/delivery_options_1.png)

### 一般パラメーター {#general-parameters}

E メールパラメーター画面の上部で、「**[!UICONTROL Label]**」および「**[!UICONTROL ID]**」フィールドを使用して E メールを識別します。この情報はインターフェイスに表示されますが、メッセージ受信者には表示されません。

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>ID は一意である必要があります。

「**[!UICONTROL Brand]**」フィールドでは、配信にリンクされているブランドを選択できます。ブランドの使用と設定について詳しくは、[ブランディング](../../administration/using/branding.md)の節を参照してください。

「**[!UICONTROL Campaign]**」フィールドには、E メールにリンクされたキャンペーンを入力できます。

対応するフィールドの「**[!UICONTROL Description]**」に説明を追加し、リストの E メールサムネイルに表示される画像を編集することもできます。

### 送信パラメーター {#sending-parameters}

「**[!UICONTROL Send]**」セクションは、E メールテンプレートに対してのみ使用できます。次のパラメーターが含まれます。

#### 再試行パラメーター {#retries-parameters}

一時的に配信できなかったメッセージは、自動再試行の対象となります。詳しくは、[一時的な配信エラーの後の再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

>[!IMPORTANT]
>
>再試行間の最小遅延と実行する再試行の最大数は、IP が特定のドメインでどの程度過去に実行され、現在どの程度の動作を実行しているかに基づいています。 Campaign の **[!UICONTROL Retry period]** 設定と **[!UICONTROL Max. number of retries]** 設定は無視されます。

Campaign で設定した&#x200B;**配信期間設定**（[有効期間パラメーター](#validity-period-parameters)の節で定義）**は引き続き使用されますが、最大 3.5 日までです**。この時点で、再試行キュー内のメッセージがキューから削除され、バウンスとして返されます。配信エラーについて詳しくは、[この節](../../sending/using/understanding-delivery-failures.md#about-delivery-failures)を参照してください。

#### E メールフォーマットパラメーター {#email-format-parameters}

送信する E メールの形式を設定できます。次の 3 つのオプションを使用できます。

* **Use recipient preferences**（デフォルトモード）：メッセージの形式は、受信者のプロファイルに格納されたデータに従って定義され、デフォルトでは「**Email format**」フィールド（@emailFormat）に保存されます。受信者が特定の形式でメッセージを受信することを希望していれば、メッセージはその形式で送信されます。このフィールドに何も入力されていない場合は、マルチパート／オルタナティブメッセージが送信されます（以下を参照）。
* **Let recipient mail client choose the most appropriate format (multipart-alternative)**：メッセージには、テキストと HTML の両方の形式が含まれます。受信時に表示されるメッセージ形式は、受信者のメールソフトウェアの設定に応じて切り替わります（マルチパート／オルタナティブ）。

   >[!IMPORTANT]
   >
   >このオプションを指定すると、両方のバージョンのメッセージが含められます。したがって、メッセージサイズが大きくなり、配信のスループットに影響します。

* **Send all messages in text format**：メッセージはテキスト形式で送信されます。HTML 形式は送信されませんが、受信者がメッセージのリンクをクリックした場合にのみ表示されるミラーページに使用されます。

#### SMTP テストモード {#smtp-test-mode}

「**[!UICONTROL Enable SMTP test mode]**」オプションを使用すると、実際にメッセージを送信することなく、SMTP 接続を介した E メールの送信をテストできます。
SMTP サーバーとの接続が達成されるまでメッセージは処理されますが、送信されません。

![](assets/smtp-test-mode.png)

このオプションは、E メールおよび E メールテンプレートで使用できます。

E メールテンプレートに対して「SMTP test mode」オプションを有効にした場合、このテンプレートから作成されるすべての E メールメッセージでこのオプションが有効になります。

>[!IMPORTANT]
>
>E メールに対してこのオプションを有効にした場合、オフになるまでメッセージは送信されません。
>E メールまたは E メールテンプレートダッシュボードに警告が表示されます。

SMTP の設定について詳しくは、[E メール SMTP パラメーターのリスト](#list-of-email-smtp-parameters)の節を参照してください。

### 有効期間のパラメーター {#validity-period-parameters}

「**[!UICONTROL Validity period]**」セクションでは、次のパラメーターについて説明します。

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**：このチェックボックスがオフの場合は、「**[!UICONTROL Delivery duration]**」および「**[!UICONTROL Resource validity limit]**」フィールドに期間を入力する必要があります。

   特定の日時を定義する場合は、このチェックボックスをオンにします。

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**／**[!UICONTROL Validity limit for sending messages]**：Adobe Campaign は、開始日に開始するメッセージを送信します。このフィールドでは、メッセージを送信できる期間を指定できます。

   >[!IMPORTANT]
   >
   >**最大 3.5 日までの値を定義する必要があります。** 3.5 日を超える値を設定した場合、その値は考慮されません。

* **[!UICONTROL Resource validity duration]**／**[!UICONTROL Validity limit date for resources]**：このフィールドは、アップロードされたリソース（主にミラーページと画像）に関して使用されます。ディスクスペースを節約するために、このページ上のリソースが有効な期間は限られています。
* **[!UICONTROL Mirror page management]**：ミラーページは、Web ブラウザーからオンラインアクセス可能な HTML ページです。コンテンツは E メールの内容と変わりません。デフォルトでは、メールコンテンツ内にリンクが挿入されているとミラーページが生成されます。このフィールドでは、このページの生成方法を変更できます。

   >[!IMPORTANT]
   >
   >ミラーページを作成するには、E メールに HTML コンテンツが定義されている必要があります。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]**（デフォルトモード）：リンクがメールコンテンツに挿入された場合、ミラーページが生成されます。
   * **Force the generation of the mirror page**：メッセージ内にミラーページへのリンクが挿入されていなくても、ミラーページを生成します。
   * **Do not generate the mirror page**：メッセージ内にリンクが挿入されていても、ミラーページを生成しません。
   * **Generate a mirror page accessible using only the message ID**：配信ログウィンドウで、パーソナライズ機能情報を含むミラーページのコンテンツにアクセスできるようにします。

>[!NOTE]
>
>「**[!UICONTROL Delivery duration]**」パラメーターはトランザクションメッセージには適用されません。トランザクションメッセージについて詳しくは、[この節](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

### トラッキングパラメーター {#tracking-parameters}

「**[!UICONTROL Tracking]**」セクションでは、次のパラメーターについて説明します。

* **[!UICONTROL Activate tracking]**：メッセージ URL 追跡をアクティブ化／非アクティブ化できます。各メッセージ URL の追跡を管理するには、E メールデザイナーのアクションバーにある「**[!UICONTROL Links]**」アイコンを使用します。[追跡する URL について](../../designing/using/links.md#about-tracked-urls)を参照してください。
* **[!UICONTROL Tracking validity limit]**：URL で追跡を有効にする期間を定義できます。
* **[!UICONTROL Substitution URL for expired URLs]**：追跡の有効期限が切れた後に表示される web ページへの URL を入力できます。

### 詳細設定パラメーター {#advanced-parameters}

「**[!UICONTROL Advanced parameters]**」セクションには複数のパラメーターが含まれています。

最初のフィールドには、E メールメッセージヘッダーを詳細に記述するために必要な情報を入力できます。ここでは、返信先のアドレスとテキスト、および送信者のアドレス（「送信者」フィールドに入力）を管理できます。この情報はパーソナライズ可能です。

変更するフィールドの右側にあるボタンをクリックし、パーソナライゼーションフィールド、コンテンツブロックまたは動的テキストを追加します。

![](assets/advancedparameters.png)

パーソナライゼーションコンテンツの挿入と使用について詳しくは、[E メールコンテンツのパーソナライズ](../../designing/using/personalization.md)を参照してください。

#### Targeting context {#target-context}

ターゲティングコンテキストを使用すると、E メールのターゲット設定（オーディエンス定義画面）およびパーソナライズ機能（HTML コンテンツエディターでのパーソナライゼーションフィールドの定義）に使用される一連のテーブルを定義できます。

#### ルーティング {#routing}

このフィールドは、使用されるルーティングモードを示します。これは外部アカウントを参照します。例えば、特定のブランディング設定を含む外部アカウントを使用する場合に使用できます。

>[!NOTE]
>
>外部アカウントには、**Administration**／**Application settings**／**External accounts**&#x200B;メニューからアクセスできます。

#### 準備 {#preparation}

メッセージの準備について詳しくは、[メッセージの承認](../../sending/using/preparing-the-send.md)の節を参照してください。

* **[!UICONTROL Typology]**：送信の前に、コンテンツと設定を検証するためのメッセージを準備する必要があります。準備段階中に適用される検証ルールは、**タイポロジ**&#x200B;内に定義されています。例えば、E メールの場合、件名、URL、画像などを確認する必要があります。このフィールドに適用するタイポロジを選択します。

   >[!NOTE]
   >
   >タイポロジ（、**[!UICONTROL Administration]**／**[!UICONTROL Channels]**／**[!UICONTROL Typologies]**&#x200B;メニューでアクセス可能）は[このセクション](../../sending/using/about-typology-rules.md)に表示されます。

* **[!UICONTROL Compute the label during delivery preparation]**：パーソナライゼーションフィールド、コンテンツブロック、動的テキストを使用して、メッセージの準備段階で E メールのラベル値を計算できます。

   ワークフローの外部シグナルアクティビティに宣言されたイベント変数を使用して、配信ラベルをパーソナライズすることもできます。詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md)を参照してください。

* **[!UICONTROL Save SQL queries in the log]**：このオプションを使用すると、準備段階でジャーナルに SQL クエリログを追加できます。

#### Proof settings {#proof-settings}

このセクションでは、配達確認の件名行に使用するデフォルトのプレフィックスを設定できます。詳しくは、[この節](../../sending/using/sending-proofs.md)を参照してください。

### E メール SMTP パラメーターのリスト {#list-of-email-smtp-parameters}

「**[!UICONTROL SMTP]**」セクションでは、次のパラメーターについて説明します。

* **[!UICONTROL Character encoding]**：メッセージのエンコーディングを強制する場合は、「**[!UICONTROL Force encoding]**」ボックスをチェックし、使用するエンコーディングを選択します。
* **[!UICONTROL Bounce mails]**：デフォルトでは、バウンスメールはプラットフォームのエラーインボックス（**[!UICONTROL Administration]**／**[!UICONTROL Channels]**／**[!UICONTROL Email]** ／**[!UICONTROL Configuration]**&#x200B;画面で定義）に受信されます。E メールの特定のエラーアドレスを定義するには、「**[!UICONTROL Error address]**」フィールドにアドレスを入力します。
* **[!UICONTROL Additional SMTP headers]**：このオプションを使用すると、追加の SMTP ヘッダーをメッセージに追加できます。「**[!UICONTROL Headers]**」フィールドで入力するスクリプトは、**名前:値**&#x200B;の形式で 1 行ごとに 1 つのヘッダーを参照する必要があります。値は必要に応じて自動的にエンコードされます。

   >[!IMPORTANT]
   >
   >スクリプトを追加すると、挿入する SMTP ヘッダーを追加できます。これは高度な知識を持つユーザー向けに用意されています。スクリプトの構文は、このコンテンツタイプの要件を満たしている必要があります（不要なスペースや空行を含まないなど）。

### アクセス許可パラメーターのリスト {#list-of-access-authorization-parameters}

「**[!UICONTROL Access authorization]**」セクションでは、次のパラメーターについて説明します。

* 「**[!UICONTROL Organizational unit]**」フィールドを使用すると、この E メールへのアクセスを特定のユーザーに制限できます。指定したユニットまたは親ユニットに関連付けられたユーザーは、この E メールに対する読み取りと書き込みをおこなえるようになります。子ユニットに関連付けられたユーザーは、この E メールに対する読み取りのみおこなえるようになります。

   >[!NOTE]
   >
   >組織単位は、**Administration**／**Users &amp; Security** メニューで設定できます。

* 「**[!UICONTROL Created by]**」、「**[!UICONTROL Created]**」、「**[!UICONTROL Modified by]**」、「**[!UICONTROL Last modified]**」の各フィールドは自動的に入力されます。

## 従来の設定 {#legacy-settings}

最新バージョンの Campaign を **実行していない** 場合でも、以下で説明するパラメーターと UI の節は引き続き適用されます。

### 再試行 {#legacy-retries}

E メールプロパティの [ 設定メニュー ](#email-channel-parameters) と [ 送信パラメーター ](#retries-parameters) の **[!UICONTROL Retries]** 設定は、送信開始の翌日 (**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**) に実行する再試行の回数と、再試行間の最小遅延 (**[!UICONTROL Retry period]**) を示します。

再試行の回数の変更は、グローバルに (Adobeの技術管理者にお問い合わせください )、または配信または配信テンプレートごとにおこなうことができます。

デフォルトでは、最初の日に 5 回の再試行がスケジュールされ、最低 1 時間の間隔が 1 日の 24 時間にわたって適用されます。 その後は、**[!UICONTROL Configuration]** メニューの **[!UICONTROL Delivery parameters]** セクションまたは配信レベルの **[!UICONTROL Validity period]** セクションでグローバルに定義される配信期限が来るまで、1 日 1 回の再試行がスケジュールされます（以下の [ 配信期間 ](#legacy-delivery-duration) の節を参照）。

### 配信期間 {#legacy-delivery-duration}

[ 設定メニュー ](#email-channel-parameters) の **[!UICONTROL Message delivery duration]** パラメーターを使用すると、一時的なエラーまたはソフトバウンスが発生した配信内のメッセージを再試行する時間枠を指定できます。

「 [ 有効期間パラメーター ](#validity-period-parameters) 」セクションの **[!UICONTROL Delivery duration]** または **[!UICONTROL Validity limit for sending messages]** パラメーターを使用すると、メッセージの送信期間を指定できます。

### E メール処理ルール {#legacy-email-processing-rules}

**[!UICONTROL MX management]**、**[!UICONTROL Bounce mails]** および **[!UICONTROL Domain management]** ルールは、管理者が **[!UICONTROL Administration > Channels > Email > Email processing rules]** [ メニュー ](#email-processing-rules) を使用してアクセスし、変更できます。

### バウンスメールの認定 {#legacy-bounce-mail-qualification}

様々なバウンスとそれに関連するエラータイプの理由を一覧表示するには、左上の **Adobe** ロゴをクリックし、**[!UICONTROL Administration > Channels > Quarantines > Message qualification]** を選択します。

バウンスは、次の資格認定ステータスを持つことができます。

* **[!UICONTROL To qualify]**:バウンスメールを選定する必要があります。選定は、プラットフォームの配信品質が正しく機能することを確認するために、配信品質チームがおこなう必要があります。 選定されていない限り、バウンスメールは E メール処理ルールのリストのエンリッチメントには使用されません。
* **[!UICONTROL Keep]**:バウンスメールは検証され、配信品質の更新ワークフ **ローで使用さ** れ、既存の e メール処理ルールと比較してリストをエンリッチメントします。
* **[!UICONTROL Ignore]**:バウンスメールは検証されましたが、配信品質の更新ワークフローで **は使用さ** れません。したがって、クライアントインスタンスに送信されません。

>[!NOTE]
>
>ISP を利用できなくなった場合、Campaign を通じて送信された E メールは、誤ってバウンスとしてマークされます。 これを修正するには、バウンスの認定条件を更新する必要があります。 詳しくは、[このページ](../../administration/using/update-bounce-qualification.md)を参照してください。

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### 配信指標レポート {#legacy-delivered-status-report}

各メッセージの **[!UICONTROL Summary]** 表示では、ソフトバウンスとハードバウンスがレポートされると、配信の有効期間を通じて **[!UICONTROL Delivered]** の割合が徐々に増加します。

ソフトバウンスメッセージは、配信の 1 日目の翌日に **[!UICONTROL Failed]** と表示され、配信の有効期間の翌日に再試行されます。
