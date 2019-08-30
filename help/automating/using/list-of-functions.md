---
title: 関数のリスト
seo-title: 関数のリスト
description: 関数のリスト
seo-description: クエリ編集ツールを使用すると、高度な関数を使用して複雑なフィルター処理を実行できます。
page-status-flag: 決して活性化されていない
uuid: fd50fc99-1e7a-479b- beb7-1f246b419d46
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: フィルタリングデータ
discoiquuid: 3cdd962-1c59-4cd8- b29e-36aa2562fac6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 83be3f22f3508248f2a4666080a7207998093dc3

---


# 関数のリスト{#list-of-functions}

## 関数について {#about-functions}

クエリ編集ツールを使用すると、高度な関数を使用して複雑なフィルター処理を実行できます。これを行うには、ワークスペースで使用できる **[!UICONTROL Expression]** 要素がツールパレットに含まれます。この要素の詳細については、特定 [のセクション](../../automating/using/advanced-expression-editing.md)で詳しく説明します。

この要素を使用すると、条件を手動で入力できます。ここでは、次のセクションで定義した関数を使用できます。

必要な結果と操作データのタイプに応じて、いくつかの関数タイプを使用できます。

* 日付
* ジオマーケティング
* 数値
* その他の機能
* 集計
* 文字列操作
* 並べ替え

## 日付 {#dates}

