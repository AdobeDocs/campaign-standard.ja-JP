---
title: SMS およびプッシュコンテンツエディターインターフェイス
description: エディターの各セクションを使用して SMS やプッシュコンテンツを変更する方法について説明します。
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: d430d0e7-1201-49c6-aad3-a2c03d02290c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 96%

---

# SMS およびプッシュコンテンツエディターインターフェイス{#sms-and-push-content-editor-interface}

SMS およびプッシュコンテンツエディターは、メッセージの表示と編集が可能な 2 つのセクションに分かれています。

1. **アクションバー**&#x200B;には、ページの一般的なオプションが含まれています。ここから、パーソナライゼーションフィールドやコンテンツブロックの挿入、条件付きテキストの追加、SMS コンテンツのプレビューをおこなうことができます。[SMS とプッシュコンテンツエディターのアクションバー](#sms-and-push-content-editor-action-bar)を参照してください。
1. 画面の&#x200B;**編集領域**&#x200B;では、テキストメッセージを直接入力し、パーソナライゼーションを挿入する場所を選択できます。[SMS およびプッシュコンテンツ編集モード](#sms-and-push-content-edition-modes)を参照してください。

## SMS とプッシュコンテンツエディターのアクションバー {#sms-and-push-content-editor-action-bar}

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
   <td> <span class="uicontrol">Preview</span> <br /> </td> 
   <td> SMS のみ<br /> </td> 
   <td> 受信者のメールがどのようにレンダリングされるかを表示できます。<a href="../../sending/using/previewing-messages.md">メッセージのプレビュー</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Undo</span> <br /> </td> 
   <td> SMS とプッシュ<br /> </td> 
   <td> 最後に実行された操作をキャンセルします。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Redo</span> <br /> </td> 
   <td> SMS とプッシュ<br /> </td> 
   <td> 最後にキャンセルした操作をやり直します。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insert personalization field</span> <br /> </td> 
   <td> SMS とプッシュ<br /> </td> 
   <td> データベースからコンテンツにフィールドを追加できます。<a href="../../designing/using/personalization.md#inserting-a-personalization-field" target="_blank">パーソナライゼーションフィールドの挿入</a><br />を参照してください。 </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insert content block</span> <br /> </td> 
   <td> SMS とプッシュ<br /> </td> 
   <td> コンテンツにパーソナライゼーションブロックを追加できます。<a href="../../designing/using/personalization.md#adding-a-content-block" target="_blank">コンテンツブロックの追加</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Enable dynamic text</span> <br /> </td> 
   <td> SMS とプッシュ<br /> </td> 
   <td> コンテンツにダイナミックテキストを挿入できます。<a href="../../channels/using/defining-dynamic-text.md" target="_blank">ダイナミックテキストの定義</a>を参照してください。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Disable dynamic text</span> <br /> </td> 
   <td> SMS とプッシュ<br /> </td> 
   <td> ダイナミックテキストを削除できます。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## SMS およびプッシュコンテンツ編集モード {#sms-and-push-content-edition-modes}

SMS およびプッシュコンテンツエディターでは、次の機能を使用できます。

* テキストの入力。
* パーソナライゼーションフィールドの追加。詳しくは、[パーソナライゼーションフィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field)を参照してください。
* コンテンツブロックの追加。詳しくは、[コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)を参照してください。
* ダイナミックテキストの追加。詳しくは、[ダイナミックテキストの定義](../../channels/using/defining-dynamic-text.md)を参照してください。
* SMS 送信者の名前のパーソナライズ（SMS のみ）。詳しくは、[SMS の設定](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)を参照してください。
