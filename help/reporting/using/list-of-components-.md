---
solution: Campaign Standard
product: campaign
title: 'コンポーネントのリスト '
description: 動的レポートで使用可能なすべてのコンポーネントのリストとその定義を以下に示します。
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 5%

---


# コンポーネントのリスト {#list-of-components}

ディメンションと指標の互換性の詳細については、次の [表を参照してください](/help/reporting/using/assets/dynamic_report_compatibility.pdf)。 2つのコンポーネントに互換性がない場合、セルには「 **なし**」と表示されます。

![](assets/dynamic_report_compatibility.png)

## サイズ {#dimensions}

次の表に、レポートで使用されるディメンションとその定義のリストを示します。

<table> 
 <thead> 
  <tr> 
   <th> ディメンション<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ブラウザー<br /> </td> 
   <td> メッセージが開かれた、またはクリックされたブラウザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> キャンペーン<br /> </td> 
   <td> キャンペーンのラベルとID。<br /> </td> 
  </tr> 
  <tr> 
   <td> 市区町村<br /> </td> 
   <td> 受信者のプロファイルに登録された市。<br /> </td> 
  </tr> 
  <tr> 
   <td> Country/region<br /> </td> 
   <td> 受信者のプロファイルに登録された国。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信<br /> </td> 
   <td> Label and ID of the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> デバイス<br /> </td> 
   <td> 電子メール/SMS/プッシュ通知が開かれた、表示された、またはクリックされたデバイス。<br /> </td> 
  </tr> 
  <tr> 
   <td> エラーの理由<br /> </td> 
   <td> 各配信にバウンスを引き起こしたエラーの種類(不明なユーザー、無効なドメイン、メールボックスがいっぱいなど)。<br /> </td> 
  </tr> 
  <tr> 
   <td> 性別<br /> </td> 
   <td> 受信者の性別（男性、女性など）。 受信者のプロファイルで性別フィールドが空の場合、値はnoneになります。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内メッセージのアクション<br /> </td> 
   <td> アプリ内メッセージに対するアクションが配信されます。例えば、ボタン1や2のアクションや拒否などです。<br /> </td> 
  </tr> 
  <tr> 
   <td> メッセージタイプ<br /> </td> 
   <td> 電子メール、SMS、プッシュ通知、アプリ内通知など、配信に使用されるチャネル。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mobile App name<br /> </td> 
   <td> モバイルアプリケーションの名前<br /> </td> 
  </tr> 
  <tr> 
   <td> プラットフォーム<br /> </td> 
   <td> メッセージが開かれた、表示された、またはクリックされたデバイスのプラットフォーム。<br /> </td> 
  </tr> 
  <tr> 
   <td> プロファイル<br /> </td> 
   <td> プロファイルリソースの拡張時に作成された、標準搭載されたフィールドとカスタムプロファイルフィールドを再グループ化します。詳しくは、この <a href="../../developing/using/key-steps-to-add-a-resource.md">ページ</a> または <a href="../../reporting/using/creating-a-custom-profile-dimension.md">次の</a>例を参照してください。<br /> このディメンションのデータは、プロファイルフィールドにリンクされたカスタムリソースが発行されるとすぐに取得されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> プッシュプラットフォーム<br /> </td> 
   <td> プッシュ通知が開かれたデバイスのプラットフォーム（iOS、Androidなど）。<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient domain<br /> </td> 
   <td> 電子メールを開くために使用するドメイン。<br /> </td> 
  </tr> 
  <tr> 
   <td> 繰り返し配信<br /> </td> 
   <td> 定期配信のラベルとID。<br /> </td> 
  </tr> 
  <tr> 
   <td> Sender domain<br /> </td> 
   <td> 電子メールの送信に使用するドメイン。<br /> </td> 
  </tr> 
  <tr> 
   <td> 送信者IP<br /> </td> 
   <td> 電子メールの送信に使用するIP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 都道府県<br /> </td> 
   <td> 州が受信者のプロファイルに登録されました。<br /> </td> 
  </tr> 
  <tr> 
   <td> トラッキング URL<br /> </td> 
   <td> ユーザーがメッセージからクリックしたURL。<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking URL category<br /> </td> 
   <td> 追跡URLに割り当てられたカテゴリ。<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking URL label<br /> </td> 
   <td> URLに付与されるラベル(ミラーページなど)。お問い合わせいただくか、開いてください。<br /> </td> 
  </tr> 
  <tr> 
   <td> 取引配信<br /> </td> 
   <td> トランザクション配信のラベルとID。<br /> </td> 
  </tr> 
  <tr> 
   <td> バリアント<br /> </td> 
   <td> A/Bテストの場合の電子メールのバリアントです。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 指標 {#metrics}

次の表に、レポートで使用される指標のリストと、配信タイプに応じた指標の定義を示します。

### 電子メールとSMSの指標 {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> On denylist<br /> </td> 
   <td> 電子メールをスパムまたは迷惑メールとして宣言した受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Denylist rate<br /> </td> 
   <td> 配信にマークされブロックリストているの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス数 + エラー数<br /> </td> 
   <td> 配信および自動返信処理中に発生したエラーの合計で、送信されたメッセージの合計数に関連して計算されたエラーの合計です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br /> </td> 
   <td> 送信された電子メールと比較してバウンスした電子メールの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> クリック<br /> </td> 
   <td> 配信内でコンテンツがクリックされた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> 配信内のクリックの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> 送信されたメッセージの合計数に関連して、正常に送信されたメッセージの数。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br /> </td> 
   <td> 正常に送信されたメッセージの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> Hard bounce<br /> </td> 
   <td> 誤った電子メールアドレスなど、永続的なエラーの合計数。<br /> </td> 
  </tr> 
  <tr> 
   <td> Hard bounce rate<br /> </td> 
   <td> 永続的なエラーが原因で失敗した配信の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> ミラーページ<br /> </td> 
   <td> ミラーページリンクをクリックした受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page rate<br /> </td> 
   <td> ミラーページリンクのクリック数の合計配信メッセージ数に対する割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> オファークリック数<br /> </td> 
   <td> 配信でオファーがクリックされた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> オファークリック率<br /> </td> 
   <td> オファーのクリックの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> 配信でメッセージが開かれた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> 開封済みメッセージの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br /> </td> 
   <td> 配信の送信の合計数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離<br /> </td> 
   <td> アドレスの強制隔離につながった、バウンスしたメッセージの数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine rate<br /> </td> 
   <td> 送信されたメッセージと比較した強制隔離の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 却下<br /> </td> 
   <td> SMTPサーバーによってスパムとして分類されたメッセージの数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejected rate<br /> </td> 
   <td> 拒否済みとマークされたメッセージの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce<br /> </td> 
   <td> 完全な受信トレイなどの一時エラーの合計数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce rate<br /> </td> 
   <td> 一時的な理由により失敗した配信の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数<br /> </td> 
   <td> 配信内のコンテンツをクリックした受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique opens<br /> </td> 
   <td> 配信を開いた受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribe rate<br /> </td> 
   <td> 配信されたメッセージと比較した、受信者別の購読解除の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 購読解除済み<br /> </td> 
   <td> 購読解除リンクのクリック数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### プッシュ通知指標 {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> バウンス数 + エラー数<br /> </td> 
   <td> MCPNSやプロバイダーからのエラーなど、送信されたメッセージの合計数に関して配信中に累積されたエラーの合計。<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br /> </td> 
   <td> 送信されたプッシュ通知と比較してバウンスしたプッシュ通知の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> クリック<br /> </td> 
   <td> プッシュ通知がデバイスに配信され、ユーザーがクリックした回数。 ユーザーは、通知を表示したいと考え、その後プッシュオープン追跡に移動するか、削除したいと考えていました。<br /> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> プッシュ通知に対して何らかのアクションを起こしたユーザーの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> 正常に送信されたプッシュ通知の数（プッシュ通知の送信総数に関連）。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br /> </td> 
   <td> 正常に送信されたプッシュ通知の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> プッシュ通知がデバイスに配信され、通知センターに何も操作されなかった回数です。 ほとんどの場合、インプレッション数は配信された数と同じになります。 これにより、デバイスはメッセージを取得し、その情報をサーバーに中継します。<br /> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br /> </td> 
   <td> 送信されたプッシュ通知の合計数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> デバイスに配信され、ユーザーがアプリを開くためにクリックしたプッシュ通知の合計数です。 これはプッシュクリックと似ていますが、通知が閉じられた場合にプッシュ開くはトリガーされません。<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> 開かれているプッシュ通知の割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数<br /> </td> 
   <td> 一意のユーザーがプッシュ通知と対話する回数、例えば通知やボタンのクリック数。<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br /> </td> 
   <td> 受信者別のインプレッション数。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーク開封数<br /> </td> 
   <td> 配信を開いた受信者の数です。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### アプリ内指標 {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> サービスプロバイダーがデバイスに配信したアプリ内メッセージの合計数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> トリガー条件が満たされたかどうかに応じて、受信者が表示したアプリ内メッセージの合計です。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App clicks <br /> </td> 
   <td> ボタン1またはボタン2をクリックした受信者の合計数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App click through rate<br /> </td> 
   <td> メッセージを表示したユーザーと比較して、ボタン1またはボタン2をクリックしたユーザーの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal<br /> </td> 
   <td> 受信者が閉じるボタンをクリックするか、自動的に閉じたときに閉じたメッセージの合計数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal rate<br /> </td> 
   <td> 受信者が却下したアプリ内メッセージの割合。<br /> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br /> </td> 
   <td> 配信が送信したプロセスの一部としてAdobe Campaignから送信されたアプリ内メッセージの合計数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br /> </td> 
   <td> 個別受信者によるインプレッション数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別アプリ内クリック数<br /> </td> 
   <td> 受信者がボタン1またはボタン2をクリックした回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別のアプリ内課金<br /> </td> 
   <td> 受信者がアプリ内メッセージを消去した回数です。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## セグメント {#segments}

>[!NOTE]
>
>デフォルトでは、レポートをフィルターするために **[!UICONTROL Exclude proof]** セグメントが既に選択されていますが、必要に応じて変更できます。

次の表に、レポートで使用されるセグメントとその定義のリストを示します。

<table> 
 <thead> 
  <tr> 
   <th> セグメント<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 年齢：ブーマー1<br /> </td> 
   <td> 1946年から1954年まで生まれた受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：ブーマー2<br /> </td> 
   <td> 1955年から1965年まで生まれた受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：18～25<br /> </td> 
   <td> 18～25歳の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：26 ～ 30<br /> </td> 
   <td> 26～30歳の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：31 ～ 40<br /> </td> 
   <td> 31歳から40歳の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：41 ～ 50<br /> </td> 
   <td> 41歳から50歳の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：X世代<br /> </td> 
   <td> 受信者は1966年から1976年まで生まれた。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：世代Y（2000年代）<br /> </td> 
   <td> 1977年から1994年まで生まれた受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：世代Z<br /> </td> 
   <td> 1995年から今日まで生まれた受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：50より大きい<br /> </td> 
   <td> 年齢が50を超える受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：25未満<br /> </td> 
   <td> 年齢が25歳未満の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：30未満<br /> </td> 
   <td> 年齢が30歳未満の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：40未満<br /> </td> 
   <td> 年齢が40歳未満の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：50未満<br /> </td> 
   <td> 年齢が50歳未満の受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> 年齢：無声生成<br /> </td> 
   <td> 1945年以前に生まれた受信者。<br /> </td> 
  </tr> 
  <tr> 
   <td> All visits<br /> </td> 
   <td> すべての受信者<br /> </td> 
  </tr> 
    <tr> 
   <td> 除外配達確認<br /> </td> 
   <td> レポートからの配達確認の除外<br /> </td> 
  </tr> 
 </tbody> 
</table>

