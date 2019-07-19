---
title: 電子メールチャネルの設定
seo-title: 電子メールチャネルの設定
description: 電子メールチャネルの設定
seo-description: 電子メールチャネルを設定する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 9fddb655- b445-41f3-9b02-5d356fc88aa1
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: configuring- channels
discoiquuid: 3752d41f-8c59-4fad- b30f- e98e09cd74a8
context-tags: extAccountEmail， overview;emailConfig， main;ルールセット、概要;配信，プロパティ，開く
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring email channel{#configuring-email-channel}

## Email channel parameters {#email-channel-parameters}

電子メール設定画面では、電子メールチャネルのパラメーターを定義できます。

![](assets/channels_1.png)

* **送信済み電子メールのヘッダーパラメーター**

   In this section, you can specify the **[!UICONTROL masks]** authorized for the sender address and the error address. 必要に応じて、これらのマスクをコンマで区切ることができます。この設定はオプションです。これらのフィールドが入力されると、メッセージの準備段階で、Adobe Campaignは入力されたアドレスが有効であるかどうかを確認します。この操作モードによって、配信品質の問題をトリガーする可能性のあるアドレスが使用されなくなります。配信アドレスは、配信サーバー上で設定する必要があります。

* **配信品質**

   このIDはサポートによって提供されます。配信品質レポートが正しく動作する必要があります。

* **配信パラメーター**

   Adobe Campaignは、開始日から始まるメッセージを送信します。**[!UICONTROL Message delivery duration]** このフィールドでは、メッセージの送信期間を指定できます。

   **[!UICONTROL Online resources validity duration]** このフィールドは、ミラーページと画像に主にアップロードされたリソースに使用されます。このページのリソースは、限られた時間（ディスク容量を節約するため）に有効です。

* **再試行**

   一時的に未配信のメッセージには、自動再試行が許可されます。This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**).

   デフォルトでは、5回の再試行は、1時間の最小間隔が1時間で、24時間の間に広がります。One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **電子メール隔離パラメーター**

   **[!UICONTROL Time between two significant errors]** フィールドに、エラーの場合にエラーカウンターを増分する前にアプリケーションが待機する時間を定義する値を入力します。Defaut value: **"1d"**, for 1 day.

   **[!UICONTROL Maximum number of errors before quarantine]** 値に達すると、電子メールアドレスが隔離されます。Default value: **"5"**: the address will be quarantined on the sixth error. つまり、その連絡先は、後続の配信から自動的に除外されます。

**関連トピック**:

[強制隔離について](../../sending/using/understanding-quarantine-management.md)

## Email routing accounts {#email-routing-accounts}

**[!UICONTROL Integrated email routing]** 外部アカウントはデフォルトで提供されます。アプリケーションが電子メールを送信できる技術的なパラメーターが含まれています。

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**関連トピック**:

[外部アカウント](../../administration/using/external-accounts.md)

## Email processing rules {#email-processing-rules}

These rules contain the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

デフォルトのルールは次のとおりです。

**バウンスメール**

電子メールが失敗すると、リモートメッセージサーバーは、アプリケーション設定で指定されたアドレスにバウンスエラーメッセージを返します。Adobe Campaignは、各バウンスメールの内容をルールのリスト内の文字列と比較し、3つのエラータイプのいずれかを割り当てます。

ユーザーは独自のルールを作成できます。

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**電子メールドメインの管理**

ドメイン管理ルールは、特定のドメインの送信電子メールのフローを制御するために使用します。ユーザーはバウンスメッセージをサンプルし、適切な場所に送信します。Adobe Campaignメッセージングサーバーは、ドメインに固有のルールを適用し、ルールのリスト内のアスタリスクで表される一般的なケースのルールを適用します。Adobe Campaignでは、HotmailドメインおよびMSNドメインのルールをデフォルトで使用できます。

ドメイン管理ルールを設定するには、しきい値を設定し、特定のSMTPパラメーターを選択します。**しきい値** は、特定のドメインに対するすべてのメッセージがブロックされるまでのエラー割合として計算される制限です。

例えば、一般的なケースでは、最小300メッセージの場合、エラー率が90%に達すると電子メールの送信が3時間ブロックされます。

**SMTPパラメーター** は、ブロックルールに適用されるフィルターとして機能します。

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTPリレー**:を使用すると、特定のドメインのリレーサーバーのIPアドレスとポートを設定できます。