日付関数は日付または時刻の値を操作するために使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> 日付に日数を追加します<br /> </td> 
   <td> AddDays（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>追加時間</strong><br /> </td> 
   <td> 日付に数時間を追加します<br /> </td> 
   <td> AddHours（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> 日付に分数を追加します<br /> </td> 
   <td> AddMinutes（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> 日付に月数を追加します<br /> </td> 
   <td> AddMonths（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> 日付に秒数を追加します<br /> </td> 
   <td> AddSeconds（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> 日付に年数を追加します<br /> </td> 
   <td> AddYears（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> 日付のみを返します（時刻は00:00）。<br /> </td> 
   <td> DateOnly（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>デイ</strong><br /> </td> 
   <td> 日付の日付を表す数値を返します<br /> </td> 
   <td> 日（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> 日付の年の日付を表す数値を返します<br /> </td> 
   <td> DayOfYear（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>デイサゴ</strong><br /> </td> 
   <td> 現在の日付からn日を引いた日付を返します<br /> </td> 
   <td> DaysHello（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>デイサゴ</strong><br /> </td> 
   <td> 現在の日付を負のyyyymmddとして返します。<br /> </td> 
   <td> DaysAsInt（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysdiff</strong><br /> </td> 
   <td> 2つの日付間の日数<br /> </td> 
   <td> DaysDiff（&lt;終了日&gt;、&lt;開始日&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>デイセールス</strong><br /> </td> 
   <td> 日付の日数を返します<br /> </td> 
   <td> DaySold（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> サーバーの現在のシステム日付を返します<br /> </td> 
   <td> getDate（）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>アワー</strong><br /> </td> 
   <td> 日付の時刻を返します<br /> </td> 
   <td> 時間（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> 2つの日付間の時間数を返します<br /> </td> 
   <td> HoursDiff（&lt;終了日&gt;、&lt;開始日&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ローカルToutc</strong><br /> </td> 
   <td> ローカルの日付と時刻をUTCに変換します<br /> </td> 
   <td> localToUTC（&lt; date&gt;、&lt; Time Zone&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>議事録</strong><br /> </td> 
   <td> 日付の分を返します<br /> </td> 
   <td> 分（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinuesDiff</strong><br /> </td> 
   <td> 2つの日付間の分数を返します<br /> </td> 
   <td> MinuesDiff（&lt;終了日&gt;、&lt;開始日&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月</strong><br /> </td> 
   <td> 日付の月を表す数値を返します<br /> </td> 
   <td> 月（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ムーンサゴ</strong><br /> </td> 
   <td> 現在の日付に対応する日付を返します<br /> </td> 
   <td> MonthsInformation（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月単位</strong><br /> </td> 
   <td> 2つの日付間の月数を返します<br /> </td> 
   <td> MonthsDiff（&lt;終了日&gt;、&lt;開始日&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthSold</strong><br /> </td> 
   <td> 日付の月数を月単位で返します<br /> </td> 
   <td> MonthSold（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>セカンド</strong><br /> </td> 
   <td> 日付の秒を返します<br /> </td> 
   <td> 2番目（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最も古い</strong><br /> </td> 
   <td> 最も古い日付を返します </td> 
   <td> 最も古い（&lt;日付&gt;、&lt;日付&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>セカンダリdiff</strong><br /> </td> 
   <td> 2つの日付間の秒数を返します<br /> </td> 
   <td> secondsDiff（&lt;終了日&gt;、&lt;開始日&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブデイズ</strong><br /> </td> 
   <td> 日付から日数を減算します<br /> </td> 
   <td> subDays（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブ時間</strong><br /> </td> 
   <td> 日付から数時間を減算します<br /> </td> 
   <td> サブ時間（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブ秒</strong><br /> </td> 
   <td> 日付から分数を減算します<br /> </td> 
   <td> サブ分（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブ月</strong><br /> </td> 
   <td> 日付から月数を減算します<br /> </td> 
   <td> subMonths（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブ秒</strong><br /> </td> 
   <td> 日付から秒数を減算します<br /> </td> 
   <td> subSeconds（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブイヤー</strong><br /> </td> 
   <td> 日付から年数を減算します<br /> </td> 
   <td> subyees（&lt; date&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トデート</strong><br /> </td> 
   <td> 日付+時刻を日付として変換します<br /> </td> 
   <td> ToDate（&lt; date+ time&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> 文字列を日付+時刻に変換します<br /> </td> 
   <td> ToDateTime（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TimeDateTimeWithZone</strong><br /> </td> 
   <td> 文字列を日付+タイムゾーンに変換します。<br /> 例:ToDateTimeWithTimeZone（"2019-02-1908:09:00"、「アジア/テヘラン」）<br /> </td> 
   <td> ToDateTimeWithTimeZone（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncate</strong><br /> </td> 
   <td> 日付+時刻を最も近い2番目の日付に丸めます<br /> </td> 
   <td> truncate（@ LastModified、&lt;の秒数&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トランデート</strong><br /> </td> 
   <td> 日付+時刻を秒単位で指定した精度に丸めます<br /> </td> 
   <td> TruncateTZ（&lt; date&gt;、&lt;の秒数&gt;、&lt;タイムゾーン&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トランククォーター</strong><br /> </td> 
   <td> 四半期に日付を四捨五入します<br /> </td> 
   <td> SubQuarter（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トランケート時間</strong><br /> </td> 
   <td> タイムパーツを最も近い2番目の部分まで四捨五入します<br /> </td> 
   <td> truncTime（&lt; date&gt;、&lt;の秒数&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トランケート</strong><br /> </td> 
   <td> 日付を週に四捨五入します<br /> </td> 
   <td> truncek（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncate</strong><br /> </td> 
   <td> 日付+時刻を年の1月1日に丸めます<br /> </td> 
   <td> Truncate（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>平日</strong><br /> </td> 
   <td> 日付の週の曜日を表す数値を返します<br /> </td> 
   <td> WeekDay（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年</strong><br /> </td> 
   <td> 日付の年を表す数値を返します<br /> </td> 
   <td> 年（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年と月</strong><br /> </td> 
   <td> 日付の年と月を表す数値を返します<br /> </td> 
   <td> YearAndMonth（&lt; date&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> 2つの日付間の年数を返します<br /> </td> 
   <td> YearsDiff（&lt;終了日&gt;、&lt;開始日&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年間販売済み</strong><br /> </td> 
   <td> 日付を年単位で返します<br /> </td> 
   <td> YearSold（&lt; date&gt;）<br /> </td> 
  </tr> 
 </tbody> 
</table>

## ジオマーケティング {#geomarketing}

