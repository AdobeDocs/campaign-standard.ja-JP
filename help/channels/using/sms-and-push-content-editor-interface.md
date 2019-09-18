---
title: SMSとプッシュコンテンツエディタのインターフェイス
seo-title: SMSとプッシュコンテンツエディタのインターフェイス
description: SMSとプッシュコンテンツエディタのインターフェイス
seo-description: エディタの各セクションを使用してSMSを変更し、コンテンツをプッシュする方法を説明します。
page-status-flag: 未活性化の
uuid: 4af5d247-555b-45c5-95a7-cb27f356b5a0
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 編集， SMSとプッシュの内容
discoiquuid: 4e214eb9-d299-4095-b786-8d1de9b1c8a2
context-tags: 配信，smsContent，戻る
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# SMSとプッシュコンテンツエディタのインターフェイス{#sms-and-push-content-editor-interface}

SMSおよびプッシュコンテンツエディタは、メッセージを表示および編集できる2つの異なるセクションに編成されています。

1. アクシ **ョンバーに** 、ページの全般オプションが表示されます。 ここから、個人用設定フィールドやコンテンツブロックの挿入、条件付きテキストの追加、およびSMSコンテンツのプレビューを行うことができます。 「 [SMS」および「コンテンツエディタのアクションバーを押す](../../channels/using/sms-and-push-content-editor-interface.md#sms-and-push-content-editor-action-bar)」を参照。
1. 画面 **の編集領域** では、テキストメッセージを直接入力し、個人用設定を挿入する場所を選択できます。 「 [SMS」および「Push Content Editionモード」を参照](../../channels/using/sms-and-push-content-editor-interface.md#sms-and-push-content-edition-modes)。

## SMSとプッシュコンテンツエディタのアクションバー {#sms-and-push-content-editor-action-bar}

アクションバーには、作成中のコンテンツを操作するためのさまざまなボタンが含まれています。

<table> 
 <thead> 
  <tr> 
   <th> アイコン<br /> </th> 
   <th> ボタン名<br /> </th> 
   <th> チャンネル<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/viewon_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">プレビュー</span><br /> </td> 
   <td> SMSのみ<br /> </td> 
   <td> 受信者の電子メールの表示方法を表示できます。 メッセージのプ <a href="../../sending/using/previewing-messages.md">レビューを参照してくださ</a>い。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">元に戻す</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> 最後に実行した操作を取り消します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">やり直し</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> 最後に取り消した操作をやり直します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">個人用設定フィールドの挿入</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> データベースからコンテンツにフィールドを追加できます。 「個人用設 <a href="../../designing/using/personalization.md#inserting-a-personalization-field" target="_blank">定フィールドの挿入」を参照してくださ</a>い。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">コンテンツブロックを挿入</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> コンテンツに個人用設定ブロックを追加できます。 「コンテンツ <a href="../../designing/using/personalization.md#adding-a-content-block" target="_blank">ブロックの追加」を参照してくださ</a>い。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">ダイナミックテキストを有効にする</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> コンテンツに動的なテキストを挿入できます。 動的テキ <a href="../../channels/using/defining-dynamic-text.md" target="_blank">ストの定義を参照</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">ダイナミックテキストを無効にする</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> ダイナミックテキストを削除できます。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## SMSおよびプッシュコンテンツエディションモード {#sms-and-push-content-edition-modes}

SMSおよびプッシュコンテンツエディタには、次の機能が用意されています。

* テキストを入力します。
* 個人用設定フィールドを追加します。 詳細については、「個人用設定フィールドを [挿入する」を参照してくださ](../../designing/using/personalization.md#inserting-a-personalization-field)い。
* コンテンツブロックを追加します。 詳細は、「コンテンツブロックを追 [加する」を参照してください](../../designing/using/personalization.md#adding-a-content-block)。
* ダイナミックテキストを追加します。 詳細は、「ダイナミックテキストの定 [義」を参照してください](../../channels/using/defining-dynamic-text.md)。
* SMS送信者の名前をカスタマイズします（SMSのみ）。 詳細については、「 [SMSの構成」を参照してください](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)。

