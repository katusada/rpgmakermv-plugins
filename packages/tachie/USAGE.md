使い方
======

 1. 以下形式の名前の立ち絵画像ファイルを Picture フォルダに配置します。

        characterA1.png
        characterA2.png
        characterA3.png
        characterA4.png
        characterA5.png
        characterB1.png
        characterB2.png
        :
        :

 2. Data フォルダに Tachie.csv という名前で以下形式の立ち絵定義ファイルを
    作成してください。

        characterA, キャラA, 笑い, 怒り, 呆れ, 不満
        characterB, キャラB, 笑い, 緊張, 呆れ, 不満
        :
        :

  - 一列目は Picture フォルダに配置した立ち絵画像ファイル名から拡張子と
    末尾の数字を取り除いた部分です
  - 二列目はキャラクターの名前です  
    プラグインコマンドから立ち絵画像ファイルを指定するときに、この名前で
    指定します
  - 三列目以降は、立ち絵画像ファイルの表情の名前です  
    プラグインコマンドから表情を指定するときに、この名前で指定します  
    `{キャラクター名}2` 以降の表情差分に名前をつけてください  
    （`{キャラクター名}1` は表情未指定時に使われます）

    上記例では characterA2.png が キャラA の 笑い、characterA3.png が
    キャラA の 怒り という設定になっています。

 3. プラグインコマンドに立ち絵表示コマンドを入力して立ち絵を表示を行います。  
    プラグインコマンドの詳細は下記のプラグインコマンド一覧を参照してください。


プラグインコマンド一覧
======================

立ち絵表示
----------

    立ち絵表示 <キャラクター名> <表情> <位置> <距離> <横位置調整> <縦位置調整>
               <スライド横> <スライド縦> <表示にかける時間> <完了までウェイト>

立ち絵を表示します。


    <キャラクター名> 文字列

立ち絵定義ファイルで設定したキャラクターの名前


    <表情> 文字列

立ち絵定義ファイルで設定したキャラクターの表情  
未指定で1番目の表情


    <位置> { 左 | 中 | 右 }

立ち絵の X 座標を位置に応じた値にする  
未指定で中央


    <距離> { 近 | 中 | 遠 }

立ち絵の拡大率と Y 座標を距離に応じた値にする  
未指定で中距離


    <横位置調整> { 横位置調整:n | 横:n }

立ち絵の X 座標に指定した数値を加える


    <縦位置調整> { 縦位置調整:n | 縦:n }

立ち絵の Y 座標に指定した数値を加える


    <スライド横> スライド横:n

立ち絵の表示開始時の X 座標から指定した数値を引く


    <スライド縦> スライド縦:n

立ち絵の表示開始時の Y 座標から指定した数値を引く


    <表示にかける時間> nフレーム

表示にかける時間をフレーム数で指定する  
未指定で瞬間表示


    <完了までウェイト> { ウェイトあり | ウェイトなし }

表示が完了するまでウェイトする  
未指定でウェイトなし  
瞬間表示の場合は無視される


呼び出し例

    立ち絵表示 キャラA 近

キャラAを表情1で画面中央、近距離に瞬間表示


    立ち絵表示 キャラA 表情2 左 横:5 縦:-5 スライド横:20 60フレーム ウェイトあり

キャラAを表情2で画面左、中距離、左に5px、上に5pxずらした位置に  
20px左にスライドしながら60フレームかけて表示する  
表示が完了するまでウェイトする


立ち絵変更
----------

    立ち絵変更 <変更前キャラクター名> <変更後キャラクター名> <表情>
               <変更にかける時間> <完了までウェイト>

立ち絵を変更します。  
主に、表情差分や衣装差分の切り替えを行うためのコマンドです。


    <変更前キャラクター名> 文字列

立ち絵定義ファイルで設定したキャラクターの名前


    <変更後キャラクター名> 文字列

立ち絵定義ファイルで設定したキャラクターの名前  
未指定で現在と同じキャラクターの表情セットを使う


    <表情> 文字列