ジオマーケティング関数は地理値を操作するために使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ディスタンス</strong><br /> </td> 
   <td> 経度と緯度で定義された2点間の距離をキロメートル単位で返します（度単位）。<br /> </td> 
   <td> 距離（経度A&gt;&gt;、&lt; Latitude A&gt;、&lt;経度B&gt;、&lt; Latitude B&gt;）<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 数値 {#numerical}

数値関数は、テキストを数値に変換するために使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>アブス</strong><br /> </td> 
   <td> 数値の絶対値を返します<br /> </td> 
   <td> Abs（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>セイル</strong><br /> </td> 
   <td> 数値以上の最小の整数を返します<br /> </td> 
   <td> ceil（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>フロア</strong><br /> </td> 
   <td> 数値以上の最大整数を返します<br /> </td> 
   <td> 床（&lt;番号&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大</strong><br /> </td> 
   <td> 2つの数値を返します<br /> </td> 
   <td> 最大値（&lt; number1&gt;，&lt; number2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最小</strong><br /> </td> 
   <td> 2つの数値の小さい方を返します<br /> </td> 
   <td> 最小（&lt; number1&gt;，&lt; number2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> n1からn2までの整数除算の残りの部分を返します<br /> </td> 
   <td> Mod（&lt; number1&gt;，&lt; number2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>パーセント</strong><br /> </td> 
   <td> パーセンテージで表される2つの数値の比率を返します<br /> </td> 
   <td> パーセント（&lt; number1&gt;，&lt; number2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ランダム</strong><br /> </td> 
   <td> ランダム値を返す<br /> </td> 
   <td> ランダム（）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ラウンド</strong><br /> </td> 
   <td> 数値をn進数に四捨五入します<br /> </td> 
   <td> ラウンド（&lt; number&gt;，&lt; decimals&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サイン</strong><br /> </td> 
   <td> 数値の符号を返します<br /> </td> 
   <td> サイン（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トダブル</strong><br /> </td> 
   <td> 整数を浮動小数点に変換します<br /> </td> 
   <td> ToDouble（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> floatを64ビット整数に変換します<br /> </td> 
   <td> ToInt64（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> 浮動小数点を整数に変換します<br /> </td> 
   <td> ToInteger（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トランス</strong><br /> </td> 
   <td> n1からn2の小数点を切り捨てます<br /> </td> 
   <td> trunc（&lt; n1&gt;，&lt; n2&gt;）<br /> </td> 
  </tr> 
 </tbody> 
</table>

## その他 {#others}

このテーブルには、使用可能な残りの関数が含まれます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ケース</strong><br /> </td> 
   <td> 条件が検証された場合は、値1を返します。それ以外の場合は、value2を返します<br /> </td> 
   <td> ケース（&lt;条件&gt;、&lt; value1&gt;）、Else（&lt; value2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>クリアビット</strong><br /> </td> 
   <td> 値のフラグを削除します<br /> </td> 
   <td> ClearBit（&lt; identifier&gt;，&lt;フラグ&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>コークシュ</strong><br /> </td> 
   <td> value1がゼロまたはnullの場合はvalue2を返し、それ以外の場合はvalue1を返します<br /> </td> 
   <td> Coalesce（&lt; value1&gt;，&lt; value2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>デコード</strong><br /> </td> 
   <td> 値3はvalue1= value2です。それ以外の場合は4を返します<br /> </td> 
   <td> decode（&lt; value1&gt;，&lt; value2&gt;，&lt; value3&gt;，&lt; value4&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>その他</strong><br /> </td> 
   <td> 値1を返します（ケース関数のパラメータとしてのみ使用できます）。<br /> </td> 
   <td> その他（&lt; value1&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> 電子メールアドレスからドメインを抽出します<br /> </td> 
   <td> GetEmailDomain（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> ミラーページサーバーのURLを取得します<br /> </td> 
   <td> GetMirrorUrl（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>イフ</strong><br /> </td> 
   <td> 式がtrueの場合は値1を返し、それ以外の場合はvalue2を返します<br /> </td> 
   <td> if（&lt; condition&gt;，&lt; value1&gt;，&lt; value2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> フラグが値に含まれているかどうかを示します<br /> </td> 
   <td> IsBitSet（&lt; identifier&gt;，&lt;フラグ&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> 文字列が空の場合はvalue2を返し、それ以外の場合はvalue3を返します<br /> </td> 
   <td> ISEmptyString（&lt; string&gt;，&lt; value2&gt;，&lt; value3&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ヌル</strong><br /> </td> 
   <td> 引数がNULLの場合、空の文字列を返します<br /> </td> 
   <td> NULL（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowID</strong><br /> </td> 
   <td> 行番号を返す<br /> </td> 
   <td> RowID<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> 値のフラグを強制的に強制します<br /> </td> 
   <td> SetBit（&lt; identifier&gt;，&lt;フラグ&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> 数値をブール値に変換します<br /> </td> 
   <td> ToBoolean（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>時</strong><br /> </td> 
   <td> 式が検証された場合は、値1を返します。それ以外の場合は、value2を返します（ケース関数のパラメータとしてのみ使用できます）。<br /> </td> 
   <td> （&lt; condition&gt;，&lt; value1&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ニューUID</strong><br /> </td> 
   <td> 新しいUUIDを返します。<br /> </td> 
   <td> ニューUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 文字列 {#string}

文字列関数は、文字列のセットを操作するために使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> すべてのパラメーターがNULLではなく、空でないかどうかを示します<br /> </td> 
   <td> AllNonNull2（&lt; string&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> すべてのパラメーターがNULLではなく、空でないかどうかを示します<br /> </td> 
   <td> AllNonNull3（&lt; string&gt;，&lt; string&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> 文字列内の最初の文字のASCII値を返します<br /> </td> 
   <td> ASCII（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>チャー</strong><br /> </td> 
   <td> 'n'ASCIIコードに対応する文字を返します<br /> </td> 
   <td> char（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>シャルインデックス</strong><br /> </td> 
   <td> string1の文字列2の位置を返します<br /> </td> 
   <td> Charindex（&lt; string&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> 文字列内の文字数を返す<br /> </td> 
   <td> DataLength（&lt; String&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> 文字列のn番目の行（1からn）を返します<br /> </td> 
   <td> GetLine（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IFEQUAL</strong><br /> </td> 
   <td> 最初の2つのパラメーターが等しい場合は3番目のパラメーターを返し、それ以外の場合は最後のパラメーターを返します<br /> </td> 
   <td> IFEquals（&lt; string&gt;，&lt; string&gt;，&lt; string&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>イスミムノール</strong><br /> </td> 
   <td> パラメーターとして渡されたメモがnullかどうかを示します<br /> </td> 
   <td> IsMemNull（&lt;メモ&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> パラメーターとして渡される2つの文字列を計算します。戻り値の各文字列間にスペースが追加されます。<br /> </td> 
   <td> JuxTWords（&lt; string&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> パラメーターとして渡される3つの文字列を計算します。戻り値の各文字列間にスペースが追加されます。<br /> </td> 
   <td> JuxWords3（&lt; string&gt;，&lt; string&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ラパッド</strong><br /> </td> 
   <td> 左側の完成した文字列を返します<br /> </td> 
   <td> LPad（&lt; string&gt;，&lt; number&gt;，&lt; caracecre&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>左</strong><br /> </td> 
   <td> 文字列の最初のn文字を返します<br /> </td> 
   <td> 左（&lt; string&gt;、&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>長さ</strong><br /> </td> 
   <td> 文字列の長さを返す<br /> </td> 
   <td> 長さ（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>下</strong><br /> </td> 
   <td> 文字列を小文字で返します<br /> </td> 
   <td> 下（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ルトリム</strong><br /> </td> 
   <td> 文字列の左側にスペースを削除します<br /> </td> 
   <td> ltrim（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> 文字列のMD5キーの16進表記を返します<br /> </td> 
   <td> md5ダイジェスト（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemosContains</strong><br /> </td> 
   <td> メモにパラメーターとして渡される文字列が含まれるかどうかを指定します<br /> </td> 
   <td> MemosContains（&lt;メモ&gt;，&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>パッド</strong><br /> </td> 
   <td> 右側の完成した文字列を返します<br /> </td> 
   <td> rPad（&lt; string&gt;，&lt; number&gt;，&lt;文字&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>置換</strong><br /> </td> 
   <td> 指定した文字列（2番目のパラメータ）値を文字列内の別の文字列値（3番目のパラメータ）に置き換えます（1stパラメータ）。<br /> </td> 
   <td> 置換（&lt; String&gt;，&lt; String&gt;，&lt; String&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>右</strong><br /> </td> 
   <td> 文字列の最後のn文字を返します<br /> </td> 
   <td> 右（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トリム</strong><br /> </td> 
   <td> 文字列の右側にスペースを削除します<br /> </td> 
   <td> rtrim（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> 指定されたUTF8文字列の標準SHA <strong>256</strong> ハッシュを計算します<br /> </td> 
   <td> Sha256ダイジェスト（&lt; String&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> 指定されたUTF8文字列の標準SHA <strong>384</strong> ハッシュを計算します<br /> </td> 
   <td> Sha384ダイジェスト（&lt; String&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> 指定されたUTF8文字列の標準SHA <strong>512</strong> ハッシュを計算します<br /> </td> 
   <td> sha512ダイジェスト（&lt; String&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>スマート</strong><br /> </td> 
   <td> 各単語の最初の文字の文字列を大文字で返します<br /> </td> 
   <td> スマート（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>文字列</strong><br /> </td> 
   <td> 文字列の文字n1から始まり、n2の長さのサブストリングを抽出します<br /> </td> 
   <td> 文字列（&lt; string&gt;，&lt; offset&gt;，&lt; length&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> 数値を文字列に変換します<br /> </td> 
   <td> toIntlString（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> 数値を文字列に変換します<br /> </td> 
   <td> ToString（&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>上部</strong><br /> </td> 
   <td> 文字列を大文字で返します<br /> </td> 
   <td> 上位（&lt; string&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> 他の2つのパラメータが等しい場合、パラメータとして渡されたリンクの外部キーを返します<br /> </td> 
   <td> VirtualLink（&lt; number&gt;，&lt; number&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> 他の2つのパラメーターが等しい場合に、パラメーターとして渡されたリンクの外部（テキスト）キーを返します<br /> </td> 
   <td> virtualInkStr（&lt; string&gt;，&lt; number&gt;，&lt; number&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>暗号化_ aESCCDecrypt</strong><br /> </td> 
   <td> 16進形式で暗号化された値を"x<strong></strong>」プレフィックス（1stパラメータ）で復号化します（2番目のパラメータ（2番目のパラメータ）と16進形式の初期化ベクター（3番目のパラメータ）<br /> </td> 
   <td> encryption_ aESCCDecrypt（&lt; String&gt;，&lt; String&gt;，&lt; String&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>暗号化_ aESCCEncrypt</strong><br /> </td> 
   <td> AESアルゴリズム（CBCブロックモード）を使用して、キー（第2パラメータ）と初期化ベクター（第3パラメータ）との文字列（第1パラメータ）を暗号化します。キーと初期化ベクターは、16進表記（\ <strong>xから開始）で指定</strong>する必要があります。結果は\ <strong>yのない16進数に</strong>なります。<br /> 鍵の大きさは128ビット、192ビット、256ビット（16、24、32の16進文字）であることに注意してください。しかし、このキーと同じ長さの256ビットとランダム化IVを使用することをお勧めします。<br /> </td> 
   <td> encryption_ aESCCEncrypt（&lt; String&gt;，&lt; String&gt;，&lt; String&gt;）<br /> 例:encryption_ aESCCEncrypt（johndoe@example.com，"\<strong>x0123456789ABCDEF0123456789ABCDEF</strong>」，"\<strong>x0123456789ABCDEFEDCBA9876543210"</strong>）<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 集計 {#aggregates}

集計関数は、ワークフローのアクティビティから追加のデータ [](../../automating/using/query.md#enriching-data) を追加する場合にのみ使用 **[!UICONTROL Query]** できます。

集計関数は、一連の値に対して計算を実行するために使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>平均</strong>、平均<br /> </td> 
   <td> 数値列の平均を返します。<br /> </td> 
   <td> 平均（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>、Count（NULL以外）<br /> </td> 
   <td> 列のNULL以外の値をカウントします。<br /> </td> 
   <td> Count（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountHeight</strong>、カウント<br /> </td> 
   <td> すべての値（NULL値と重複を含む）をカウントします。<br /> </td> 
   <td> CountHeight（）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountDistinct</strong>、Distinctカウント<br /> </td> 
   <td> 列内のNULL以外の個別の値をカウントします。<br /> </td> 
   <td> CountDistinct（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大</strong>、最大<br /> </td> 
   <td> 数値、文字列、または日付の列の最大値を返します。<br /> </td> 
   <td> 最大値（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ミン</strong>ミン<br /> </td> 
   <td> 数値、文字列、または日付の列の最小値を返します。<br /> </td> 
   <td> 最小（&lt; value&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum Sum Sum Sum Sum Sum Sum Sum</strong>Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum Sum<br /> </td> 
   <td> 数値列の値の和を返します。<br /> </td> 
   <td> Sum（&lt; value&gt;）<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 表現 {#representation}

表示関数は、値の順序付けに使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> 降順の並べ替えを適用します<br /> </td> 
   <td> Desc（&lt; value1&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> パーティション内の結果を並べ替えます<br /> </td> 
   <td> OrderBy（&lt; value1&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>パーティションBY</strong><br /> </td> 
   <td> テーブルに対するクエリの結果をパーティション分割します<br /> </td> 
   <td> PartitionBy（&lt; value1&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ロWnンム</strong><br /> </td> 
   <td> テーブルパーティションと並べ替えシーケンスに基づいて、行番号を生成します。この関数はMySQLではサポートされていません<br /> </td> 
   <td> RowNum（PartitionBy（&lt; value1&gt;）、OrderBy（&lt; value1&gt;））<br /> </td> 
  </tr> 
 </tbody> 
</table>

