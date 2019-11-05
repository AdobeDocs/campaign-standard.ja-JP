---
title: SMS およびプッシュコンテンツエディタインターフェイス
description: エディターの様々なセクションを使用してSMSを変更し、コンテンツをプッシュする方法を説明します。
page-status-flag: 非活性化の
uuid: 4af5d247-555b-45c5-95a7-cb27f356b5a0
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: editing-sms-and-push-content
discoiquuid: 4e214eb9-d299-4095-b786-8d1de9b1c8a2
context-tags: delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# SMS およびプッシュコンテンツエディタインターフェイス{#sms-and-push-content-editor-interface}

SMSおよびプッシュコンテンツエディターは、メッセージを表示および編集できる2つの異なるセクションに編成されています。

1. アクシ **ョンバーに** 、ページの一般的なオプションが表示されます。 ここから、パーソナライゼーションフィールドやコンテンツブロックの挿入、条件テキストの追加、SMSコンテンツのプレビューを行うことができます。 詳しくは、 [SMSおよびプッシュコンテンツエディタのアクションバーを参照してくださ](#sms-and-push-content-editor-action-bar)い。
1. 画面の **編集領域では** 、テキストメッセージを直接入力し、パーソナライゼーションを挿入する場所を選択できます。 詳しくは、 [SMSおよびプッシュコンテンツ編集モードを参照してくださ](#sms-and-push-content-edition-modes)い。

## SMSおよびプッシュコンテンツエディタのアクションバー {#sms-and-push-content-editor-action-bar}

アクションバーには、作成中のコンテンツを操作するための様々なボタンが含まれています。

<table> 
 <thead> 
  <tr> 
   <th> アイコン<br /> </th> 
   <th> ボタン名<br /> </th> 
   <th> チャネル<br /> </th> 
   <th> 説明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/viewon_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">プレビュー</span><br /> </td> 
   <td> SMSのみ<br /> </td> 
   <td> 受信者に対する電子メールのレンダリング方法を表示できます。 詳しくは、メッ <a href="../../sending/using/previewing-messages.md">セージのプレビューを参照してくださ</a>い。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">元に戻す</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> 最後に実行された操作をキャンセルします。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">やり直し</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> 最後に取り消した操作をやり直します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">パーソナライゼーションフィールドを挿入</span> <br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> データベースからコンテンツにフィールドを追加できます。 See <a href="../../designing/using/personalization.md#inserting-a-personalization-field" target="_blank">Inserting a personalization field</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">コンテンツブロックの挿入</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> コンテンツにパーソナライゼーションブロックを追加できます。 詳しくは、コ <a href="../../designing/using/personalization.md#adding-a-content-block" target="_blank">ンテンツブロックの追加を参照してくださ</a>い。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">動的テキストの有効化</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> コンテンツに動的テキストを挿入できます。 See <a href="../../channels/using/defining-dynamic-text.md" target="_blank">Defining dynamic text</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">動的テキストの無効化</span><br /> </td> 
   <td> SMSとプッシュ<br /> </td> 
   <td> ダイナミックテキストを削除できます。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## SMSおよびプッシュコンテンツ編集モード {#sms-and-push-content-edition-modes}

SMSおよびプッシュコンテンツエディターには、次の機能が用意されています。

* テキストを入力します。
* パーソナライゼーションフィールドの追加詳しくは、「パーソナライゼーションフィールド [の挿入」を参照してくださ](../../designing/using/personalization.md#inserting-a-personalization-field)い。
* コンテンツブロックを追加します。 詳しくは、「コンテンツブロックの追 [加」を参照してください](../../designing/using/personalization.md#adding-a-content-block)。
* ダイナミックテキストの追加 詳しくは、ダイナミックテキストの定義 [を参照してください](../../channels/using/defining-dynamic-text.md)。
* SMS送信者の名前をパーソナライズします（SMSのみ）。 詳細については、「 [SMSの設定」を参照してください](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)。