立ち絵定義ファイルで設定したキャラクターの表情
未指定で1番目の表情


    <表示にかける時間> nフレーム

表示にかける時間をフレーム数で指定する  
未指定で瞬間表示


    <完了までウェイト> { ウェイトあり | ウェイトなし }

表示が完了するまでウェイトする  
未指定でウェイトなし  
瞬間表示の場合は無視される


呼び出し例

    立ち絵変更 キャラA 表情2 30フレーム

キャラAを表情2に30フレームかけて変更する


    立ち絵変更 キャラA キャラB 30フレーム

キャラAをキャラBの表情1に30フレームかけて変更する


立ち絵移動
----------

    立ち絵移動 <キャラクター名> <位置> <横位置調整> <縦位置調整>
               <移動にかける時間> <完了までウェイト>

立ち絵を移動します


    <キャラクター名> 文字列

立ち絵定義ファイルで設定したキャラクターの名前


    <位置> { 左 | 中 | 右 }

立ち絵の X 座標を位置に応じた値にする  
未指定で中央


    <横位置調整> { 横位置調整:n | 横:n }

立ち絵の X 座標に指定した数値を加える


    <縦位置調整> { 縦位置調整:n | 縦:n }

立ち絵の Y 座標に指定した数値を加える


    <表示にかける時間> nフレーム

表示にかける時間をフレーム数で指定する  
未指定で瞬間表示


    <完了までウェイト> { ウェイトあり | ウェイトなし }

表示が完了するまでウェイトする  
未指定でウェイトなし  
瞬間表示の場合は無視される


呼び出し例

    立ち絵移動 キャラA 右 横:-15

キャラAを画面右、右に15pxずらした位置に30フレームかけて移動させる


立ち絵消去
----------

    立ち絵消去 <キャラクター名> <スライド横> <スライド縦> <消去にかける時間>
               <完了までウェイト>

立ち絵を消去します


    <キャラクター名> 文字列

立ち絵定義ファイルで設定したキャラクターの名前


    <スライド横> スライド横:n

立ち絵の表示開始時の X 座標から指定した数値を引く


    <スライド縦> スライド縦:n

立ち絵の表示開始時の Y 座標から指定した数値を引く


    <表示にかける時間> nフレーム

表示にかける時間をフレーム数で指定する  
未指定で瞬間表示


    <完了までウェイト> { ウェイトあり | ウェイトなし }

表示が完了するまでウェイトする  
未指定でウェイトなし  
瞬間表示の場合は無視される


呼び出し例

    立ち絵消去 キャラA 30フレーム

キャラAを30フレームかけて消去する


よくある質問
============

Q. プラグインコマンドは間違ってないのに立ち絵が表示されない  
A. プラグインを有効化しても、プロジェクトを保存しないとプラグインコマンドが
   認識されないようです。一度プロジェクトを保存してやり直してみてください。

Q. 表情を変更したい  
A. 立ち絵変更コマンドを使ってください。

Q. 表示しているキャラの距離を変更したい  
A. 消去と表示を組み合わせてください。

Q. 透明度の指定ができない  
A. 未実装の機能です。今後の実装予定を参照してください。

Q. 同距離、同位置に複数のキャラクターを表示したい  
A. 未実装の機能です。今後の実装予定を参照してください。

Q. キャラクターの重なり順を制御したい  
A. 未実装の機能です。今後の実装予定を参照してください。


今後の予定
==========

- 表示、移動時の透明度指定  
  表示、移動コマンドで透明度を指定できるように

- 同距離、同位置の複数キャラクター表示  
  同じ距離、同じ位置に複数のキャラクターを配置できるように

- 重なり順の制御  
  キャラクターの重なり順を明示的に指定できるように

- プラグインコマンドで指定した画像のプリロード対応  
  プラグインコマンドで指定した画像をマップ遷移時にプリロードするように

- プラグインパラメータによる各種の値の設定  
  立ち絵プラグインで使用するピクチャ番号などをプラグインパラメータで
  指定できるように
