---
title: 電子メールチャネルの設定
seo-title: 電子メールチャネルの設定
description: 電子メールチャネルの設定
seo-description: 電子メールチャネルの設定方法を説明します。
page-status-flag: 非活性化の
uuid: 9fdb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: 設定チャネル
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 電子メールチャネルの設定{#configuring-email-channel}

## 電子メールチャネルパラメーター {#email-channel-parameters}

電子メール設定画面では、電子メールチャネルのパラメータを定義できます。

![](assets/channels_1.png)

* **送信された電子メールのヘッダーパラメーター**

   このセクションでは、送信者アドレスとエ **[!UICONTROL masks]** ラーアドレスに対して承認された値を指定できます。 必要に応じて、これらのマスクをコンマで区切ることができます。 この設定はオプションです。 これらのフィールドに入力すると、メッセージの準備段階で、Adobe Campaignは入力されたアドレスが有効であることを確認します。 このオペレーティングモードでは、配信品質の問題を引き起こす可能性のあるアドレスが使用されないようにします。 配信アドレスは、配信サーバーで設定する必要があります。

* **配信品質**

   このIDはサポートによって提供されます。 配信品質レポートが正しく機能するには、これが必要です。

* **配信パラメーター**

   Adobe Campaignは開始日から始まるメッセージを送信します。 このフ **[!UICONTROL Message delivery duration]** ィールドでは、メッセージを送信できる期間を指定できます。

   The **[!UICONTROL Online resources validity duration]** field is used for uploaded resources, mainly for the mirror page and images. ディスクスペースを節約するために、このページ上のリソースが有効な期間は限られています。

* **再試行**

   一時的に配信できなかったメッセージは、自動再試行の対象となります。この節では、送信開始後に実行する再試行の回数(再試行回数&#x200B;**)と、再試行間隔の最小遅延(再試**&#x200B;行期間&#x200B;****)を示します。

   デフォルトでは、最低1時間の間隔で最初の日に5回の再試行がスケジュールされ、1日の24時間にわたって配信されます。 One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **E メール強制隔離のパラメーター**

   このフィー **[!UICONTROL Time between two significant errors]** ルドに、エラーが発生した場合にエラーカウンターを増やすまでのアプリケーションの待機時間を定義する値を入力します。 デフォルト値：「 **1d**」（1日）

   値に達する **[!UICONTROL Maximum number of errors before quarantine]** と、電子メールアドレスが隔離されます。 デフォルト値： **"5"**:アドレスは6番目のエラーで隔離されます。 つまり、連絡先は以降の配信から自動的に除外されます。

**関連トピック**:

[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)

## 電子メールルーティングアカウント {#email-routing-accounts}

外部ア **[!UICONTROL Integrated email routing]** カウントはデフォルトで提供されます。 アプリケーションが電子メールを送信するための技術的なパラメーターが含まれます。

![](assets/channels_2.png)

アカウントタイプは常ににに、チャネル **[!UICONTROL Routing]**&#x200B;はに、配信モードは **[!UICONTROL Email]** に設定されている必要がありま **[!UICONTROL Bulk delivery]**&#x200B;す。

**関連トピック**:

[外部アカウント](../../administration/using/external-accounts.md)

## 電子メール処理ルール {#email-processing-rules}

これらのルールには、リモートサーバーが返すことができ、エラー（**ハード**、**ソフト**&#x200B;または&#x200B;**無視**）を検証できる文字列のリストが含まれます。

デフォルトのルールには次のものがあります。

**バウンスメール**

電子メールが失敗すると、リモートメッセージサーバーは、アプリケーション設定で指定されたアドレスにバウンスエラーメッセージを返します。 Adobe Campaign は、各バウンスメールのコンテンツをルールのリストの文字列と比較して、3 つのエラータイプのいずれかを割り当てます。

ユーザーは独自のルールを作成できます。

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**電子メールドメインの管理**

ドメイン管理ルールを使用して、特定のドメインに送信される E メールのフローを規制します。このルールは、バウンスメッセージをサンプリングし、必要に応じて送信をブロックします。Adobe Campaign のメッセージングサーバーは、ドメイン独自のルールを適用します。一般的なケース用のルールは、ルールのリストにアスタリスクで表されます。デフォルトでは、Adobe Campaign で Hotmail ドメインと MSN ドメイン用のルールを使用できます。

ドメイン管理ルールを設定するには、しきい値を設定して、特定の SMTP パラメーターを選択するだけです。**しきい値**&#x200B;とは、特定のドメイン宛てのメッセージをブロックする基準となるエラー率です。エラー率がこの値を超えると、特定のドメイン宛てのすべてのメッセージがブロックされます。

例えば一般的なケースでは、300 件以上のメッセージに対してエラー率が 90％に達すると、E メールの送信が 3 時間ブロックされます。

**SMTP パラメーター**&#x200B;は、ブロッキングルールに適用されるフィルターの役割を果たします。

* 特定の識別標準や、**送信者 ID**、**DomainKeys**、**DKIM**、**S/MIME** などドメイン名をチェックするための暗号鍵を有効化するかどうかを選択できます。
* **SMTP リレー**：特定のドメインのリレーサーバーの IP アドレスおよびポートを設定できます。

**MX 管理**

各ルールはMXのアドレスマスクを定義します。 したがって、このマスクと名前が一致するMXはすべて有効です。 マスクには、「*」と「?」を含めることができます。 汎用文字。

例えば、次のアドレスがあります。

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

は、次のマスクと互換性があります。

* *.yahoo.com
* ?.mx.yahoo.com

次のルールが順に適用されます。mxマスクが対象のMXと互換性がある最初のルールが適用されます。

各ルールでは、次のパラメーターを使用できます。

* **[!UICONTROL Range of IDs]**:このオプションを使用すると、ルールを適用する識別子(publicId)の範囲を指定できます。 次の項目を指定できます。

   * 数値：ルールはこのpublicIdにのみ適用されます。
   * 数値の範囲（数値1 ～数値2）:この2つの数字の間のすべてのpublicIdにルールが適用されます。
   フィールドが空の場合、ルールはすべてのIDに適用されます。

* **[!UICONTROL Shared]**:このオプションは、1時間あたりの最大メッセージ数と接続数が、このルールにリンクされているすべてのMXに適用されることを示します。
* **[!UICONTROL Maximum number of connections]**:特定のアドレスからMXへの同時接続の最大数。
* **最大メッセージ数**:1つの接続で送信できるメッセージの最大数。 この金額が経過すると、接続が閉じられ、新しい接続が再び開かれます。
* **[!UICONTROL Messages per hour]**:mxに対して、指定したアドレスを介して1時間で送信できるメッセージの最大数。

>[!CAUTION]
>
>* パラメーターを変更した場合は、配信サーバー（MTA）を再起動する必要があります。
>* 管理ルールを変更または作成できるのは、エキスパートユーザーのみです。
>



## 電子メールのプロパティのリスト {#list-of-email-properties}

この節では、電子メールまたは電子メールテンプレートのプロパティ画面で使用できるパラメーターのリストにつ [いて説明しま](../../start/using/about-templates.md)す。

>[!NOTE]
>
>一部のパラメーターはテンプレートでのみ使用できます。 アクセスできるパラメータ [ーは、権限によって異なります](../../administration/using/users-management.md)。

電子メールまたは電子メールテンプレートのプロパティを編集するには、ボタンを使用 **[!UICONTROL Edit properties]** します。

![](assets/delivery_options_1.png)

### 一般パラメーター {#general-parameters}

電子メールパラメータ画面の上部で、およびフィールドを使用して電子メールを **[!UICONTROL Label]** 識別 **[!UICONTROL ID]** します。 この情報はインターフェイスに表示されますが、メッセージの受信者には表示されません。

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>IDは一意である必要があります。

このフ **[!UICONTROL Brand]** ィールドでは、配信にリンクされたブランドを選択できます。 ブランドの使用と設定の詳細については、「ブランド」の節を参照し [てください](../../administration/using/branding.md) 。

このフ **[!UICONTROL Campaign]** ィールドを使用して、電子メールにリンクされたキャンペーンを入力できます。

対応するフィールドにを追加 **[!UICONTROL Description]** し、リスト内の電子メールサムネールに表示される画像を編集することもできます。

### 送信パラメーター {#sending-parameters}

このセクシ **[!UICONTROL Send]** ョンは、電子メールテンプレートでのみ使用できます。 これには次のパラメーターが含まれます。

#### Retriesパラメーター {#retries-parameters}

一時的に配信できなかったメッセージは、自動再試行の対象となります。この節では、送信開始後の1日に実行する再試行の回数( **[!UICONTROL Max. number of retries]** )と、再試行間の最小遅延( **[!UICONTROL Retry period]** )を示します。

デフォルトでは、最低1時間の間隔で最初の日に5回の再試行がスケジュールされ、1日の24時間にわたって配信されます。 One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

再試行の回数は、グローバルに変更するか（アドビのテクニカル管理者にお問い合わせください）、各配信または配信テンプレートに対して変更できます

#### 電子メール形式パラメーター {#email-format-parameters}

送信する電子メールの形式を設定できます。 次の3つのオプションを使用できます。

* **受信者の環境設定** （デフォルトモード）を使用する：メッセージの形式は、受信者プロファイルに保存されたデータに従って定義され、デフォルトでは「 **Email format** 」フィールド(@emailFormat)に保存されます。 受信者が特定の形式でメッセージを受信することを希望していれば、メッセージはその形式で送信されます。フィールドが完了していない場合は、マルチパート代替メッセージが送信されます（以下を参照）。
* **受信者のメールクライアントに最も適切な形式を選択させます（マルチパート代替）**。メッセージには両方の形式が含まれます。テキストとHTML。 受信時に表示される形式は、受信者のメールソフトウェアの設定によって異なります（マルチパート代替）。

   >[!CAUTION]
   >
   >このオプションには、両方のバージョンのメッセージが含まれます。 したがって、メッセージサイズが大きいので、配信スループットに影響します。

* **すべてのメッセージをテキスト形式で送信**:メッセージはテキスト形式で送信されます。 HTML形式は送信されませんが、受信者がメッセージ内のリンクをクリックした場合にのみミラーページに使用されます。

#### SMTPテストモード {#smtp-test-mode}

このオプ **[!UICONTROL Enable SMTP test mode]** ションを使用すると、実際にメッセージを送信することなく、SMTP接続を介した電子メールの送信をテストできます。
SMTPサーバーとの接続が確立されるまでメッセージが処理されますが、送信されません。

![](assets/smtp-test-mode.png)

このオプションは、電子メールおよび電子メールテンプレートで使用できます。

電子メールテンプレートに対してSMTPテストモードオプションを有効にした場合、このテンプレートから作成されるすべての電子メールメッセージでこのオプションが有効になります。

>[!CAUTION]
>
>電子メールに対してこのオプションを有効にすると、オフになるまでメッセージは送信されません。
>電子メールまたは電子メールテンプレートのダッシュボードに警告が表示されます。

SMTPの設定について詳しくは、「電子メールSMTPパラメーター [のリスト」の節を参照してください](#list-of-email-smtp-parameters) 。

### 有効期間パラメーター {#validity-period-parameters}

この節に **[!UICONTROL Validity]** は、次のパラメーターが含まれています。

* **[!UICONTROL Explicitly set validity dates]**:このチェックボックスをオフにした場合は、およびフィールドに期間を入力する必要 **[!UICONTROL Delivery duration]** があ **[!UICONTROL Resource validity limit]** ります。 特定の日時を定義する場合は、このチェックボックスをオンにします。
* **[!UICONTROL Delivery duration]**:Adobe Campaignは開始日から始まるメッセージを送信します。 このフィールドでは、メッセージを送信できる期間を指定できます。
* **[!UICONTROL Resource validity duration]**:このフィールドは、主にミラーページと画像のアップロードされたリソースに使用されます。 ディスクスペースを節約するために、このページ上のリソースが有効な期間は限られています。
* **[!UICONTROL Mirror page management]**:ミラーページは、Webブラウザを介してオンラインでアクセスできるHTMLページです。 その内容は電子メールの内容と同じです。 デフォルトでは、リンクがメールコンテンツに挿入されると、ミラーページが生成されます。 このフィールドでは、このページの生成方法を変更できます。

   >[!CAUTION]
   >
   >ミラーページを作成する電子メールには、HTMLコンテンツを定義する必要があります。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** （デフォルトモード）:メールコンテンツにリンクが挿入されると、ミラーページが生成されます。
   * **ミラーページの生成を強制**:ミラーページへのリンクがメッセージに挿入されていない場合でも、ミラーページが作成されます。
   * **ミラーページを生成しない**:リンクがメッセージ内にある場合でも、ミラーページは生成されません。
   * **メッセージIDのみを使用してミラーページにアクセス可能**:このオプションを使用すると、パーソナライゼーション情報を含むミラーページのコンテンツに配信ログウィンドウでアクセスできます。

>[!NOTE]
>
>パラメー **[!UICONTROL Explicitly set validity dates]** ターとパ **[!UICONTROL Delivery duration]** ラメーターは、トランザクションメッセージには適用されません。 トランザクションメッセージングについて詳しくは、この節 [を参照してくださ](../../channels/using/about-transactional-messaging.md)い。

### トラッキングパラメーター {#tracking-parameters}

この節に **[!UICONTROL Tracking]** は、次のパラメーターが含まれています。

* **[!UICONTROL Activate tracking]**:メッセージのURLトラッキングをアクティブ化/非アクティブ化できます。 各メッセージURLの追跡を管理するには、「電子メールデザイナー」ア **[!UICONTROL Links]** クションバーのアイコンを使用します。 詳しくは、追 [跡されるURLについてを参照してくださ](../../designing/using/links.md#about-tracked-urls)い。
* **[!UICONTROL Tracking validity limit]**:URLでトラッキングを有効にする期間を定義できます。
* **[!UICONTROL Substitution URL for expired URLs]**:追跡の有効期限が切れると表示されるWebページへのURLを入力できます。

### 詳細設定パラメーター {#advanced-parameters}

セクション **[!UICONTROL Advanced parameters]** には複数のパラメーターが含まれます。

最初の2つのフィールドには、電子メールメッセージヘッダー（返信アドレスと返信アドレスのテキスト）を入念に入力するために必要な情報を入力できます。 この情報はパーソナライズ可能です。これを行うには、変更するフィールドの右側のボタンをクリックし、パーソナライゼーションフィールドを追加します。 パーソナライゼーションフィールドの挿入と使用について詳しくは、「パーソナライゼ [ーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field) 」の節を参照してください。

#### Targetコンテキスト {#target-context}

ターゲットコンテキストを使用すると、電子メールのターゲット設定（オーディエンス定義画面）とパーソナライゼーション（HTMLコンテンツエディターでパーソナライゼーションフィールドを定義）に使用する一連のテーブルを定義できます。

#### ルーティング {#routing}

このフィールドは、使用されるルーティングモードを示します。 外部アカウントを参照します。 例えば、特定のブランド設定を含む外部アカウントを使用する場合に使用できます。

>[!NOTE]
>
>外部アカウントには、管理/アプリケーシ **ョン設定** /外部ア **カウントメニュ** ーからアク **セスできます** 。

#### 準備 {#preparation}

メッセージの準備の詳細については、「メッセ [ージの承認](../../sending/using/preparing-the-send.md) 」を参照してください。

* **[!UICONTROL Typology]**:送信の前に、コンテンツと設定を検証するためのメッセージを準備する必要があります。 The verification rules applied during the preparation phase are defined in a **typology**. 例えば、電子メールの場合、件名、URL、画像などを確認する準備が必要です。 このフィールドに適用するタイポロジを選択します。

   >[!NOTE]
   >
   >「タイポロジ」セクションには、//メニ **[!UICONTROL Administration]** ューからア **[!UICONTROL Channels]** クセ **[!UICONTROL Typologies]** スできるタイポロジが表 [示され](../../administration/using/about-typology-rules.md) ます。

* **[!UICONTROL Compute the label during delivery preparation]**:パーソナライゼーションフィールド、コンテンツブロックおよび動的テキストを使用して、メッセージ準備段階での電子メールのラベル値を計算できます。

   また、ワークフローの外部シグナルアクティビティに宣言されたイベント変数を使用して、配信ラベルをパーソナライズすることもできます。 詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md)を参照してください。

* **[!UICONTROL Save SQL queries in the log]**:このオプションを使用すると、準備段階でSQLクエリログをジャーナルに追加できます。

### 電子メールSMTPパラメーターのリスト {#list-of-email-smtp-parameters}

この節に **[!UICONTROL SMTP]** は、次のパラメーターが含まれています。

* **[!UICONTROL Character encoding]**:メッセージ **[!UICONTROL Force encoding]** のエンコーディングを強制する場合は、このボックスをオンにして、使用するエンコーディングを選択します。
* **[!UICONTROL Bounce mails]**:デフォルトでは、バウンスメールはプラットフォームのエラーインボックス(&gt; &gt; **[!UICONTROL Administration]** &gt;画面で **[!UICONTROL Channels]** 定義 **[!UICONTROL Email]** )で受 **[!UICONTROL Configuration]** 信されます。 電子メールの特定のエラーアドレスを定義するには、フィールドにアドレスを入力 **[!UICONTROL Error address]** します。
* **[!UICONTROL Additional SMTP headers]**:このオプションを使用すると、追加のSMTPヘッダーをメッセージに追加できます。 フィールドに入力するスクリ **[!UICONTROL Headers]** プトは、name:valueの形式で1行に1つのヘッダーを参照する必要 **があります**。 値は必要に応じて自動的にエンコードされます。

   >[!CAUTION]
   >
   >スクリプトを追加すると、挿入する SMTP ヘッダーを追加できます。これは高度な知識を持つユーザー向けに用意されています。スクリプトの構文は、このコンテンツタイプの要件を満たしている必要があります（不要なスペースや空行を含まないなど）。

### アクセス承認パラメーターのリスト {#list-of-access-authorization-parameters}

この節に **[!UICONTROL Access authorization]** は、次のパラメーターが含まれています。

* このフ **[!UICONTROL Organizational unit]** ィールドを使用すると、この電子メールへのアクセスを特定のユーザーに制限できます。 指定したユニットまたは親ユニットに関連付けられたユーザーは、この電子メールに対する読み取りと書き込みのアクセス権を持ちます。 子ユニットに関連付けられたユーザーは、この電子メールに対する読み取りアクセス権のみを持ちます。

   >[!NOTE]
   >
   >組織単位は、管理/ユーザーとセキュリテ **ィ** ( **Administration** )メニューで設定できます。

* 、およ **[!UICONTROL Created by]**&#x200B;び各フ **[!UICONTROL Created]**&#x200B;ィー **[!UICONTROL Modified by]** ルドが自 **[!UICONTROL Last modified]** 動的に入力されます。

## E メールのアーカイブ {#archiving-emails}

プラットフォームから送信された電子メールのコピーを保持するようにAdobe Campaignを設定できます。

ただし、Adobe Campaign自体はアーカイブされたファイルを管理しません。 これにより、選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブできます。

この機能を有効にすると、対応する送信済みメッセージの正確なコピーを、指定する必要のあるBCC電子メールアドレス（配信受信者には見えない）に送信できます。

### 推奨事項と制限事項 {#recommendations-and-limitations}

* この機能はオプションです。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。
* BCC電子メールアドレスは1つだけ使用できます。
* 正常に送信された電子メールのみが考慮されます。 バウンスはありません。
* プライバシー上の理由から、BCC電子メールは、個人を特定できる情報(PII)を安全に保存できるアーカイブ・システムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、オプションが購入されていても、電子メールBCCはデフォルトで有効になっていません。 使用する各配信テンプレートで、この機能を手動で有効にする必要があります。

### 電子メールアーカイブのアクティブ化 {#activating-email-archiving}

電子メールBCCは、電子メールテンプレートで、次の専 [用オプションを使用し](../../start/using/about-templates.md)、アクティブ化されます。

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. そのまま使用できるテンプレートを複製 **[!UICONTROL Send via email]** します。
1. 複製したテンプレートを選択します。
1. テンプレートの **[!UICONTROL Edit properties]** プロパティを編集するには、このボタンをクリックします。
1. セクションを展 **[!UICONTROL Send]** 開します。
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