**MX Management**

各ルールは、MXのアドレスマスクを定義します。このマスクに一致する名前を持つMXは、使用可能です。マスクには"*"と"?"を含めることができます。汎用文字。

例えば、次のアドレスです。

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

は、次のマスクと互換性があります。

* *.yahoo.com
* ?.mx.yahoo.com

次のルールが順番に適用されます。MXマスクが対象のMXと互換性がある最初のルールが適用されます。

ルールごとに次のパラメーターを使用できます。

* **[!UICONTROL Range of IDs]**:このオプションを使用すると、ルールが適用される識別子（publicId）の範囲を指定できます。次のように指定できます。

   * 数字:ルールはこのpublicIdにのみ適用されます。
   * 数値の範囲（number1~ number2）:このルールは、これら2つの数値の間のすべての投稿に適用されます。
   フィールドが空の場合、ルールはすべてのIDに適用されます。

* **[!UICONTROL Shared]**:このオプションは、1時間あたりのメッセージ数と接続数が、このルールにリンクされているすべてのmxsに適用されることを示します。
* **[!UICONTROL Maximum number of connections]**:特定のアドレスからのMXへの同時接続の最大数。
* **メッセージ**&#x200B;の最大数:1回の接続で送信できるメッセージの最大数です。この金額の後、接続が閉じ、新しい接続が再び開かれます。
* **[!UICONTROL Messages per hour]**:特定のアドレスを介してMXに対して1時間以内に送信できるメッセージの最大数です。

>[!CAUTION]
>
>* パラメーターが変更されている場合は、配信サーバー（MTA）を再起動する必要があります。
>* 管理ルールの変更または作成は、エキスパートユーザーのみを対象としています。
>



## List of email properties {#list-of-email-properties}

This section details the list of parameters available in the properties screen of an email or [email template](../../start/using/about-templates.md).

>[!NOTE]
>
>一部のパラメーターはテンプレートでのみ使用できます。Parameters you can access [depend on your permissions](../../administration/using/types-of-users.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### General parameters {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. この情報はインターフェイスに表示されますが、メッセージの受信者には表示されません。

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>IDは一意である必要があります。

**[!UICONTROL Brand]** このフィールドでは、配信にリンクされているブランドを選択できます。For more information on using and configuring brands, refer to the [Branding](../../administration/using/branding.md) section.

**[!UICONTROL Campaign]** このフィールドにより、電子メールにリンクされているキャンペーンを入力できます。

You can also add a **[!UICONTROL Description]** in the corresponding field and edit the image displayed on the email thumbnail in the lists.

### Sending parameters {#sending-parameters}

**[!UICONTROL Send]** セクションは電子メールテンプレートでのみ使用できます。次のパラメーターが含まれています。

#### Retries parameters {#retries-parameters}

一時的に未配信のメッセージには、自動再試行が許可されます。This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

デフォルトでは、5回の再試行は、1時間の最小間隔が1時間で、24時間の間に広がります。One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters) section.

再試行の数は、グローバル（アドビのテクニカル管理者に問い合わせる）、または配信または配信テンプレートごとに変更できます

**[!UICONTROL Test SMTP delivery]** このオプションを使用すると、SMTPを使用してメッセージをテストできます。メッセージは、SMTPサーバーとの接続が確立されるまで処理されますが、送信されません。For more information on configuring SMTP, refer to the [List of email SMTP parameters](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters) section.

#### Email format parameters {#email-format-parameters}

送信する電子メールの形式を設定できます。次の3つのオプションがあります。

* **受信者の環境設定を使用します** （デフォルトモード）:メッセージの形式は、受信者プロファイルに保存されているデータに従って定義され、デフォルトで **電子メール形式** フィールド（@ EmailFormat）に保存されます。受信者が特定の形式でメッセージを受信したい場合は、送信形式です。フィールドが完了していない場合は、マルチパート区切りのメッセージが送信されます（下記を参照）。
* **受信者メールクライアントに最も適した形式（multipart- alternative）を選択**&#x200B;します。メッセージには、次の両方の形式が含まれています。テキストとHTMLを使用します。受信時に表示される形式は、受信者のメールソフトウェアの設定によって異なります（マルチパート区切り）。

   >[!CAUTION]
   >
   >このオプションには、メッセージの両方のバージョンが含まれます。これは、メッセージサイズが大きいので配信スループットに影響します。

* **すべてのメッセージをテキスト形式で送信**&#x200B;します。メッセージはテキスト形式で送信されます。HTML形式は送信されませんが、受信者がメッセージ内のリンクをクリックしたときにのみミラーページに使用されます。

### Validity period parameters {#validity-period-parameters}

**[!UICONTROL Validity]** この節では、以下のパラメーターについて説明します。

* **[!UICONTROL Explicitly set validity dates]**:このボックスの選択を解除すると、 **[!UICONTROL Delivery duration]****[!UICONTROL Resource validity limit]** フィールドに期間を入力する必要があります。特定の日時を定義する場合は、このチェックボックスをオンにします。
* **[!UICONTROL Delivery duration]**:Adobe Campaignは、開始日から始まるメッセージを送信します。このフィールドでは、メッセージの送信期間を指定できます。
* **[!UICONTROL Resource validity duration]**:このフィールドは、主にミラーページと画像のアップロードされたリソースに使用されます。このページのリソースは、限られた時間（ディスク容量を節約するため）に有効です。
* **[!UICONTROL Mirror page management]**:ミラーページは、WebブラウザーからオンラインでアクセスできるHTMLページです。コンテンツは電子メールコンテンツと同じです。デフォルトでは、メールコンテンツにリンクが挿入されるとミラーページが生成されます。このフィールドでは、このページの生成方法を変更できます。

   >[!CAUTION]
   >
   >ミラーページを作成するには、電子メール用のHTMLコンテンツが定義されている必要があります。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** （デフォルトモード）:メールコンテンツにリンクが挿入されると、ミラーページが生成されます。
   * **ミラーページの生成を強制**&#x200B;的に行います。ミラーページへのリンクがメッセージに挿入されていない場合でも、ミラーページが作成されます。
   * **ミラーページを生成し**&#x200B;ない:リンクがメッセージ内にある場合でも、ミラーページは生成されません。
   * **メッセージIDのみを使用してアクセスできるミラーページを生成**&#x200B;します。このオプションを使用すると、パーソナライゼーション情報付きのミラーページのコンテンツに配信ログウィンドウにアクセスできます。

>[!NOTE]
>
>**[!UICONTROL Explicitly set validity dates]** トランザクションメッセージに **[!UICONTROL Delivery duration]** は、パラメーターは適用されません。For more on transactional messaging, see [this section](../../channels/using/about-transactional-messaging.md).

### Tracking parameters {#tracking-parameters}

**[!UICONTROL Tracking]** この節では、以下のパラメーターについて説明します。

* **[!UICONTROL Activate tracking]**:を使用すると、メッセージURL追跡をアクティブ化/非アクティブ化できます。To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. See [About tracked URLs](../../designing/using/about-tracked-urls.md).
* **[!UICONTROL Tracking validity limit]**:では、URLでトラッキングをアクティブにする時間を定義できます。
* **[!UICONTROL Substitution URL for expired URLs]**:トラッキングの有効期限が切れると表示されるWebページへのURLを入力できます。

### Advanced parameters {#advanced-parameters}

**[!UICONTROL Advanced parameters]** セクションには複数のパラメーターが含まれています。

最初の2つのフィールドでは、電子メールメッセージヘッダー（返信アドレスおよび返信アドレステキスト）に必要な情報を入力できます。この情報はパーソナライズできます。これを行うには、変更するフィールドの右側のボタンをクリックし、パーソナライゼーションフィールドを追加します。Inserting and using the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

#### Target context {#target-context}

ターゲットコンテキストでは、電子メールターゲティング（オーディエンス定義画面）とパーソナライゼーション（HTMLコンテンツエディターでのパーソナライゼーションフィールドの定義）に使用されるテーブルのセットを定義できます。

#### Routing {#routing}

このフィールドは、使用するルーティングモードを示します。外部アカウントを参照します。例えば、特定のブランド設定を含む外部アカウントを使用する場合に使用できます。

>[!NOTE]
>
>External accounts are accessible via the **Administration** &gt; **Application settings** &gt; **External accounts** menu.

#### Preparation {#preparation}

Preparing messages is detailed in the [Approving messages](../../sending/using/preparing-the-send.md) section.

* **[!UICONTROL Typology]**:送信する前に、コンテンツと設定を検証するためにメッセージを準備する必要があります。The verification rules applied during the preparation phase are defined in a **typology**. 例えば、電子メールの場合、準備には件名、URL、画像などがあります。このフィールドに適用する誤字を選択します。

   >[!NOTE]
   >
   >**[!UICONTROL Administration]** / **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** メニューからアクセスできるタイポロジは [、「タイポロジ](../../administration/using/about-typology-rules.md) 」セクションに表示されます。

* **[!UICONTROL Compute the label during delivery analysis]**:を使用すると、メッセージの準備段階で電子メールのラベル値を計算できます。
* **[!UICONTROL Save SQL queries in the log]**:このオプションを使用すると、準備段階でSQLクエリログをジャーナルに追加できます。

### List of email SMTP parameters {#list-of-email-smtp-parameters}

**[!UICONTROL SMTP]** この節では、以下のパラメーターについて説明します。

* **[!UICONTROL Character encoding]**:メッセージのエンコーディングを強制する **[!UICONTROL Force encoding]** 場合は、このチェックボックスをオンにして、使用するエンコーディングを選択します。
* **[!UICONTROL Bounce mails]**:デフォルトでは、バウンスメールはプラットフォームのエラーインボックス（ **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]****[!UICONTROL Configuration]** &gt;画面で定義）で受信されます。To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**:このオプションを使用すると、追加のSMTPヘッダーをメッセージに追加できます。**[!UICONTROL Headers]** フィールドに入力されたスクリプトは、名前の **形式で1行に1ヘッダーを参照する必要があります。の**&#x200B;値を指定します。値は必要に応じて自動的にエンコードされます。

   >[!CAUTION]
   >
   >追加のSMTPヘッダーを挿入するスクリプトの追加は、上級ユーザー向けに予約されています。このスクリプトの構文は、このコンテンツタイプの要件に準拠する必要があります。使用されていないスペース、空白の行など

### List of access authorization parameters {#list-of-access-authorization-parameters}

**[!UICONTROL Access authorization]** この節では、以下のパラメーターについて説明します。

* **[!UICONTROL Organizational unit]** このフィールドでは、特定のユーザーにこの電子メールへのアクセスを制限できます。指定された単位または親単位に関連付けられているユーザーは、この電子メールへの読み取りおよび書き込みアクセス権を持ちます。子単位に関連付けられたユーザーは、この電子メールへの読み取りアクセス権のみを持ちます。

   >[!NOTE]
   >
   >You can configure organizational units via the **Administration** &gt; **Users &amp; Security** menu.

* **[!UICONTROL Created by]**&#x200B;および **[!UICONTROL Created]****[!UICONTROL Modified by]****[!UICONTROL Last modified]** フィールドは自動的に完了します。

## Archiving emails {#archiving-emails}

Adobe Campaignを設定して、プラットフォームから送信された電子メールのコピーを保存することができます。

ただし、Adobe Campaign自体はアーカイブされたファイルを管理しません。外部システムを使用して、選択したメッセージを専用アドレスに送信できます。そこから専用のアドレスに送信できます。

この機能を配信テンプレートで有効にすると、指定した送信メッセージの正確なコピーを、指定する必要のあるBCC電子メールアドレス（配信受信者に表示されない）に送信できます。

### Recommendations and limitations {#recommendations-and-limitations}

* この機能はオプションです。使用許諾契約書を確認して、アカウント担当者に連絡してアクティブにしてください。
* BCC電子メールアドレスは1つだけ使用できます。
* 正常に送信された電子メールのみが考慮されます。バウンスはありません。
* プライバシー上の理由から、安全に個人を特定できる情報（PII）を保存できるアーカイブシステムによってBCC電子メールを処理する必要があります。
* 新しい配信テンプレートを作成する場合、オプションが購入されていても、デフォルトでは電子メールBCCは有効になっていません。使用する各配信テンプレートで手動で有効にする必要があります。

### Activating email archiving {#activating-email-archiving}

Email BCC is activated in the [email template](../../start/using/about-templates.md), through a dedicated option:

1. **リソース** / **テンプレート** / **配信テンプレートに移動**&#x200B;します。
1. Duplicate the out-of-the-box **[!UICONTROL Send via email]** template.
1. 複製されたテンプレートを選択します。
1. Click the **[!UICONTROL Edit properties]** button to edit the template's properties.
1. **[!UICONTROL Send]** セクションを展開します。
1. **[!UICONTROL Archive emails]** このテンプレートに基づいて配信ごとに送信されるすべてのメッセージのコピーを保持するには、チェックボックスをオンにします。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

